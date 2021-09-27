<template>
  <v-row justify="center" align="center">
    <v-col cols="12" lg="12">
      <v-card class="logo py-4 justify-center">
        <!-- <HoneyDoLogo /> -->
        <v-card-title class="headline">
          Welcome to the Honey Do's
          <blockquote class="blockquote">
            I can take care of all of the honey do tasks for you and your home.
            Here is a list of  some of the tasks I can do for you so you can 
            <v-icon color="primary" large>mdi-bee</v-icon> care free.
          </blockquote>
        </v-card-title>
        <v-card-text>
          <ul style="font-size: large; margin-left: 20px;">
            <li>House cleaning </li> 
            <li>Grocery shopping</li>
            <li>House sitting</li>
            <li>Pet sitting and pet care</li>
            <li>Dog walking</li>
            <li>Child care</li>
          </ul>
        </v-card-text>
        <v-card-actions>
          <v-spacer color="accent" />
          <v-btn
            color="primary"
            nuxt
            to="/services"
          >
            Services
          </v-btn>
        </v-card-actions>
        <v-card-text style="font-size: large;">
          View details about each of the services below:
        </v-card-text>
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
              <h3 class="my-4">{{ item.description }}</h3>
              <v-btn
                v-if="item.servicesId"
                :color="i % 2 == 0 ? 'primary': 'secondary'"
                class="mx-0"
                outlined
                type="link"
                :href="item.servicesId ? '/services#' + item.servicesId : ''"
              >
                See more
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
            description: 'Regular house cleaning services available including discounts when you start a weekly subscription.',
            servicesId: 'servicesClean',
          },
          {
            title: 'Deep House Cleaning',
            icon: 'mdi-star',
            description: 'For one time deep cleaning jobs we\'ll get the job done right, and take care leave your space fresh.',
          },
          {
            title: 'Office Cleaning',
            icon: 'mdi-office-building',
            description: 'Office spaces need regular cleaning to help your employees focus. Let us ensure your office space is clean and safe.',
          },
          {
            title: 'Linens',
            icon: 'mdi-hanger',
            description: 'We can take care of your regularly used towels and sheets. We\'re happy to service Air BnB\'s too.',
            
          },
          {
            title: 'Trial Cleaning',
            icon: 'mdi-alarm',
            description: 'First time cleanings are performed at a discounted hourly rate.',
          },
          {
            title: 'Pet Care',
            icon: 'mdi-paw',
            description: 'Allow us to ensure your pets are taken care of. Our experienced pet care professionals will feed, and walk your 4 legged friends.',
            servicesId: 'servicesPets',
          },
          {
            title: 'Child Care',
            icon: 'mdi-human-male-child',
            description: '',
            servicesId: 'servicesChildCare'
          },
          {
            title: 'Grocery Services',
            icon: 'mdi-cart-variant',
            description: '',
            servicesId: 'servicesGrocery',
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