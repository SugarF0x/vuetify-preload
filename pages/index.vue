<template>
  <v-row justify="center">
    <v-col>
      <v-card>
        <v-card-title>
          Result of an asset image require
        </v-card-title>
        <v-card-text>
          <code>
            {{ display }}
          </code>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  },
  data() {
    return {
      result: require('~/assets/image.jpg?vuetify-preload')
    }
  },
  computed: {
    display() { return typeof this.result === 'string' ? this.result : JSON.stringify(this.result, null, '    ') }
  },
  mounted() {
    console.log(require('~/assets/image.jpg?vuetify-preload'))
  }
}
</script>
