<template>
  <q-layout view="lHh Lpr fff">
    <q-header elevated class="bg-white text-grey-8" height-hint="64">
      <q-toolbar class="GPL__toolbar" style="height: 64px">
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
          icon="menu"
          class="q-mx-md"
        />

        <q-toolbar-title v-if="$q.screen.gt.sm" shrink class="row items-center no-wrap">
          <img src="statics/logo_interseguro.png">
          <span class="q-ml-sm">MIR</span>
        </q-toolbar-title>

        <q-space />

        <q-input class="GPL__toolbar-input" dense v-model="search" placeholder="Buscar" @keyup.enter="buscar">
          <template v-slot:prepend>
            <q-icon v-if="search === ''" name="search" />
            <q-icon v-else name="clear" class="cursor-pointer" @click="search = ''" />
          </template>
        </q-input>

        <!--<q-btn v-if="$q.screen.gt.xs" flat dense no-wrap color="primary" icon="add" no-caps label="Create" class="q-ml-sm q-px-md">
          <q-menu anchor="top right" self="top right">
            <q-list class="text-grey-8" style="min-width: 100px">
              <q-item aria-hidden="true">
                <q-item-section class="text-uppercase text-grey-7" style="font-size: 0.7rem">Create New</q-item-section>
              </q-item>
              <q-item v-for="menu in createMenu" :key="menu.text" clickable v-close-popup aria-hidden="true">
                <q-item-section avatar>
                  <q-icon :name="menu.icon" />
                </q-item-section>
                <q-item-section>{{ menu.text }}</q-item-section>
              </q-item>
            </q-list>
          </q-menu>
        </q-btn>

        <q-btn v-if="$q.screen.gt.xs" flat dense no-wrap color="primary" icon="cloud_upload" no-caps label="Upload" class="q-ml-sm q-px-md" />-->

        <q-space />

        <div class="q-gutter-sm row items-center no-wrap">
          <q-btn round dense flat color="text-grey-7" icon="apps">
            <q-tooltip>MIR Apps</q-tooltip>
          </q-btn>
          <q-btn round dense flat color="grey-8" icon="notifications">
            <q-badge color="red" text-color="white" floating>
              2
            </q-badge>
            <q-tooltip>Notifications</q-tooltip>
          </q-btn>
          <q-btn round flat>
            <q-avatar size="26px">
              <img src="https://cdn.quasar.dev/img/boy-avatar.png">
            </q-avatar>
            <q-tooltip>Account</q-tooltip>
          </q-btn>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      bordered
      behavior="mobile"
      @click="leftDrawerOpen = false"
    >
      <q-scroll-area class="fit">
        <q-toolbar class="GPL__toolbar">
          <q-toolbar-title class="row items-center text-grey-8">
            <img class="q-pl-md" src="statics/logo_interseguro.png">
            <span class="q-ml-sm">MIR</span>
          </q-toolbar-title>
        </q-toolbar>

        <q-list padding>
          <q-item v-for="link in links1" :key="link.text" clickable class="GPL__drawer-item">
            <q-item-section avatar>
              <q-icon :name="link.icon" />
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ link.text }}</q-item-label>
            </q-item-section>
          </q-item>

          <q-separator class="q-my-md" />

          <q-item v-for="link in links2" :key="link.text" clickable class="GPL__drawer-item">
            <q-item-section avatar>
              <q-icon :name="link.icon" />
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ link.text }}</q-item-label>
            </q-item-section>
          </q-item>

          <q-separator class="q-my-md" />

          <q-item v-for="link in links3" :key="link.text" clickable class="GPL__drawer-item">
            <q-item-section avatar>
              <q-icon :name="link.icon" />
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ link.text }}</q-item-label>
            </q-item-section>
          </q-item>

          <q-separator class="q-my-md" />

          <q-item clickable class="GPL__drawer-item GPL__drawer-item--storage">
            <q-item-section avatar>
              <q-icon name="cloud" />
            </q-item-section>
            <q-item-section top>
              <q-item-label>Storage</q-item-label>
              <q-linear-progress :value="storage" class="q-my-sm" />
              <q-item-label caption>2.6 GB of 15 GB</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </q-scroll-area>
    </q-drawer>

    <q-page-container class="GPL__page-container">
      <router-view />

      <q-page-sticky v-if="$q.screen.gt.sm" expand position="left">
        <div class="fit q-pt-xl q-px-sm column">
          <q-btn to="Index" round flat color="grey-8" stack no-caps size="26px" class="GPL__side-btn">
            <q-icon size="22px" name="markunread_mailbox" />
            <div class="GPL__side-btn__label">Póliza</div>
          </q-btn>

          <q-btn to="Eecc" round flat color="grey-8" stack no-caps size="26px" class="GPL__side-btn">
            <q-icon size="22px" name="dashboard" />
            <div class="GPL__side-btn__label">EECC</div>
          </q-btn>

          <q-btn to="Persona" round flat color="grey-8" stack no-caps size="26px" class="GPL__side-btn">
            <q-icon size="22px" name="perm_identity" />
            <div class="GPL__side-btn__label">Persona</div>
            <!--<q-badge floating color="red" text-color="white" style="top: 8px; right: 16px">
              1
            </q-badge>-->
          </q-btn>

          <q-btn round flat color="grey-8" stack no-caps size="26px" class="GPL__side-btn">
            <q-icon size="22px" name="flight_land" />
            <div class="GPL__side-btn__label">Siniestro</div>
          </q-btn>

        </div>

        <q-dialog v-model="bar" persistent>
          <q-card>
            <q-bar>
              <div>Resultados de búsqueda</div>

              <q-space />

              <q-btn dense flat icon="close" v-close-popup>
                <q-tooltip>Close</q-tooltip>
              </q-btn>
            </q-bar>

            <q-card-section>
              <div class="col-md-12 col-xs-12">
                <q-table
                  :grid="$q.screen.xs"
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
            </q-card-section>
          </q-card>
        </q-dialog>
      </q-page-sticky>
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: 'PolizaConsultasLayout',
  data () {
    return {
      leftDrawerOpen: false,
      search: '',
      storage: 0.26,
      bar: false,
      links1: [
        { icon: 'markunread_mailbox', text: 'Póliza' },
        { icon: 'dashboard', text: 'EECC' },
        { icon: 'perm_identity', text: 'Persona' },
        { icon: 'flight_land', text: 'Siniestros' }
      ],
      links2: [
        { icon: 'archive', text: 'Historial' },
        { icon: 'star', text: 'Favoritos' }
      ],
      links3: [
        { icon: 'settings', text: 'Configuración' },
        { icon: 'help', text: 'Acerca de' }
        // { icon: 'get_app', text: 'App Downloads' }
      ],
      createMenu: [
        { icon: 'photo_album', text: 'Album' },
        { icon: 'people', text: 'Shared Album' },
        { icon: 'movie', text: 'Movie' },
        { icon: 'library_books', text: 'Animation' },
        { icon: 'dashboard', text: 'Collage' },
        { icon: 'book', text: 'Photo book' }
      ],
      columns: [
        {
          name: 'numeroDocumento',
          align: 'center',
          label: 'Documento',
          field: 'numeroDocumento',
          sortable: true
        },
        {
          name: 'cliente',
          align: 'center',
          label: 'Cliente',
          field: 'cliente',
          sortable: true
        },
        {
          name: 'numeroPoliza',
          align: 'center',
          label: 'Número Póliza',
          field: 'numeroPoliza',
          sortable: true
        }
      ],
      data: [
        {
          numeroDocumento: '19197656',
          cliente: 'Karla Monica Culquitante Abanto',
          numeroPoliza: '104643'
        },
        {
          numeroDocumento: '19156787',
          cliente: 'Manuel Alonso Vargas Gutierrez',
          numeroPoliza: '104643'
        }
      ]
    }
  },
  methods: {
    buscar () {
      this.bar = true
    }
  }
}
</script>

<style lang="stylus">
.GPL
  &__toolbar
    height 64px
    background-color $interseguro
    color white
  &__toolbar-input
    width 35%
    background-color white
  &__drawer-item
    line-height 24px
    border-radius 0 24px 24px 0
    margin-right 12px
    .q-item__section--avatar
      padding-left 12px
      .q-icon
        color #5f6368
    .q-item__label:not(.q-item__label--caption)
      color #3c4043
      letter-spacing .01785714em
      font-size .875rem
      font-weight 500
      line-height 1.25rem
    &--storage
      border-radius 0
      margin-right 0
      padding-top 24px
      padding-bottom 24px
      display none
  &__side-btn
    &__label
      font-size 12px
      line-height 24px
      letter-spacing .01785714em
      font-weight 500
  @media (min-width 1024px)
    &__page-container
      padding-left 94px
</style>
