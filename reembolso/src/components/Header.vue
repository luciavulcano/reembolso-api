<template>
  <div>
    <md-card md-with-hover class="cabecalho">
        <md-ripple class="cabecalho__riple">
          <md-card-header>
            <h1 class="md-title"> Reembolso #{{ info.id }} </h1>
          </md-card-header>
          <md-card-content class="cabecalho__content">
            <section>
              <p>Nome: {{ info.collaborator.name }}</p>
              <p>Email: {{ info.collaborator.email }}</p>
              <p>Justificativa: </p>
              <p>Finalidade: {{ info.purpose }}</p>
              <p>Projeto: {{ info.project.title }}</p>
              <p>Data: {{ new Date(info.createdOn).toLocaleDateString("en-GB") }}</p>
              <p>Quantidade: {{ info.accountabilityExtraInfo.amountOfPeople }}</p>
              <p>Inclui café da manhã:</p>
            </section>
            <hr>
            <section>
            <p>Atribuir analista</p>
              <input placeholder="Atribuir analista" class="cabecalho__input">
              <p>Centro de Custo: {{ info.costCenters.percentage}}</p>
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
      .then(response => (this.info = response.data))
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
  color: #ffff;
  width: 125px;
}
.cabecalho__riple{
  display: flex;
  flex-direction: column;
}
.cabecalho__content{
  display: flex;
  flex-direction: column;

}

.cabecalho__input{
  border-radius: .2rem;
  border: none;
  height: 2rem;
  padding: 0 1rem;
  margin-bottom: 1rem;
}

@media (min-width: 768px){
    hr {
    border: none;
    border-left: 1px solid;
    height: 150px;
    width: 1px;
  }
  .cabecalho__content{
    flex-direction: row;
    align-items: center;
  }
}
</style>
