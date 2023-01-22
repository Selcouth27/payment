<template>
  <v-app>
    <v-main>
      <Payment />
      <link rel="styleshee" href="style.css">
    </v-main>
  </v-app>
</template>

<script setup>
  import Payment from '@/components/paymentProcess.vue'
  // import Payment from '@/components/payment.vue'
</script>

<style lang="css">
main{
  background-image: url(./assets/BG-header.jpg);
  background-size: 100%;
  background-color: #f1f1f1;
}

</style>
