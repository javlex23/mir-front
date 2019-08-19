<template>
  <q-page class="flex">
    <div class="q-pa-md all-width">
      <div class="row q-col-gutter-xs">
        <div class="col-md-3 col-xs-12">
          <q-field label="Póliza" stack-label :dense="dense">
            <template v-slot:control>
              <div class="self-center full-width no-outline" tabindex="0">{{poliza}}</div>
            </template>
          </q-field>
        </div>
        <div class="col-md-3 col-xs-12">
          <q-field label="Último evento" stack-label :dense="dense">
            <template v-slot:control>
              <div class="self-center full-width no-outline" tabindex="0">{{ultimo_evento}}</div>
            </template>
          </q-field>
        </div>
        <div class="col-md-3 col-xs-12">
          <q-field label="Estado" stack-label :dense="dense">
            <template v-slot:control>
              <div class="self-center full-width no-outline" tabindex="0">{{estado}}</div>
            </template>
          </q-field>
        </div>
      </div>
      <br>
      <div class="row q-col-gutter-xs">
        <div class="col-md-12 col-xs-12">
          <q-table
            :grid="$q.screen.xs"
            title="Movimientos Open Items"
            :data="data"
            :columns="columns"
            row-key="openItem"
            :pagination.sync="pagination"
          />
        </div>
      </div>
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
      ultimo_evento: 'Pago',
      estado: 'Vigente',
      dense: false,
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
