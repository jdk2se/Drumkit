<template>
  <div :class="`letter ${clicked ? 'active': ''}`" @click="play">
    {{ letter }}
  </div>
</template>

<script>
export default {
  name: "Sound",
  props: ['letter', 'audio'],
  data() {
    return {
      clicked: false,
    };
  },
  methods: {
    play() {
      if (false === this.clicked) {
        new Audio(this.audio).play();
        this.clicked = true;

        setTimeout(() => {
          this.clicked = false;
        }, 200);
      }
    }
  },
  mounted() {
    document.addEventListener('keydown', (e) => {
      if (e.key.toLowerCase() === this.letter.toLowerCase()) {
        this.play();
      }
    });
  },
}
</script>

<style scoped>
.letter {
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
  width: 40px;
  height: 40px;
  border-radius: 8px;
  background-color: #bd1047;
  cursor: pointer;
}

.active {
  border: 1px solid #651be3;
}
</style>
