<template>
  <q-page class="flex">
    <div class="q-pa-md all-width">
      <q-table
        title="Movimientos Open Items"
        :data="data"
        :columns="columns"
        row-key="openItem"
        :pagination.sync="pagination"
      />
    </div>
  </q-page>
</template>
<style>
</style>

<script>
export default {
  name: 'EECC',
  data () {
    return {
      poliza: '52467',
      pagination: {
        sortBy: 'openItem',
        descending: false,
        rowsPerPage: 5
      },
      columns: [
        {
          name: 'tipoItem',
          align: 'center',
          label: 'Tipo',
          field: 'tipoItem',
          sortable: true
        },
        {
          name: 'openItem',
          align: 'center',
          label: 'OpenItem',
          field: 'openItem',
          sortable: true
        },
        {
          name: 'inicioCobertura',
          label: 'Inicio Cobertura',
          field: 'inicioCobertura',
          sortable: true
        },
        {
          name: 'finCobertura',
          label: 'Fin Cobertura',
          field: 'finCobertura',
          sortable: true
        },
        { name: 'saldo', label: 'Saldo', field: 'saldo' },
        { name: 'estado', label: 'Estado', field: 'estado' }
      ],
      data: [
        {
          tipoItem: 'Pago',
          openItem: '104643',
          inicioCobertura: '2019-01-10',
          finCobertura: '2025-01-10',
          saldo: 40000.0,
          estado: 'Vigente'
        },
        {
          tipoItem: 'Pago',
          openItem: '104687',
          inicioCobertura: '2019-01-10',
          finCobertura: '2025-01-10',
          saldo: 40000.0,
          estado: 'Vigente'
        }
      ]
    }
  }
}
</script>
