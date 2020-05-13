<template>
  <v-app>
    <v-app-bar
      :height="88"
      dense=""
      app=""
      elevate-on-scroll=""
      hide-on-scroll=""
    >
      <v-container>
        <v-toolbar-title>
          <h1>
            <v-card
              color="transparent"
              flat=""
              nuxt=""
              exact=""
              to="/"
              aria-label="Satu Padu Indonesia"
            >
              <app-img
                src="/img/logo.png"
                alt="Satu Padu Indonesia"
                max-width="128"
                contain=""
              >
                <template #placeholder="">
                  <v-row
                    class="fill-height ma-0"
                    align="center"
                    justify="center"
                  >
                    <v-progress-circular indeterminate="" color="grey" />
                  </v-row>
                </template>
              </app-img>
            </v-card>
          </h1>
        </v-toolbar-title>
        <v-spacer />
      </v-container>
    </v-app-bar>
    <v-content>
      <nuxt />
    </v-content>
    <app-about />
    <app-footer />
  </v-app>
</template>

<script>
import AppImg from '~/components/AppImg'
import AppAbout from '~/components/AppAbout'
import AppFooter from '~/components/AppFooter'

export default {
  components: { AppImg, AppFooter, AppAbout }
}
</script>
