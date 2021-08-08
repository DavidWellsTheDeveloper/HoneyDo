<template>
  <img
    alt="Honey Do Logo"
    src="/honeyDoLogoThick.svg"
    class="honeyDoLogo"
    :style="heightformatted"
  >
</template>

<script>
  export default {
    props: {
      height: {
        type: String,
        default: '180' 
      },
    },
    computed: {
      heightformatted() {
        return 'height: ' + this.height + 'px;' 
      }
    },
  }
</script>


<style>
.honeyDoLogo {
  transform: rotateY(560deg);
  animation: turn 3.5s ease-out forwards 1s;
  filter: drop-shadow( 3px 3px 2px rgba(0, 0, 0, .7));
}

@keyframes turn {
  100% {
    transform: rotateY(0deg);
  }
}
</style>
