<template>
  <div>
    <md-card md-with-hover class="timeline">
      <section v-if="errored" class="timeline__error">
        <p>Pedimos desculpas, não estamos conseguindo recuperar as informações no momento. Por favor, tente novamente mais tarde.</p>
      </section>
      <section v-else>
        <div v-if="loading">
          Carregando...
        </div>
        <div
         v-else
         v-for="informacoes in info"
        >
          <md-ripple>
            <md-card-header>
              <h1 class="md-title"> {{ informacoes.content }} </h1>
            </md-card-header>
            <md-card-content>
              <section>
              </section>
            </md-card-content>
          </md-ripple>
        </div>  
      </section>    
    </md-card>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Timeline',
  data () {
    return {
      info: null,
      loading: true,
      errored: false
    }
  },
  mounted () {
    axios
      .get('https://api-front-end-challenge.buildstaging.com/api/timeline')
      .then(response => {
        (this.info = response)
      })
      .catch(error => {
        console.log(error)
        this.errored = true
      })
      .finally(() => this.loading = false)
  }
}
</script>

<style scoped>
.timeline {
  margin: 0 1rem;
  border-radius: .75rem;
}
.timeline__error{
  padding: 1rem;
}
</style>