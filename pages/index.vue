<template>
  <v-row justify="center" align="center">
    <v-col cols="12" lg="12">
      <v-card class="logo py-4 justify-center">
        <!-- <HoneyDoLogo /> -->
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
            to="/services"
          >
            Continue
          </v-btn>
        </v-card-actions>
      </v-card>
      <v-timeline
        align-top
        :dense="$vuetify.breakpoint.smAndDown"
      >
        <v-timeline-item
          v-for="(item, i) in timelineItems"
          :key="i"
          :color="i % 2 == 0 ? 'primary': 'secondary'"
          :icon="item.icon"
          fill-dot
        >
          <v-card
            :color="i % 2 == 0 ? 'primary': 'secondary'"
            dark
          >
            <v-card-title class="text-h6">
              {{ item.title }}
            </v-card-title>
            <v-card-text class="white text--primary">
              <p>Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.</p>
              <v-btn
                :color="i % 2 == 0 ? 'primary': 'secondary'"
                class="mx-0"
                outlined
              >
                Button
              </v-btn>
            </v-card-text>
          </v-card>
        </v-timeline-item>
      </v-timeline>
    </v-col>
  </v-row>
</template>

<script>
  export default {
    data() {
      return {
        // <li>house cleaning </li> 
        //     <li>grocery shopping</li>
        //     <li>house sitting</li>
        //     <li>pet sitting and pet care</li>
        //     <li>dog walking</li>
        //     <li>child care</li>
        timelineItems: [
          {
            title: 'Regular House Cleaning',
            icon: 'mdi-spray-bottle',
          },
          {
            title: 'Deep House Cleaning',
            icon: 'mdi-star',
          },
          {
            title: 'Office Cleaning',
            icon: 'mdi-office-building',
          },
          {
            title: 'Linens',
            icon: 'mdi-hanger',
          },
          {
            title: 'Trial Cleaning',
            icon: 'mdi-alarm',
          },
          {
            title: 'Pet Care',
            icon: 'mdi-paw',
          },
          {
            title: 'Child Care',
            icon: 'mdi-human-male-child',
          },
          {
            title: 'Grocery Services',
            icon: 'mdi-cart-variant',
          },
        ],
      }
    },
  }
</script>

<style lang="scss" scoped>
.v-card__text, .v-card__title {
  word-break: normal; /* maybe !important  */
}
</style>