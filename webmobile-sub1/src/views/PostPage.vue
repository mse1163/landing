<template>
  <div>
    <ImgBanner imgSrc="https://source.unsplash.com/random/1600x900/?coffee">
      <div style="line-height:1.2em; color:white; font-size:1.2em;" slot="text">Post</div>
    </ImgBanner>
    <v-container>

      <!-- Post -->
      <v-layout>
        <v-flex xs12>
          <PostList :limits="6" :load-more="true"></PostList>
        </v-flex>
      </v-layout>

    </v-container>
  </div>
</template>

<script>
import ImgBanner from '../components/ImgBanner'
import PostList from '../components/PostList'

export default {
	name: 'PostPage',
	components: {
		ImgBanner,
		PostList,
	}
}
</script>
