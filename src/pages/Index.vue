<template>
  <q-page class="">
    <div class="q-pa-md">
      <div class="q-gutter-md">
        <q-input filled v-model="codigo" label="Codigo" />
        <q-input outlined v-model="description" label="Descrição" />
      </div>

      <div class="q-gutter-md">
        <q-btn
          color="purple"
          label="Enviar"
          @click="adicionarCompromisso"
          style="margin:25px auto; display: block;"
        />
      </div>
    </div>
    <q-item
      clickable
      v-ripple
      v-for="(compromisso, index) in listaCompromisso"
      :key="index"
    >
      <q-item-section>
        <q-item-label
          >{{ compromisso.codigo }} -
          {{ compromisso.description }}</q-item-label
        >
        <q-btn
          color="red"
          label="Excluir"
          icon="delete"
          @click="deleteCompromisso(index)"
          style="margin:25px auto; display: block;"
        />
      </q-item-section>
    </q-item>
  </q-page>
</template>

<script>
import axios from 'boot/axios'

export default {
  name: "PageIndex",
 
  data () {
    return {
      codigo: '',
      description: '',
      listaCompromisso: [
        {codigo: 1, description: 'Aula'},
        {codigo: 2,description: 'Natação'}
      ]
    }
  },
  methods: {
    adicionarCompromisso() {
      this.listaCompromisso.push({
       codigo: this.codigo,
       description: this.description });
      this.codigo = ''
      this.description = ''
    },
    deleteCompromisso (index) {
      this.$q.dialog({
        title: 'deletar',
        message: 'Deseja excluir?',
        cancel: true,
        persistent: true
      }).onOk(() => {
        this.listaCompromisso.splice(index, 1)
        this.$q.notify({
        message: 'Tarefa excluida',
        color: 'green'
      })
      }).onCancel(() => {
      })
    },

     
    }
  }
</script>
