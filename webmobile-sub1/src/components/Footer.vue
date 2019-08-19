<template>
  <v-footer
    dark
    height="auto"
  >
    <v-card
      class="flex"
      flat
      tile
    >
      <v-card-title class="green">
        <strong class="subheading">무단복사 및 무단사용시 법적처리대상이 될 수 있습니다.<br>
        Copyright. 2019 Baek JinSeon All Right Reserved.</strong>

        <v-spacer></v-spacer>

        <v-btn
          v-for="icon in icons"
          :key="icon[0]"
          :href='icon[1]'
          class="mx-3"
          dark
          icon
        >
          <v-icon size="24px">{{ icon[0] }}</v-icon>
        </v-btn>
      </v-card-title>

      <v-card-actions class="grey darken-3 justify-center">
        &copyright;2019 — <strong>JinSeon</strong>
      </v-card-actions>
    </v-card>
  </v-footer>
</template>


<script>
export default {
  name: 'main-footer',
    data: () => ({
      icons: [
        ['fab fa-facebook',"https://ko-kr.facebook.com/FacebookKorea/"],
        ['fab fa-twitter',"https://twitter.com/search-home?lang=ko"],
        ['fab fa-linkedin', "https://kr.linkedin.com/"],
        ['fab fa-instagram', "https://www.instagram.com/?hl=ko"]
      ]
    })
}
</script>

<!-- /* <style scoped>
.footer_css{
  background: black;
  padding: 10px;
}
</style> */ -->
