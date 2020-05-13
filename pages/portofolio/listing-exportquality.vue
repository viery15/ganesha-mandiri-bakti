<template>
  <v-sheet>
    <v-card flat="" height="88" color="grey lighten-3">
      <v-container>
        <v-row class="ma-3">
          <div class="title font-weight-light">
            Export Quality
          </div>
          <v-spacer />
          <div class="caption">
            <span class="font-weight-light">
              You are here:
            </span>
            <span>Home</span>
            >
            <span>Portofolio</span>
            >
            <span class="font-weight-light">EXport Quality</span>
          </div>
        </v-row>
      </v-container>
    </v-card>
    <v-card>
      <v-container>
        <v-row>
          <v-col cols="12" md="8" sm="6">
            <v-card flat="">
              <v-carousel
                id="slider"
                :height="$vuetify.breakpoint.mdAndDown ? '200' : '400'"
                cycle=""
                :interval="12000"
                progress=""
              >
                <v-carousel-item
                  v-for="(slider, i) in carouselItem"
                  :key="`slider_${i}`"
                  :src="slider.image"
                  alt="Ganesha Bakti Mandiri"
                >
                </v-carousel-item>
              </v-carousel>
            </v-card>
          </v-col>
          <v-col cols="12" md="4" sm="6">
            <div class="title mb-3 font-weight-bold">
              Product Description
            </div>
            <div class="body-2 font-weigt-light">
              We also providing various origin of coffee bean around Indonesia,
              We give our best services and quality of products and strive to
              International market.
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
  </v-sheet>
</template>

<script>
export default {
  data() {
    return {
      carouselItem: [
        { image: '/img/exportquality-01.jpg' },
        { image: '/img/exportquality-02.jpg' }
      ]
    }
  }
}
</script>
