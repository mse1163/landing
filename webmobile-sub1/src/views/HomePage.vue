<template>
  <div>
    <ImgBanner imgSrc="https://source.unsplash.com/random/1600x900/?coffee">
      <div style="line-height:1.2em; color:white; bold" slot="text">We will find a way.<br> We always have.</div>
    </ImgBanner>
    <v-container>
      <!-- About Me -->
      <v-layout my-5>
        <v-flex xs12 sm8 class="me_text" :class="$mq">
          <h2 class="headline mb-3">About Me</h2>
          <p class="mr-4" >안녕하세요, 개발자 백진선입니다.!<br/>저는 습득력과 응용력이 좋습니다. 그래서 개발하는데 처음에는 더딜지라도 한번 속도가 붙으면 따라올 수 없습니다.</p>
          <br>
          <p class="mr-4">
            <h4>Skill</h4>
            "Java",  "Spring",  "R",  "SPSS"
          </p>
        </v-flex>
        <v-flex sm4 class="hidden_img" :class="$mq">
          <v-img :src="getImgUrl('photo.png')" aspect-ratio="0.5" style="height: 200px;  width: 120px "/>
        </v-flex>
      </v-layout>

      <!-- Portfolio -->
      <v-layout my-5>
        <v-flex xs12>
          <h2 class="headline my-5 text-xs-center">
            <router-link :to="{ name: 'portfolio', params: {} }" style="text-decoration: none">Portfolio</router-link>
           </h2>
          <PortfolioList></PortfolioList>
        </v-flex>
      </v-layout>

      <!-- Post -->
      <v-layout my-5>
        <v-flex xs12>
          <h2 class="headline my-5 text-xs-center">Post</h2>
          <PostList :column="2"></PostList>
        </v-flex>
      </v-layout>


      <!-- Github -->
      <v-layout my-5>
        <v-flex xs12>
          <h2 class="headline my-5 text-xs-center">Project</h2>
          <RepositoryList></RepositoryList>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import ImgBanner from '../components/ImgBanner'
import PortfolioList from '../components/PortfolioList'
import PostList from '../components/PostList'
import RepositoryList from '../components/RepositoryList'

export default {
	name: 'HomePage',
	components: {
		ImgBanner,
		PortfolioList,
		PostList,
		RepositoryList,

	},
	methods: {
		getImgUrl(img) {
			return require('../assets/' + img)
		}
	},
}
</script>
<style>
  .hidden_img.mobile {
    display: none;
  }
  .me_text.mobile{
    width: 100%;
    text-align: center;
  }
</style>
