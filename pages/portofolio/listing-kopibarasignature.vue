<template>
  <v-sheet>
    <v-card flat="" height="88" color="grey lighten-3">
      <v-container>
        <v-row class="ma-3">
          <div class="title font-weight-light">
            Kopi Bara Signature
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
            <span class="font-weight-light">Kopi Bara Signature</span>
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
              Nusantara single origin coffee beans and coming from various
              origins that have their own special taste
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
        { image: '/img/signature-01.jpg' },
        { image: '/img/signature-02.jpg' }
      ]
    }
  }
}
</script>
