<template>
  <v-row justify="center" align="center">
    <v-col cols="12" lg="8">
      <v-card class="logo py-4 d-flex justify-center">
        <!-- <NuxtLogo /> -->
        <HoneyDoLogo />
      </v-card>
      <v-card>
        <v-card-title class="headline">
          Welcome to the Honey Do's
          <blockquote class="blockquote">
            I can take care of all of the honey do tasks for you and your home.
            I'll happily take care of the following for you so you can <v-icon color="primary" large>mdi-bee</v-icon> care free.
          </blockquote>
        </v-card-title>
        <v-card-text>
          <ul>
            <li>house cleaning </li> 
            <li>grocery shopping</li>
            <li>house sitting</li>
            <li>pet sitting and pet care</li>
            <li>dog walking</li>
            <li>child care</li>
          </ul>
        </v-card-text>
        <v-card-actions>
          <v-spacer color="accent" />
          <v-btn
            color="primary"
            nuxt
            to="/inspire"
          >
            Continue
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
  export default {
    
  }
</script>

<style lang="scss" scoped>
.v-card__text, .v-card__title {
  word-break: normal; /* maybe !important  */
}
</style>