<template>
  <v-container fluid class="my-0">
    <v-row class="flush-row" no-gutters>
      <v-col>
        <v-parallax v-if="isParallax" :src="src"></v-parallax>
      </v-col>
    </v-row>
    <v-row class="my-0">
      <v-col cols="12" class="text-left py-0">
        <v-card :dark="dark" :color="color" class="py-0">
          <v-card-title primary-title>
            {{ title }}
          </v-card-title>
          <v-card-text>
            <slot></slot>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
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
      title: {
        type: String,
        default: ''
      }

    },
  }
</script>

<style lang="scss" scoped>
.flush-row {
  margin: 0px;
  padding: 0px;
}
</style>
