<template>
  <v-container>
    <h1 class="text-center">SERVICES</h1>
    <ServicesInspiration
      src="/parallaximg/nastuh-abootalebi-JdcJn85xD2k-unsplash.jpg"
      color="primary"
      title="I'll keep your home clean, and fresh"
    >
      <p>I'm confident that you'll love the cleaning service, so your first cleaning is 
        free of charge. After your first cleaning, we'll provide a quote for additional 
        regular cleaning services.</p>
    </ServicesInspiration>

    <ServicesInspiration
      src="/parallaximg/josh-hild-95RvuULh91A-unsplash.jpg"
      color="secondary"
      :invert-align="true"
      title="Have Pets? I'll watch them too!"
    >
      <p>I provide a full set of pet services so you can be sure that your pet is well 
        cared for while you're gone.</p>
      <dl>
        <dt>Pet Walking</dt>
        <dd>Rest assured that your pet is getting attiquite exercise.</dd>
        <dt>Dogs &amp; Cats</dt>
        <dd></dd>
        <dt>Daily Pet Updates</dt>
        <dd>Recieve a photo update daily to keep up to date with your pets.</dd>
      </dl>
    </ServicesInspiration>
    
    <ServicesInspiration
      src="/parallaximg/thomas-le-pRJhn4MbsMM-unsplash.jpg"
      color="primary"
      :invert-align="true"
      title="I'm happy to do grocery runs"
    >
      <p>Whether you forgot a few things last time you went, or if you just 
        want to come home to a stocked kitchen, I've got you covered.</p>
    </ServicesInspiration>
    <!-- <v-row>
      <v-col>
        <v-parallax src="/paralaximg/nastuh-abootalebi-JdcJn85xD2k-unsplash.jpg"></v-parallax>
      </v-col>
    </v-row> -->
  </v-container>
</template>

<script>
  export default {
    data() {
      return {
        slides: [
          'First',
          'Second',
          'Third',
          'Fourth',
          'Fifth',
        ],
      }
    },
  }
</script>

<style lang="scss" scoped>
dl {
  dt {
    font-weight: 600;
  }
  dd {
    font-style: italic;
    margin-left: 1em;
  }
}
h2 {
  margin-bottom: 20px;
}
</style>
