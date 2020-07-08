<template>
  <v-container>
    <v-btn small right v-on:click="play">播放</v-btn>
  </v-container>
</template>

<script>
import { Howl, Howler } from "howler";

export default {
  name: "HelloWorld",

  data: () => ({}),
  methods: {
    play: function() {
      var sound = new Howl({
        src: ["playlist/1.mp3"],
        html5: true,
        onload: function() {
          console.log(sound.duration());
        }
      });
      sound.play();
    }
  }
};
</script>
