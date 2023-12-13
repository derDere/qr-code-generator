<template>

  <v-container fluid>
    <v-row>

      <v-col
          class="qr-code-col"
          :cols="qrCodeCols"
        >
          <v-card class="qr-code-card">
          <QrCode />
        </v-card>
      </v-col>

      <v-col v-for="(a,i) in items" :key="a" :cols="featureCols">
        <v-card class="feature-card">
          TEST = ...{{ a }} - {{ i }}...
        </v-card>
      </v-col>

    </v-row>

  </v-container>

</template>

<script>
export default {
  data() {
    return {
      name: 'IndexPage',
      isDesktop: false,
      qrCodeCols: 6,
      featureCols: 3,
      items: ['T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T','T']
    };
  },
  mounted() {
    this.handleResize(); // Initialisierung basierend auf Fenstergröße
    window.addEventListener('resize', this.handleResize);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.handleResize);
  },
  methods: {
    handleResize() {
      this.isDesktop = window.innerWidth >= 1024; // Beispiel-Grenze für Desktop
    },
  },
};
</script>

<style scoped>
.qr-code-col {
  position: sticky;
  top: 70px;
  z-index: 1;
}
</style>
