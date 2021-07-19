<template>
  <q-page class="container">
    <div class="row q-mt-md">
      <div class="col">
        <q-btn color="primary">Criar novo</q-btn>
      </div>
    </div>
    <div class="row q-mt-md">
      <div class="col">
        <q-table
          class="q-mt-md"
          title="Clientes"
          no-data-label="Sem registros"
          :columns="columns"
        />
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

const columns = [
  {
    name: 'cliente',
    label: 'cliente',
    align: 'left',
    field: 'cliente'
  },
  {
    name: 'email',
    label: 'email',
    align: 'left',
    field: 'email'
  },
  {
    name: 'ações',
    label: 'ações',
    align: 'left',
    field: 'acoes'
  }
]

export default defineComponent({
  name: 'Data',
  data () {
    return {
      data: []
    }
  },
  mounted () {
    this.getData()
  },
  methods: {
    getData () {
      this.$axios.get('http://localhost/api/clientes')
        .then((res) => {
          this.data = res.data
          console.log('POSTS', res.data)
        })
        .catch((err) => {
          console.error(err)
        })
    }
  },
  setup () {
    return {
      columns
    }
  }
})
</script>
