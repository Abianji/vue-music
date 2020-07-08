<template>
  <div>
    <PlayerTitleBar></PlayerTitleBar>
    <PlayerPlaylistPanel :playlist="playlist"></PlayerPlaylistPanel>
  </div>
</template>

<script>
import { Howl, Howler } from "howler";

import PlayerTitleBar from "../components/Player/PlayerTitleBar";
import PlayerPlaylistPanel from "../components/Player/PlayerPlaylistPanel";

export default {
  components: {
    PlayerTitleBar,
    PlayerPlaylistPanel
  },
  data: () => ({
    playlist: [
      {
        title: "1",
        artist: "Ask Again",
        howl: null,
        display: true
      },
      {
        title: "2",
        artist: "Ask Again",
        howl: null,
        display: true
      },
      {
        title: "3",
        artist: "Ask Again",
        howl: null,
        display: true
      },
      {
        title: "4",
        artist: "Ask Again",
        howl: null,
        display: true
      },
      {
        title: "5",
        artist: "Ask Again",
        howl: null,
        display: true
      },
      {
        title: "6",
        artist: "Ask Again",
        howl: null,
        display: true
      },
      {
        title: "7",
        artist: "Ask Again",
        howl: null,
        display: true
      }
    ]
  }),
  created: function() {
    Howler.autoUnlock = false;
    this.playlist.forEach(track => {
      track.howl = new Howl({
        src: ["playlist/${track.title}.mp3"],
        html5: true,
        format: ["mp3"]
      });
      console.log(track.howl.duration());
    });
  }
};
</script>

<style>
</style>