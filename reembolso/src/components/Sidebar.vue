<template>
  <div>
    <md-card md-with-hover>
        <md-ripple>
          <md-card-header class="sidebar__header" v-bind="info" :key="info">
            <div class="sidebar__header__titulo">Status</div>
            <div v-if="info.accountabilityStatus === 'OPEN'" class="sidebar__header__subtitulo"  > Pendente </div>
          </md-card-header>

          <md-card-content v-for="informacoes in info" v-bind="informacoes" :key="informacoes" class="sidebar__content">
            <section>
              <h2 class="sidebar__content__h2">Saldo</h2>
              <p>Extrato</p>
              <hr>
              <p>Descrição</p>
              <p class="sidebar__content__p">Despesas declaradas: {{ informacoes.currency.symbol }} {{ informacoes.declared}}</p>
              <p class="sidebar__content__p">Despesas aprovadas: {{ informacoes.currency.symbol }} {{informacoes.approved}}</p>
              <p class="sidebar__content__p">Pagamento realizado: {{ informacoes.currency.symbol }} {{informacoes.received}}</p>
            </section>
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
.sidebar__content{
  padding: 1rem;
  border: solid 1px #6b7480;
  margin: 1rem;
  border-radius: 10px;
}
.sidebar__content__h2{
  color:#6b7480;
  text-transform: uppercase;
  font-size: 14px;
  text-align: center;
}
.sidebar__content__p{
  font-size: 14px;
  font-weight: 700;
}
</style>
