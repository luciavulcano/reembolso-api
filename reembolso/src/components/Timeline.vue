<template>
  <div>
      <md-card md-with-hover class="timeline" v-for="informacoes in info" v-bind="informacoes" :key="informacoes">
        <md-ripple class="timeline__ripple">
          <md-card-header class="timeline__header">
            <div v-if="informacoes.cardType ==='EXPENSE'" class="timeline__header__div">
              <svg  class="timeline__icon" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:svgjs="http://svgjs.com/svgjs" version="1.1" width="512" height="512" x="0" y="0" viewBox="0 0 682.66669 682" style="enable-background:new 0 0 512 512" xml:space="preserve"><g>
                <path xmlns="http://www.w3.org/2000/svg" d="m583.75 434.375h-198.628906v-33.253906h207.050781c5.714844 0 11.296875-2.328125 15.320313-6.386719 4.078124-4.113281 6.292968-9.574219 6.238281-15.378906-.78125-77.828125-31.683594-150.875-87.011719-205.679688-55.371094-54.84375-128.78125-85.046875-206.71875-85.046875s-151.347656 30.203125-206.714844 85.046875c-55.332031 54.804688-86.230468 127.851563-87.015625 205.695313-.054687 5.789062 2.164063 11.25 6.238281 15.363281 4.023438 4.058594 9.605469 6.386719 15.320313 6.386719h207.050781v33.253906h-198.628906c-31.015625 0-56.25 25.234375-56.25 56.25s25.234375 56.25 56.25 56.25h527.5c31.015625 0 56.25-25.234375 56.25-56.25s-25.234375-56.25-56.25-56.25zm0 0" fill="#0f68bd" data-original="#000000" style=""/>
                <path xmlns="http://www.w3.org/2000/svg" d="m320 51.128906c22.132812 0 43.898438 2.433594 64.992188 7.175782-2.144532-33.980469-30.476563-60.972657-64.992188-60.972657s-62.847656 26.992188-64.992188 60.972657c21.09375-4.742188 42.859376-7.175782 64.992188-7.175782zm0 0" fill="#0f68bd" data-original="#000000" style="" class=""/></g>
              </svg>
              <p>Data:</p>
            </div>
            <div v-else-if="informacoes.cardType === 'EVALUATION'" class="timeline__header__div">
              <svg class="timeline__icon" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:svgjs="http://svgjs.com/svgjs" version="1.1" width="512" height="512" x="0" y="0" viewBox="0 0 511.999 511.999" style="enable-background:new 0 0 512 512" xml:space="preserve">
                        <g xmlns="http://www.w3.org/2000/svg">
                          <g>
                            <path d="M438.09,273.32h-39.596c4.036,11.05,6.241,22.975,6.241,35.404v149.65c0,5.182-0.902,10.156-2.543,14.782h65.461    c24.453,0,44.346-19.894,44.346-44.346v-81.581C512,306.476,478.844,273.32,438.09,273.32z" fill="#5f6772" data-original="#000000" style=""/>
                          </g>
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                          <g>
                            <path d="M107.265,308.725c0-12.43,2.205-24.354,6.241-35.404H73.91c-40.754,0-73.91,33.156-73.91,73.91v81.581    c0,24.452,19.893,44.346,44.346,44.346h65.462c-1.641-4.628-2.543-9.601-2.543-14.783V308.725z" fill="#5f6772" data-original="#000000" style=""/>
                          </g>
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                          <g>
                            <path d="M301.261,234.815h-90.522c-40.754,0-73.91,33.156-73.91,73.91v149.65c0,8.163,6.618,14.782,14.782,14.782h208.778    c8.164,0,14.782-6.618,14.782-14.782v-149.65C375.171,267.971,342.015,234.815,301.261,234.815z" fill="#5f6772" data-original="#000000" style=""/>
                          </g>
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                          <g>
                            <path d="M256,38.84c-49.012,0-88.886,39.874-88.886,88.887c0,33.245,18.349,62.28,45.447,77.524    c12.853,7.23,27.671,11.362,43.439,11.362c15.768,0,30.586-4.132,43.439-11.362c27.099-15.244,45.447-44.28,45.447-77.524    C344.886,78.715,305.012,38.84,256,38.84z" fill="#5f6772" data-original="#000000" style=""/>
                          </g>
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                          <g>
                            <path d="M99.918,121.689c-36.655,0-66.475,29.82-66.475,66.475c0,36.655,29.82,66.475,66.475,66.475    c9.298,0,18.152-1.926,26.195-5.388c13.906-5.987,25.372-16.585,32.467-29.86c4.98-9.317,7.813-19.946,7.813-31.227    C166.393,151.51,136.573,121.689,99.918,121.689z" fill="#5f6772" data-original="#000000" style=""/>
                          </g>
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                          <g>
                            <path d="M412.082,121.689c-36.655,0-66.475,29.82-66.475,66.475c0,11.282,2.833,21.911,7.813,31.227    c7.095,13.276,18.561,23.874,32.467,29.86c8.043,3.462,16.897,5.388,26.195,5.388c36.655,0,66.475-29.82,66.475-66.475    C478.557,151.509,448.737,121.689,412.082,121.689z" fill="#5f6772" data-original="#000000" style=""/>
                          </g>
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
                        <g xmlns="http://www.w3.org/2000/svg">
                        </g>
              </svg>
             <p>Data:</p>
            </div>
            <div v-else class="timeline__header__div">
              <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:svgjs="http://svgjs.com/svgjs" version="1.1" width="512" height="512" x="0" y="0" viewBox="0 0 438.529 438.529" style="enable-background:new 0 0 512 512" xml:space="preserve" class="timeline__icon"><g>
                      <g xmlns="http://www.w3.org/2000/svg">
                        <path d="M421.833,285.36c-2.573-9.801-8.233-17.179-16.991-22.128l-75.944-43.966l75.944-43.968   c8.758-4.949,14.421-12.322,16.991-22.126c2.566-9.803,1.379-19.082-3.572-27.836L399.99,93.932   c-4.948-8.757-12.319-14.419-22.127-16.989c-9.802-2.565-19.072-1.376-27.833,3.576l-75.944,43.677v-87.65   c0-9.899-3.621-18.464-10.855-25.697C256,3.616,247.433,0,237.537,0h-36.54c-9.9,0-18.464,3.619-25.697,10.849   c-7.232,7.232-10.85,15.798-10.85,25.697v87.65l-75.945-43.68c-8.757-4.952-18.036-6.145-27.837-3.576   c-9.803,2.573-17.179,8.232-22.128,16.989l-18.271,31.405c-4.952,8.754-6.14,18.033-3.571,27.836   c2.574,9.801,8.232,17.178,16.989,22.126l75.945,43.972l-75.945,43.966c-8.757,4.949-14.419,12.323-16.989,22.128   c-2.568,9.801-1.377,19.075,3.571,27.829l18.272,31.408c4.947,8.761,12.32,14.421,22.126,16.995   c9.805,2.562,19.08,1.375,27.837-3.58l75.945-43.681v87.655c0,9.891,3.617,18.466,10.85,25.694   c7.233,7.234,15.8,10.848,25.697,10.848h36.54c9.896,0,18.466-3.613,25.693-10.848c7.238-7.229,10.855-15.804,10.855-25.694   v-87.648l75.944,43.681c8.761,4.948,18.031,6.143,27.833,3.573c9.804-2.574,17.179-8.23,22.127-16.991l18.271-31.405   C423.212,304.438,424.4,295.161,421.833,285.36z" fill="#03a046" data-original="#000000" style=""/>
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      <g xmlns="http://www.w3.org/2000/svg">
                      </g>
                      </g>
              </svg>
              <p>Data:</p>
            </div>
          </md-card-header>
          <md-card-content v-bind="info" :key="info" class="timeline__content">
            <section class="timeline__section">
              <p class="timeline__titulo">Tipo</p>
              <p class="timeline__texto">{{ lorem }}</p>
            </section>
            <section class="timeline__section">
              <p class="timeline__titulo">Status</p>
              <p v-if="informacoes.status === 'PENDING'" class="timeline__status--pendente">
                Pendente
              </p>
              <p class="timeline__status--null" v-else>
               Aguarde
              </p>
            </section>
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
      info: null,
      lorem: 'Lorem ipsum dolor sit amet'
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
.timeline__header__div{
  display:flex;
  flex-direction: column;
  align-items: center;
}
.timeline__ripple{
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}
.timeline__content{
  display:flex;
  flex-direction: column;
}

.timeline__icon{
  width:30%;
  height:auto;
  background-color: #ecf8f8;
  border-radius: 100%;
  padding: 1rem;
}
.timeline__titulo{
  color: #d0d3d6;
  font-size: 12px;
  text-transform: uppercase;
}
.timeline__texto{
  color:#545b64;
  font-size:20px;
  font-weight: 700;
}
.timeline__status--pendente{
  color: white;
  font-weight: 700;
  padding: 0 1rem;
  border-radius: 30px;
  border: solid 3px yellow;
  background-color: #EDC911;
  width: 50%;
  text-align: center;
}
.timeline__status--null{
  color: black;
  font-weight: 700;
  padding: 0 1rem;
  border-radius: 30px;
  border: solid 3px grey;
  background-color: lightgrey;
  width: 50%;
  text-align: center;
}
@media(min-width:768px){
  .timeline__ripple{
    flex-direction: row;
  }
  .timeline__icon{
    width:20%;
  }
  .timeline__content{
  flex-direction: row;
  }
  .timeline__header__div{
    align-items: flex-start;
  }
  .timeline__status--pendente, .timeline__status--null{
    width:100%;
  }
  .timeline__section{
    padding: 0 1rem;
    margin-top: 10px;
  }
}
</style>
