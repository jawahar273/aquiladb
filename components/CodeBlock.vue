<template>
  <div class="hero">
    <div class="hero-body space-block">
      <div class="space-item">
        <h1>Get started now</h1>
        <pre
          v-highlightjs="dockerRepo"
          class="is-language"
        >
        <code class="bash" />
        </pre>
      </div>
      <div class="space-item">
        <p>Run Docker</p>
        <pre
          v-highlightjs="dockerRun"
          class="is-language"
        >
        <code class="bash" />
        </pre>
      </div>

      <b-tabs v-model="activeTab" class="is-paddingless space-item">
        <b-tab-item v-for="(content) in urls" :key="content.name" :label="content.name">
          <pre
            v-highlightjs="content.data"
            class="is-language"
          >
        <code :class="content.name" />
        </pre>
        </b-tab-item>
      </b-tabs>
    </div>
  </div>
</template>

<script>
import { ToastProgrammatic as Toast } from 'buefy'

export default {
  name: 'CodeBlock',
  data () {
    return {
      loading: true,
      dockerRepo: '$ docker pull ammaorg/aquiladb:latest',
      dockerRun: '$ docker run -d -i -p 50051:50051 -t ammaorg/aquiladb:latest',
      activeTab: null,
      urls: []
    }
  },
  watch: {
    url: {
      deep: true
    }
  },
  mounted () {
    this.getTheCodeFromGist()
  },
  methods: {
    async getTheCodeFromGist (name) {
      this.urls = [
        {
          name: 'python',
          url: 'https://gist.githubusercontent.com/jawahar273/582eeef236f3d4a74f51cdaef06b2f5a/raw/a-mma-python-client.py'
        },
        {
          name: 'javaScript',
          url: 'https://gist.githubusercontent.com/jawahar273/5bad9fc6aa3c17ee56f59321fe6d91ab/raw/42bb555e93c35db8c21d8f804b97394ca2db40f8/angular-pwa.js'
        }
      ]
      for (let index = 0; index < this.urls.length; index++) {
        const element = this.urls[index]
        try {
          const response = await this.$axios.get(element.url)
          this.urls[index].data = response.data
        } catch {
          Toast.open('Unable to load the code')
        }
        this.activeTab = 0
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .hero-body {
    padding: 0px;
  }

</style>
