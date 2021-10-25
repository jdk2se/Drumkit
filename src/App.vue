<template>
  <h1>Vue Drumkit</h1>
  <div class="keys">
    <Sound v-for="(sound, index) in keys" :letter="sound.letter" :audio="sound.audio" :key="index" />
  </div>
</template>

<script>
import Sound from './components/Sound';

export default {
  name: 'App',
  components: {
    Sound
  },
  data() {
    return {
      keys: [
        {
          name: 'boom',
          audio: require('./assets/sounds/boom.wav'),
          letter: 'A',
        },
        {
          name: 'clap',
          audio: require('./assets/sounds/clap.wav'),
          letter: 'S',
        },
        {
          name: 'hihat',
          audio: require('./assets/sounds/hihat.wav'),
          letter: 'D',
        },
        {
          name: 'kick',
          audio: require('./assets/sounds/kick.wav'),
          letter: 'F',
        }, {
          name: 'openhat',
          audio: require('./assets/sounds/openhat.wav'),
          letter: 'G',
        },
        {
          name: 'ride',
          audio: require('./assets/sounds/ride.wav'),
          letter: 'H',
        },
        {
          name: 'snare',
          audio: require('./assets/sounds/snare.wav'),
          letter: 'J',
        },
        {
          name: 'tink',
          audio: require('./assets/sounds/tink.wav'),
          letter: 'K',
        },
        {
          name: 'tom',
          audio: require('./assets/sounds/tom.wav'),
          letter: 'L',
        },
      ],
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.keys {
  display: flex;
  justify-content: space-around;
  max-width: 800px;
  margin: 0 auto;
}
</style>
