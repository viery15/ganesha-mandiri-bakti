<template>
  <v-card color="" dark tile="">
    <v-row justify="center" align="center" class="white--text">
      <v-col cols="12" xs="8">
        <v-row align="start" justify="center">
          <v-col cols="12" md="3" sm="4" lg="3" class="">
            <p
              class="mb-0 text-center"
              style="font-size: 140%; font-weight: 300;"
            >
              <b>About</b>
            </p>
            <div class="font-weight-light caption pa-4">
              PT GMB is a distribution company that was founded in 2011. we
              started our journey by opening micro-sized retail coffee outlets
              as a pilot project, to allow us understand what the customers want
              firsthand. From the experience we develop coffee recipes which was
              then expanded into retail products.
            </div>
          </v-col>

          <v-col cols="12" md="3" sm="4" lg="3">
            <p
              class="mb-0 text-center"
              style="font-size: 140%;font-weight: 300;"
            >
              <b>Get In Touch</b>
            </p>
            <v-list-item v-for="(item, i) in companyData" :key="i">
              <v-list-item-icon>
                <v-icon v-text="item.icon" />
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title class="caption" v-text="item.info" />
              </v-list-item-content>
            </v-list-item>
          </v-col>
          <v-col cols="12" md="3" sm="4" lg="3">
            <p
              class="mb-0 text-center"
              style="font-size: 140%;font-weight: 300;"
            >
              <b>Newsletter</b>
            </p>
            <div class="font-weight-light caption pa-4">
              Join our mailing list to stay up to date and get notices about our
              new releases!
            </div>
            <div class="pa-4">
              <v-text-field label="Email" outlined dense />
              <v-btn color="primary" dark="" @click="emaildecode">Gabung</v-btn>
            </div>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
/* eslint-disable no-unused-expressions */
export default {
  data() {
    return {
      companyData: [
        {
          icon: 'mdi-map-marker',
          info: 'Musi Street 21, Surabaya City East Java'
        },
        {
          icon: 'mdi-account',
          info: '(+62)31 5618880'
          // info: '(+62)81 334098929'
        },
        {
          icon: 'mdi-email',
          info: 'info@ganeshamandiribhakti.com'
        }
      ]
    }
  },
  methods: {
    emaildecode() {
      'use strict'
      function e(e) {
        try {
          if (typeof console === 'undefined') return
          // eslint-disable-next-line no-console
          'error' in console ? console.error(e) : console.log(e)
        } catch (e) {}
      }
      function t(e) {
        return (
          (d.innerHTML = '<a href="' + e.replace(/"/g, '&quot;') + '"></a>'),
          d.childNodes[0].getAttribute('href') || ''
        )
      }
      function r(e, t) {
        const r = e.substr(t, 2)
        return parseInt(r, 16)
      }
      function n(n, c) {
        // eslint-disable-next-line no-unused-vars
        for (let o = '', a = r(n, c), i = c + 2; i < n.length; i += 2) {
          const l = r(n, i) ^ a
          o += String.fromCharCode(l)
        }
        try {
          // eslint-disable-next-line no-func-assign
          o = decodeURIComponent(escape(o))
        } catch (u) {
          e(u)
        }
        return t(o)
      }
      function c(t) {
        for (let r = t.querySelectorAll('a'), c = 0; c < r.length; c++)
          try {
            const o = r[c]
            const a = o.href.indexOf(l)
            a > -1 && (o.href = 'mailto:' + n(o.href, a + l.length))
          } catch (i) {
            e(i)
          }
      }
      function o(t) {
        for (let r = t.querySelectorAll(u), c = 0; c < r.length; c++)
          try {
            const o = r[c]
            const a = o.parentNode
            const i = o.getAttribute(f)
            if (i) {
              const l = n(i, 0)
              const d = document.createTextNode(l)
              a.replaceChild(d, o)
            }
          } catch (h) {
            e(h)
          }
      }
      function a(t) {
        for (let r = t.querySelectorAll('template'), n = 0; n < r.length; n++)
          try {
            i(r[n].content)
          } catch (c) {
            e(c)
          }
      }
      function i(t) {
        try {
          // eslint-disable-next-line no-sequences
          c(t), o(t), a(t)
        } catch (r) {
          e(r)
        }
      }
      const l = '/cdn-cgi/l/email-protection#'
      const u = '.__cf_email__'
      const f = 'data-cfemail'
      const d = document.createElement('div')
      // eslint-disable-next-line no-sequences
      i(document),
        (function() {
          const e =
            document.currentScript ||
            document.scripts[document.scripts.length - 1]
          e.parentNode.removeChild(e)
        })()
    }
  }
}
</script>
