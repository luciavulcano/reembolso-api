<template>
  <div>
    <md-dialog :md-active.sync="showDialog" class="dialog">
      <md-dialog-title>Adicionar Despesa</md-dialog-title>
      <md-tabs md-dynamic-height>
        
      </md-tabs>
      <md-dialog-actions>
          <md-button class="md-primary" @click="showDialog = false">Fechar</md-button>
          <md-button class="md-primary" @click="showDialog = false">Salvar</md-button>
        </md-dialog-actions>
      </md-dialog>
      <md-button class="md-primary md-raised" @click="showDialog = true">Adicionar despesa</md-button>
  </div>
</template>

<script>
export default {
  name: 'AdicionarDespesas',
  data () {
    return {
      showDialog: false
    }
  }
}
</script>
<style>
.dialog{
  backgroundcolor: white;
}
</style>
