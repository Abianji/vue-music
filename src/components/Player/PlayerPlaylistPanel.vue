<template>
  <v-card height="330">
    <v-list :disabled="disabled">
      <v-list-item-group color="primary">
        <v-list-item v-for="(track, index) in playlist" :key="track.title" v-show="track.display">
          <v-list-item-content>
            <v-list-item-title>{{ index }} {{ track.artist }} - {{ track.title }}</v-list-item-title>
          </v-list-item-content>
          <v-spacer></v-spacer>
          {{ track.howl.duration() }}
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-card>
</template>

<script>
export default {
  props: {
    playlist: Array
  },
  data: () => ({
    disabled: false
  })
};
</script>

<style>
</style>