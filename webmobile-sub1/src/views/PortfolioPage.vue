<template>
  <div>
    <ImgBanner imgSrc="https://source.unsplash.com/random/1600x900/?coffee">
      <div style="line-height:1.2em; color:white; font-size:1.2em;" slot="text">Portfolio</div>
    </ImgBanner>
    <v-container>

      <!-- Portfolio -->
      <v-layout>
        <v-flex>
          <div>
        <router-link :to="{ name: 'portwrite', params: {} }"><v-btn style="float:right" >글쓰기</v-btn></router-link>
      </div>
    </v-flex>
    </v-layout>

      <v-layout>
      </v-flex>
        <v-flex xs12>
          <PortfolioList :limits="6" :load-more="true"></PortfolioList>
        </v-flex>
      </v-layout>

    </v-container>

  </div>
</template>

<script>
import ImgBanner from '../components/ImgBanner'
import PortfolioList from '../components/PortfolioList'

export default {
	name: 'PortfolioPage',
	components: {
		ImgBanner,
		PortfolioList,
	},
}
</script>
