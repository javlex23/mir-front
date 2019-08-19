<template>
  <q-page class="flex">
    <div class="q-pa-md all-width">
      <q-table
        title="Pólizas registradas"
        :data="data"
        :columns="columns"
        row-key="numeroPoliza"
        :pagination.sync="pagination"
      />
    </div>
  </q-page>
</template>
<style>
</style>

<script>
export default {
  name: 'Persona',
  data () {
    return {
      poliza: '52467',
      pagination: {
        sortBy: 'poliza',
        descending: false,
        rowsPerPage: 5
      },
      columns: [
        {
          name: 'numeroPoliza',
          align: 'center',
          label: 'Número Póliza',
          field: 'numeroPoliza',
          sortable: true
        },
        {
          name: 'rol',
          align: 'center',
          label: 'Rol',
          field: 'rol',
          sortable: true
        },
        {
          name: 'evento',
          label: 'Evento',
          field: 'evento',
          sortable: true
        },
        {
          name: 'estado',
          label: 'Estado',
          field: 'estado',
          sortable: true
        },
        { name: 'vigencia', label: 'Vigencia', field: 'vigencia' },
        { name: 'producto', label: 'Producto', field: 'producto', sortable: true },
        { name: 'frecuenciaPago', label: 'Frecuencia Pago', field: 'frecuenciaPago', sortable: true }
      ],
      data: [
        {
          numeroPoliza: '104643',
          rol: 'Contratante',
          evento: 'Pago',
          estado: 'Vigente',
          vigencia: 'Ene 2019 - Ene 2029',
          producto: 'Plan Garantizado',
          plan: 'Plan Garantizado',
          frecuenciaPago: 'Mensual'
        },
        {
          numeroPoliza: '105898',
          rol: 'Asegurado',
          evento: 'Pago',
          estado: 'Vigente',
          vigencia: 'Ene 2019 - Ene 2029',
          producto: 'Plan Garantizado',
          plan: 'Plan Garantizado',
          frecuenciaPago: 'Mensual'
        }
      ]
    }
  }
}
</script>
