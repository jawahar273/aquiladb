<template>
  <div>
    <main>
      <section class="hero">
        <div class="hero-body">
          <div class="columns">
            <div class="column space-block medium-block is-one-third is-full-mobile">
              <h1 class="title title-bolder">
                Inevitable muscle for Machine Learning
              </h1>
              <p>
                AquilaDB is a latent vector and document database built for Data Scientists and Machine Learning engineers.
                Prototype an idea in minutes then scale at your pace.
              </p>
              <p class="space-item largest-space">
                AquilaDB is the Redis for Machine Learning.
              </p>
              <div class="space-item largest-space">
                <b-button class="is-twitter is-medium">
                  Learn More
                </b-button>
              </div>
            </div>
            <div class="column is-full-mobile">
              <code-block />
            </div>
          </div>
        </div>
      </section>
      <section class="hero content is-medium">
        <div class="hero-body columns has-text-centered custom-hero-body-padding">
          <div v-for="(feature, index) in features" :key="index" class="column is-one-quarter">
            <img
              :src="feature.img"
              width="50px"
            >
            <h3>
              {{ feature.name }}
            </h3>
            <p class="space-item largest-space">
              {{ feature.description }}
            </p>
            <p class="space-item largest-space">
              {{ feature.subDescription }}
            </p>
          </div>
        </div>
      </section>
    </main>
    <footer class="footer is-paddingless">
      <div class="hero">
        <div class="hero-body">
          <div class="columns is-flex" style=" justify-content: center;">
            <div class="column is-3">
              <div>
                <p class="title">
                  Documents
                </p>
                <ol>
                  <li>
                    <a href="#">Document</a>
                  </li>
                </ol>
              </div>
            </div>
            <div class="column is-3">
              <div>
                <p class="title">
                  Community
                </p>
                <ol>
                  <li>
                    <a class="is-twitter" href="#">Discord</a>
                  </li>
                  <li>
                    <a href="#">Twitter</a>
                  </li>
                  <li>
                    <a href="#">Github</a>
                  </li>
                </ol>
              </div>
            </div>
            <div class="column is-3">
              <div>
                <p class="heading" />
                <p class="title">
                  Others
                </p>
                <ol>
                  <li>
                    License
                  </li>
                  <li>
                    Project statistics
                  </li>
                </ol>
              </div>
            </div>
          </div>
          <!-- <div class="hero-footer has-text-centered">
            <p>
              Created with 3 organization
            </p>
          </div> -->
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  components: {
    CodeBlock: () => import('@/components/CodeBlock')
  },
  data () {
    return {
      features: [
        {
          name: 'Redis of ML',
          description: 'Efficient similarity search on dense vectors of any size that do not fit in RAM',
          subDescription: 'Native to your ML model\'s internal representation'
        },
        // {
        //   name: 'Rich JSON',
        //   description: 'Add meaning to indexed vectors with rich JSON metadata documents'
        // },
        {
          name: 'Easy to start',
          description: 'Setup and start prototyping your idea in minutes and scale at you pace',
          subDescription: 'In many cases, all you need is AquilaDB and pre-trained ML model'
        },
        {
          name: 'Language',
          description: 'Drop in addition to your existing programming system',
          subDescription: 'Be in your existing environment and continue working with you environment'
        },
        {
          name: 'Replication and Scaling',
          description: 'Take advantage of everything that CouchDB can offer',
          subDescription: 'Native connectivity to anything that understands Couch protocol'
        }
      ]
    }
  }
}
</script>
