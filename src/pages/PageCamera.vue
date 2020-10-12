<template>
  <q-page class="constrain-more q-pa-md">
    <div class="camera-frame q-pa-md">
      <img
        class="full-width"
        src="https://static2.oimenu.com.br/data/images/natal-rn.jpg?21052019"
      >
    </div>
    <div class="text-center q-pa-md">
      <q-btn
        color="grey-10"
        icon="eva-camera"
        size="lg"
        round
      />
    </div>

    <div class="row justify-center q-ma-md">
      <q-input
        v-model="post.caption"
        class="col col-sm-8"
        label="Capition"
        dense
      /></div>

    <div class="row justify-center q-ma-md">
      <q-input
        v-model="post.location"
        class="col col-sm-8"
        label="Location"
        dense
      >
        <template v-slot:append>
          <q-btn
            round
            dense
            flat
            icon="eva-pin-outline"
          />
        </template>
      </q-input>
    </div>

    <div class="row justify-center q-ma-md">
      <q-btn
        color="primary"
        label="POST IMAGE"
        icon-right="send"
        rounded
      />
    </div>
  </q-page>
</template>

<script>
import { uid } from 'quasar'
export default {
  name: 'PageCamera',
  data () {
    return {
      post: {
        id: uid(),
        caption: '',
        location: '',
        photo: null,
        date: Date.now()
      }
    }
  }
}
</script>

<style lang="sass">
  .camera-frame
    border: 2px solid $grey-10
    border-radius: 10px
</style>
