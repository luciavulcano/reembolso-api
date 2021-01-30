<template>
  <div>
    <md-card md-with-hover>
        <md-ripple>
          <md-card-header class="sidebar__header">
            <div class="sidebar__header__titulo">Status</div>
            <div v-if="info.accountabilityStatus === 'OPEN'" class="sidebar__header__subtitulo"> Pendente </div>
          </md-card-header>

          <md-card-content v-for="informacoes in info" v-bind="informacoes" :key="informacoes">
          </md-card-content>

          <md-card-actions>
          </md-card-actions>
        </md-ripple>
      </md-card>
  </div>
</template>

<script>
import axios from 'axios'

export default{
  name: 'Sidebar',
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('https://api-front-end-challenge.buildstaging.com/api/sidebar')
      .then(response => {
        (this.info = response.data.content)
      })
  }
}
</script>

<style scoped>
.sidebar__header{
  padding: 1rem 6rem;
  border: solid 3px #EDC911;
  margin: 1rem;
  border-radius: 10px;
  background-color: yellow;
  text-align: center;
}

.sidebar__header__titulo{
  font-size: 16px;
  margin-bottom: .6rem;
}
.sidebar__header__subtitulo{
  font-size: 24px;
}
</style>
