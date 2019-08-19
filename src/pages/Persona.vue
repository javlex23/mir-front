<template>
  <q-page class="flex">
    <div class="q-pa-md all-width">
      <div class="row q-col-gutter-xs">
        <div class="col-md-4 col-xs-12">
          <q-field label="Persona" stack-label :dense="dense">
            <template v-slot:control>
              <div class="self-center full-width no-outline" tabindex="0">{{persona}}</div>
            </template>
          </q-field>
        </div>
        <div class="col-md-2 col-xs-12">
          <q-field label="Documento Identidad" stack-label :dense="dense">
            <template v-slot:control>
              <div class="self-center full-width no-outline" tabindex="0">{{documento}}</div>
            </template>
          </q-field>
        </div>
      </div>
      <br>
      <div class="row q-col-gutter-xs">
        <div class="col-md-12 col-xs-12">
          <q-table
            :grid="$q.screen.xs"
            title="Pólizas registradas"
            :data="data"
            :columns="columns"
            row-key="numeroPoliza"
            :pagination.sync="pagination"
          >
            <template v-slot:body-cell-numeroPoliza="cellProperties">
              <q-td :props="cellProperties">
                <q-btn to="Index" outline color="purple" >{{ cellProperties.value }}</q-btn>
              </q-td>
            </template>
          </q-table>
        </div>
      </div>
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
      persona: 'Karla Mónica Culquitante Abanto',
      documento: 'DNI 19193790',
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
