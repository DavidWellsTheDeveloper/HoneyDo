<template>
  <v-container grid-list-xs class="my-5">
    <v-row no-gutters>
      <v-col>
        <v-parallax v-if="isParallax" :src="src"></v-parallax>
      </v-col>
    </v-row>
    <v-card :dark="dark" :color="color" class="px-5 py-5">
      <v-row>
        <v-col cols="4" class="text-center" :order="invertAlign ? 12 : 4" :color="color">
          <v-icon x-large>mdi-bee</v-icon>
        </v-col>
        <v-col cols="8" class="text-left" :order="invertAlign ? 4 : 12">
          <slot></slot>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<script>
  export default {
    props: {
      isParallax: {
        type: Boolean,
        default: true
      },
      dark: {
        type: Boolean,
        default: false
      },
      src: {
        type: String,
        default: ''
      },
      // Hex code for background
      color: {
        type: String,
        default: 'primary'
      },
      invertAlign: {
        type: Boolean,
        default: false
      }

    },
  }
</script>

<style lang="scss" scoped>

</style>