<template>
  <div>
      <md-card md-with-hover class="timeline" v-for="informacoes in info" v-bind="informacoes" :key="informacoes">
        <md-ripple>
          <md-card-header>
            <div v-if="informacoes.cardType ==='EXPENSE'">
              <img src='assets/hotel-bell.png'>
            </div>
            <div v-else-if="informacoes.cardType ==='ACCOUNTABILITY_CREATED'">
            Coco
            </div>
            <div v-else-if="informacoes.cardType ==='ACCOUNTABILITY_SUBMITTED'">
            xibiu
            </div>
             <div v-else>
            piru
            </div>
          </md-card-header>
          <md-card-content v-bind="info" :key="info">
              <p>Tipo</p>
          </md-card-content>
        </md-ripple>
      </md-card>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Timeline',
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('https://api-front-end-challenge.buildstaging.com/api/timeline')
      .then(response => {
        (this.info = response.data.content)
      })
  }
}
</script>

<style scoped>
.timeline {
  margin: 1rem;
  border-radius: .75rem;
}
.timeline__error{
  padding: 1rem;
}
</style>
