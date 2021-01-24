<template>
  <div>
    <md-card md-with-hover class="cabecalho">
        <md-ripple>
          <md-card-header>
            <h1 class="md-title"> Reembolso #{{ info.data.id }} </h1>
          </md-card-header>
          <md-card-content>
            <section>
              <p>Nome: {{ info.data.collaborator.name }}</p>
              <p>Email: {{ info.data.collaborator.email }}</p>
              <p>Justificativa: </p>
              <p>Finalidade: {{ info.data.purpose }}</p>
              <p>Projeto: {{ info.data.project.title }}</p>
              <p>Data: </p>
              <p>Quantidade: {{ info.data.accountabilityExtraInfo.amountOfPeople }}</p>
              <p> Inclui café da manhã:</p>
            </section>
            <hr>
            <section>
            <p>Atribuir analista</p>
              <input placeholder="Atribuir analista" class="cabecalho__input">
              <p>Centro de Custo: {{ info.data.costCenters.percentage}}</p>
            </section>
          </md-card-content>
        </md-ripple>
      </md-card>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Cabecalho',
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('https://api-front-end-challenge.buildstaging.com/api/header')
      .then(response => (this.info = response))
  }
}
</script>

<style scoped>
.cabecalho{
  background-image: linear-gradient(to right, #00d7ce, #00c5fc);
  text-align: left;
  margin: 0 1rem;
  color: #ffff;
  border-radius: .75rem;
}
hr{
  color: #fffff;
}

.cabecalho__input{
  border-radius: .2rem;
  border: none;
}

@media (min-width: 768px){
    hr {
    border: none;
    border-left: 1px solid #fffff;
    height: 100vh;
    width: 1px;
  }
}
</style>
