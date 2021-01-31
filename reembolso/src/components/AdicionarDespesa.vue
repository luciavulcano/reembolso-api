<template>
  <div>
    <button @click="openModal()" class="modal__button">Adicionar despesa</button>
    <transition name="fade">
    <div class="modal" v-if="show">
      <div class="modal__backdrop" @click="closeModal()"/>
      <div class="modal__dialog">
        <button type="button" class="modal__close" @click="closeModal()">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 352 512">
            <path
              fill="currentColor"
                d="M242.72 256l100.07-100.07c12.28-12.28 12.28-32.19 0-44.48l-22.24-22.24c-12.28-12.28-32.19-12.28-44.48 0L176 189.28 75.93 89.21c-12.28-12.28-32.19-12.28-44.48 0L9.21 111.45c-12.28 12.28-12.28 32.19 0 44.48L109.28 256 9.21 356.07c-12.28 12.28-12.28 32.19 0 44.48l22.24 22.24c12.28 12.28 32.2 12.28 44.48 0L176 322.72l100.07 100.07c12.28 12.28 32.2 12.28 44.48 0l22.24-22.24c12.28-12.28 12.28-32.19 0-44.48L242.72 256z"
              ></path>
          </svg>
        </button>
        <div class="modal__content">
          <section class="modal__arquivo">
            <h2>Envie o comprovante</h2>
            <p>
              Você pode inserir arquivos nos formatos PNG, JPG ou PDF. Tamanho máx:10MB
            </p>
            <md-field>
              <md-file v-model="placeholder" placeholder="Escolher arquivo" class="modal__arquivo__input" />
            </md-field>
          </section>
          <section class="modal__form">
            <div class="md-layout md-gutter">
              <div class="md-layout-item">
                <section class="modal__form__um">
                  <md-field class="modal__form__field">
                    <h3 for="tipo">Tipo*</h3>
                    <md-select v-model="tipo" name="tipo" id="tipo" placeholder="Tipo" class="modal__form__input">
                      <md-option value="Tipo">Tipo</md-option>
                    </md-select>
                  </md-field>
                  <md-field class="modal__form__field">
                    <h3 for="moeda">Moeda*</h3>
                    <md-select v-model="moeda" name="moeda" id="moeda" placeholder="Moeda" class="modal__form__input">
                      <md-option value="Moeda">Moeda</md-option>
                    </md-select>
                  </md-field>
                </section>
                <section class="modal__form__dois">
                  <md-field class="modal__form__field">
                    <h3 for="descricao">Descrição da despesa*</h3>
                    <md-select v-model="descricao" name="descricao" id="descricao" placeholder="Descrição da despesa" class="modal__form__input">
                      <md-option value="Descrição">Descrição</md-option>
                    </md-select>
                  </md-field>
                  <md-field class="modal__form__field">
                    <h3 for="data">Data*</h3>
                    <md-datepicker v-model="selectedDate" placeholder="Selecione a data" class="modal__form__input" />
                      <md-option value="Data">Data</md-option>
                  </md-field>
                </section>
              </div>
            </div>
          </section>
        </div>
        <md-dialog-actions>
          <md-button class="modal__botao--cancelar" @click="showDialog = false">Cancelar</md-button>
          <md-button class="modal__botao--salvar" @click="showDialog = false">Salvar</md-button>
        </md-dialog-actions>
      </div>
    </div>
  </transition>
  </div>
</template>

<script>
export default {
  name: 'AdicionarDespesas',
  data () {
    return {
      show: false,
      showDialog: false,
      selectedDate: null,
      placeholder: null
    }
  },
  methods: {
    closeModal () {
      this.show = false
      document.querySelector('body').classList.remove('overflow-hidden')
    },
    openModal () {
      this.show = true
      document.querySelector('body').classList.add('overflow-hidden')
    }
  }
}
</script>
<style scoped>
.modal {
  overflow-x: hidden;
  overflow-y: auto;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 9;
}
.modal__backdrop {
  background-color: rgba(0, 0, 0, 0.3);
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1;
}
.modal__dialog{
  background-color: #ffffff;
  position: relative;
  margin: 50px auto;
  display: flex;
  flex-direction: column;
  border-radius: 5px;
  z-index: 2;
  width: 300px;
}
.modal__close {
  width: 30px;
  height: 30px;
  border: none;
  background-color: white;
  margin: 1rem;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.modal__button{
  background-color: white;
  border: solid 1px;
  border-radius: 5px;
  padding: .5rem 1rem;
  margin: 1rem;
}
.modal__arquivo{
  display: flex;
  flex-direction: column;
  align-content: center;
  border: solid 1px;
  border-radius: 5px;
  padding: .5rem 1rem;
  margin: 1rem;
  background-color: #f4f6fa;
  text-align: center;
}
.modal__arquivo__input{
  align-self: center;
}
.modal__form{
  padding: 1rem;
}
.modal__form__um{
  display: flex;
  flex-direction: column;
}
.modal__form__dois{
  width: 50%;
}
.modal__form__input{
  border: solid 1px;
  margin: 0 .5rem;
  border-radius: 5px;
  padding-left: .5rem;
}
.modal__form__field{
  display: flex;
  flex-direction: column;
  margin:0;
}
.md-datepicker-body {
  background-color: whitesmoke;
}
.modal__botao--salvar{
  background-color: #00c5fc;
  border-radius: 5px;
  color: white;
  text-transform: capitalize;
}
.modal__botao--cancelar{
  border-radius: 5px;
  border: solid 1px;
  text-transform: capitalize;
}

@media (min-width: 768px){
  .modal__dialog{
    width: 600px;
  }
  .modal__form__um{
    flex-direction: row;
  }
}
</style>
