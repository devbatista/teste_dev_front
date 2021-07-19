<template>
    <q-page class="container">
        <div class="row q-pa-md">
            <h4>Adicionar novo cliente</h4>
        </div>

        <div class="q-pa-md">
            <q-form action="http://localhost/api/cliente" method="post" class="q-gutter-md">
                <q-input filled outlined v-model="name" label="Nome" type="text" name="nome" />
                <q-input filled outlined v-model="email" label="Email" type="email" name="email" />
                <q-input filled outlined v-model="descricao" label="Descrição" type="textarea" name="descricao" />
                <q-input filled outlined v-model="tags" label="Palavras-chave" type="text" name="tags" />

                <div class="row">
                    <div class="col-6">
                        <q-btn color="primary" class="pull-left" type="submit" :loading="submitting">Enviar</q-btn>
                    </div>
                    <div class="col-6">
                        <q-btn color="black" class="float-right">Voltar</q-btn>
                    </div>
                </div>
            </q-form>
        </div>
    </q-page>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    return {
      name: ref(''),
      email: ref(''),
      descricao: ref(''),
      tags: ref('')
    }
  }
}
</script>
