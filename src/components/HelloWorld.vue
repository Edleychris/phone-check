<template>
  <div class="container">
    <div @click="openAppStore()">
      <a :href="appStoreLink" target="_blank">
      <img src="../assets/ban1.jpeg" alt=""></a>
    </div>
    <div @click="openAppStore()">
      <a :href="appStoreLink" target="_blank">
      <img src="../assets/ban2.jpeg" alt=""></a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      appStoreLink: '',
    };
  },
  created() {
    this.setAppStoreLink();
  },
  methods: {
    setAppStoreLink() {
      const userAgent = window.navigator.userAgent || window.navigator.vendor || window.opera;
      if (/android/i.test(userAgent)) {
        this.appStoreLink = 'https://play.google.com/store/apps/details?id=com.naijakobo.naijakobomarket&hl=en&gl=US';
      } else if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
        this.appStoreLink = 'https://apps.apple.com/us/app/naija-kobo-market/id1491327218';
      }
    },
    openAppStore() {
      if (this.appStoreLink) {
        window.open(this.appStoreLink, '_blank');
      }
    },
}
}
</script>
<style scoped>
.container{
  display: flex;
}
</style>
