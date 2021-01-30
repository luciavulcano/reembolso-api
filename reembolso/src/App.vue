<template>
  <div id="app">
    <section class="app__section__order--um">
      <cabecalho/>
      <timeline/>
    </section>
    <sidebar class="app__section__order--dois"/>
  </div>
</template>

<script>
import Cabecalho from './components/Header.vue'
import Timeline from './components/Timeline.vue'
import Sidebar from './components/Sidebar.vue'
export default {
  name: 'App',
  components: {
    'cabecalho': Cabecalho,
    'timeline': Timeline,
    'sidebar': Sidebar
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito+Sans:ital,wght@0,200;0,300;0,400;0,600;0,700;0,800;0,900;1,200;1,300;1,400;1,600;1,700;1,800;1,900&display=swap');
#app {
  font-family: 'Nunito Sans', sans-serif;
  margin-top: 2rem;
  display: flex;
  justify-content: center;
  flex-direction: column;
}
body{
  margin:0;
  padding:0;
  border-box: box-sizing;
}
p{
  margin:0;
}

.app__section__order--um{
  order: 2;
}
.app__section__order--dois{
  order: 1;
}

@media (min-width:768px){
  #app{
    flex-direction: row;
  }
  .app__section__order--um{
    order: 1;
  }
  .app__section__order--dois{
    order: 2;
  }
}
</style>
