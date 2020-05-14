<template>
  <v-sheet flat="" tile="">
    <!-- Carousel -->
    <v-carousel id="slider" cycle="" :interval="12000" progress="">
      <v-carousel-item
        v-for="(slider, i) in carouselItem"
        :key="`slider_${i}`"
        :src="slider.carouselImg"
        alt="Ganesha Mandiri Bakti"
      >
        <v-row
          class="fill-height white--text"
          align="center"
          justify="center"
          style="background-color: rgba(0, 0, 0, .5)"
        >
          <v-col :cols="$vuetify.breakpoint.mdAndDown ? '10' : '4'">
            <v-container>
              <div class="text-center" style="margin-bottom: 72px">
                <h2 class="headline">
                  {{ slider.captionTop }}
                </h2>
                <h2 class="title">{{ slider.captionCenter }}</h2>
                <h3 class="subtitle-1">
                  {{ slider.captionBottom }}
                </h3>
              </div>
            </v-container>
          </v-col>
          <v-col
            v-if="slider.haveAdditionalImage"
            cols="12"
            md="6"
            class="hidden-sm-and-down"
          >
            <v-img src="/img/slider-01.png"></v-img>
          </v-col>
        </v-row>
      </v-carousel-item>
    </v-carousel>
    <v-card id="features" flat="" tile="" color="">
      <v-responsive :aspect-ratio="2.5">
        <v-card-text class="fill-height">
          <v-row class="fill-height" align="center" justify="center">
            <v-col cols="12">
              <div class="text-center mb-5">
                <h2 class="display-1">Program Kami</h2>
              </div>
              <v-row justify="center">
                <v-col
                  v-for="(item, i) in featuresItem"
                  :key="i"
                  cols="12"
                  md="4"
                >
                  <v-card flat="" light="" ripple="" hover="">
                    <v-row>
                      <v-icon color="" size="88" class="text-center mx-auto">
                        {{ item.icon }}
                      </v-icon>
                    </v-row>
                    <v-card-text>
                      <div class="text-center">
                        <h2
                          :class="
                            $vuetify.breakpoint.mdAndDown
                              ? 'subtitle-1'
                              : 'headline'
                          "
                        >
                          {{ item.title }}
                        </h2>
                        <div class="caption">
                          <div
                            v-for="(text, j) in item.detail"
                            :key="`text_${j}`"
                          >
                            {{ text }}
                          </div>
                        </div>
                      </div>
                    </v-card-text>
                  </v-card>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-card-text>
      </v-responsive>
    </v-card>
    <v-card id="product" flat="" tile="">
      <v-row class="fill-height" align="center" justify="center">
        <div class="mt-3">
          <h2
            :class="
              $vuetify.breakpoint.mdAndDown
                ? 'headline font-weight-bold secondary--text'
                : 'display-1 font-weight-bold secondary--text'
            "
          >
            PRODUCT SEGMENTS
          </h2>
        </div>
      </v-row>
      <v-card-text class="fill-height hidden-sm-and-down">
        <v-row justify="center">
          <v-col v-for="(item, i) in productData" :key="i" cols="12" md="3">
            <v-card
              light=""
              ripple=""
              hover=""
              @click="$router.replace({ name: `${item.to}` })"
            >
              <v-img :src="item.productImage" alt="product" />
              <v-card-text>
                <v-list-item three-line>
                  <v-list-item-content class="align-center">
                    <v-list-item-title
                      class="subtitle mb-2 text-center blue--text"
                    >
                      {{ item.productName }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-card-text>
      <v-slide-group
        class="pa-4 mx-auto hidden-sm-and-up"
        center-active
        show-arrows
      >
        <v-slide-item
          v-for="(item, i) in productData"
          :key="i"
          v-slot:default=""
          class="sm-hidden"
        >
          <v-card
            class="ma-4"
            width="216"
            @click="$router.replace({ name: `${item.to}` })"
          >
            <v-img :src="item.productImage" style="height: 25vh;"> </v-img>
            <v-card-text>
              <v-list-item>
                <v-list-item-content class="align-center">
                  <v-list-item-title
                    class="subtitle mb-2 text-center blue--text"
                  >
                    {{ item.productName }}
                  </v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-card-text>
          </v-card>
        </v-slide-item>
      </v-slide-group>
    </v-card>
  </v-sheet>
</template>

<script>
export default {
  data() {
    return {
      carouselItem: [
        {
          carouselImg: '/img/slider-02.jpg',
          haveAdditionalImage: true,
          captionTop: 'OUR VISION',
          captionCenter: '',
          captionBottom:
            'To build a team with exceptionally fit mental and physical health who provide a sustainable coffee supply chain'
        }
      ],
      productData: [
        {
          productImage: '/img/portofolio/portofolio-01.jpg',
          productName: 'Kopi Bara Yahuddd',
          to: 'portofolio-listing-kopibarayahuddd'
        },
        {
          productImage: '/img/portofolio/portofolio-02.jpg',
          productName: 'Kopi Bara Premium',
          to: 'portofolio-listing-kopibarapremium'
        },
        {
          productImage: '/img/portofolio/portofolio-03.jpg',
          productName: 'Kopi Bara Signature',
          to: 'portofolio-listing-kopibarasignature'
        },
        {
          productImage: '/img/portofolio/portofolio-04.jpg',
          productName: 'Export Quality',
          to: 'portofolio-listing-exportquality'
        },
        {
          productImage: '/img/manufacturing/oem1.jpg',
          productName: 'OEM',
          to: 'manufacturing-oem'
        }
      ],
      featuresItem: [
        {
          icon: 'mdi-heart-pulse',
          title: 'Physically & Mentally Fit',
          detail: [
            'Consciously executing good energy management to keep one healthy & keep on improving the skill of creating prosperity resulting directly to happiness.'
          ]
        },
        {
          icon: 'mdi-recycle',
          title: 'Sustainable',
          detail: [
            '• Always eager in skill development to provide sustainable products.',
            '• Build social emotional skills to formulate hearty relationships with all stakeholders.',
            '• Putting attitude over aptitude to present respectfulservice.'
          ]
        },
        {
          icon: 'mdi-globe-model',
          title: 'Global',
          detail: [
            'Developing and improving distribution on an international level.'
          ]
        }
      ]
    }
  },
  head() {
    return { title: 'Home' }
  }
}
</script>
