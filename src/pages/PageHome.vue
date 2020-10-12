<template>
  <q-page class="constrain q-pa-md">

    <div class="row q-col-gutter-lg">
      <div class="col-12 col-md-8">

        <q-card
          v-for="post in posts"
          :key="post.id"
          class="card-post q-mb-md"
          flat
          bordered
        >
          <q-item>
            <q-item-section avatar>
              <q-avatar>
                <img src="~assets/photos/photo (1).jpg">
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label class="text-bold">Daniel Levino</q-item-label>
              <q-item-label caption>
                {{post.location}}
              </q-item-label>
            </q-item-section>
          </q-item>

          <q-separator />

          <img class="q-img" :src="post.imageUrl">

          <q-card-section>
            <div>{{post.caption}}</div>
            <div class="text-caption text-grey">{{post.date | niceDate}}</div>
          </q-card-section>

        </q-card>

      </div>
      <div class="col-4 x-large-screen-only">
        <q-item class="fixed">
          <q-item-section avatar>
            <q-avatar size="48px">
              <img src="~assets/photos/photo (1).jpg">
            </q-avatar>
          </q-item-section>

          <q-item-section>
            <q-item-label class="text-bold">
              daniel.levino
            </q-item-label>
            <q-item-label caption>
              Daniel Levino
            </q-item-label>
          </q-item-section>
        </q-item>
      </div>
    </div>

  </q-page>
</template>

<script>
import { date } from "quasar"
export default {
  name: 'PageName',
  data () {
    return {
      posts: [
        {
          id: 1,
          caption: "Gonden Gate Bridge",
          date: 1502020768106,
          location: "San Francisco, United States",
          imageUrl: "https://cdn.quasar.dev/img/parallax2.jpg"
        },
        {
          id: 2,
          caption: "Bilola de Brennand",
          date: 1572520768006,
          location: "Recife, Brasil",
          imageUrl: "https://upload.wikimedia.org/wikipedia/commons/e/e6/Torre_de_Cristal_-_Recife-PE%282%29.jpg"
        },
        {
          id: 3,
          caption: "Morro do Careca",
          date: 1582520068106,
          location: "Natal, Brasil",
          imageUrl: "https://static2.oimenu.com.br/data/images/natal-rn.jpg?21052019"
        },
        {
          id: 4,
          caption: "Cristo Redentor",
          date: 1592520708106,
          location: "Rio de Janeiro, Brasil",
          imageUrl: "https://ogimg.infoglobo.com.br/in/13459524-bc0-ea3/FT1086A/652/cristo-redentor-fernando-quevedo.jpg"
        }
      ]
    }
  },
  filters: {
    niceDate(value) {
      return date.formatDate(value, 'MMMM D HH:mm')
    }
  }
}

</script>

<style lang="sass">
  .q-card
    .q-img
      min-height: 200px
</style>
