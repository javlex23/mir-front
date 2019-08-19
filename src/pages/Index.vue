<template>
  <q-page class="flex">
    <div class="q-pa-md all-width">
      <div class="row q-col-gutter-xs">
        <div class="col-md-6 col-xs-12">
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Contratante" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{contratante}}</div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Documento" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{contratante_tipo_documento}} {{contratante_numero_documento}}</div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Dirección" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{contratante_direccion}}</div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Asegurado" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{asegurado}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Documento" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{asegurado_tipo_documento}} {{asegurado_numero_documento}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Fecha nacimiento" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{asegurado_fecha_nacimiento}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Edad actual" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{asegurado_edad_actual}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Edad actuarial" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{asegurado_edad_actuarial}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Sexo" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{asegurado_sexo}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Email" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{asegurado_email}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Dirección" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{asegurado_direccion}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Teléfono" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{asegurado_telefono}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Producto" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_producto}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Plan" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_plan}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Fecha emisión" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_fecha_emision}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Moneda" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_moneda}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Prima forma pago" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_forma_pago}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Prima neta" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_prima_neta}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Prima mínima" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_prima_minima}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Inicio vigencia" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_inicio_vigencia}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Fin vigencia" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_fin_vigencia}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Pagado hasta" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_pagado_hasta}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Descuento" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_descuento}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Cuotas por cobrar" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_cuotas_cobrar}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Monto por cobrar" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_monto_cobrar}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Préstamo pendiente" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_prestamo_pendiente}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Amortizado" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_amortizado}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Cesionado a" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_cesionado_a}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Monto cesión" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_monto_cesion}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Frecuencia de pago" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_frecuencia_pago}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Periodo pago prima" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_periodo_pago_prima}} </div>
                </template>
              </q-field>
            </div>
            <div class="col-md-6 col-xs-12">
              <q-field label="Periodo pago beneficio" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_periodo_pago_beneficio}} </div>
                </template>
              </q-field>
            </div>
          </div>
          <div class="row q-col-gutter-xs">
            <div class="col-md-6 col-xs-12">
              <q-field label="Canal venta" stack-label :dense="dense" disable readonly>
                <template v-slot:control>
                  <div class="self-center full-width no-outline" tabindex="0">{{poliza_canal_venta}} </div>
                </template>
              </q-field>
            </div>
          </div>
        </div>
        <div class="col-md-6 col-xs-12" style="padding-left: 25px;">
          <div class="row">
            <div class="col-md-4 col-xs-6">
              <q-knob
                readonly
                v-model="cuota_utilizada"
                show-value
                size="90px"
                :thickness="0.22"
                color="orange"
                track-color="orange-3"
                class="text-orange q-ma-md"
              />
            </div>
            <div class="col-md-4 col-xs-6">
              <q-knob
                readonly
                v-model="comodin_disponible"
                show-value
                size="90px"
                :thickness="0.22"
                color="green"
                track-color="green-3"
                class="text-green q-ma-md"
              />
            </div>
          </div>
          <div class="row">
            <div class="col-md-4 col-xs-6">
              <span>&nbsp;&nbsp;<strong>Cuotas utilizadas</strong></span>
            </div>
            <div class="col-md-4 col-xs-6">
              <span><strong>Comodín disponibles</strong></span>
            </div>
          </div>
          <q-timeline color="secondary">
            <q-timeline-entry heading>
              Historial pagos
            </q-timeline-entry>

            <q-timeline-entry
              title="Pagó atrasado"
              subtitle="Abril 01, 2019"
              color="orange"
              icon="done_all"
            >
              <div class="q-timeline-content">
                Cuota con vigencia 2019-04-01 al 2019-04-30, saldo: S/.35,000.00.
              </div>
            </q-timeline-entry>
            <q-timeline-entry
              title="Pagó a la fecha"
              subtitle="Mayo 01, 2019"
              color="green"
              icon="done_all"
            >
              <div class="q-timeline-content">
                Cuota con vigencia 2019-05-01 al 2019-05-31, saldo: S/.35,000.00.
              </div>
            </q-timeline-entry>
            <q-timeline-entry
              title="Pagó la fecha"
              subtitle="Junio 01, 2019"
              color="green"
              icon="done_all"
            >
              <div class="q-timeline-content">
                Cuota con vigencia 2019-06-01 al 2019-06-30, saldo: S/.35,000.00.
              </div>
            </q-timeline-entry>
            <q-timeline-entry
              title="Pagó atrasado"
              subtitle="Julio 01, 2019"
              color="red"
              icon="done_all"
            >
              <div class="q-timeline-content">
                Cuota con vigencia 2019-07-01 al 2019-07-27, saldo: S/.35,000.00.
              </div>
            </q-timeline-entry>
            <q-timeline-entry
              title="Pagó atrasado"
              subtitle="Agosto 01, 2019"
              color="orange"
              icon="done_all"
            >
              <div class="q-timeline-content">
                Cuota con vigencia 2019-08-01 al 2019-08-30, saldo: S/.35,000.00.
              </div>
            </q-timeline-entry>
          </q-timeline>
        </div>
      </div>
    </div>
  </q-page>
</template>

<style>
</style>

<script>
export default {
  name: 'Poliza',
  data () {
    return {
      contratante: 'Karla Mónica Culquitante Abanto',
      contratante_tipo_documento: 'DNI',
      contratante_numero_documento: '19193790',
      contratante_direccion: 'Javier Prado Este 4440',
      asegurado: 'Antonio Alejandro Crispin Culquitante',
      asegurado_tipo_documento: 'DNI',
      asegurado_numero_documento: '44718485',
      asegurado_fecha_nacimiento: '23-11-1988',
      asegurado_edad_actual: '30',
      asegurado_edad_actuarial: '30',
      asegurado_sexo: 'Masculino',
      asegurado_email: 'aacc@gmail.com',
      asegurado_direccion: 'Javier Prado Este 4440',
      asegurado_telefono: '949505521',
      poliza_producto: 'Dotal Simple',
      poliza_plan: 'Dotal Simple',
      poliza_fecha_emision: '2019-02-12',
      poliza_moneda: 'Soles',
      poliza_forma_pago: 'S/.78.13',
      poliza_prima_neta: 'S/.78.13',
      poliza_prima_minima: 'S/.78.13',
      poliza_inicio_vigencia: '2019-03-01',
      poliza_pagado_hasta: '2019-08-01',
      poliza_cuotas_cobrar: '48',
      poliza_prestamo_pendiente: '-',
      poliza_cesionado_a: '-',
      poliza_frecuencia_pago: 'Mensual',
      poliza_periodo_pago_prima: '1',
      poliza_canal_venta: 'Facebook',
      dense: false,
      cuota_utilizada: 2,
      comodin_disponible: 3
    }
  }
}
</script>
