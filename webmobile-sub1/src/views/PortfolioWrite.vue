<template>
<div>
  <ImgBanner imgSrc="https://source.unsplash.com/random/1600x900/?coffee">
      <div style="line-height:1.2em; color:white; font-size:1.2em;" slot="text">PortfolioWrite</div>
  </ImgBanner>
  <v-container>

    <!-- portfolio write-->
    <v-layout my-5>
      <v-flex xs12 sm8>
        <PortWrite></PortWrite>
      </v-flex>

    </v-layout>
  </v-container>
</div>
</template>


<script>
import ImgBanner from '../components/ImgBanner'
import PortWrite from '../components/PortWrite'

export default {
	name: 'PortfolioWrite',
  components: {
		ImgBanner,
    PortWrite,
  }
}
</script>
