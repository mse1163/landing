<template>
  <v-card>
    <!-- <v-img :src="imgSrc" height="200px"> -->
    <v-img :src="imgSrc" aspect-ratio="1.0">
    </v-img>
    <v-card-title primary-title>
      <div>
        <div class="headline">{{title}}</div>
        <span class="grey-text">{{body}}</span>
      </div>
    </v-card-title>
  </v-card>
</template>

<script>
export default {
	name: 'Portfolio',
	props: {
		date: {type: String},
		title: {type: String},
		body: {type: String},
		imgSrc: {type: String},
	},
	data() {
		return {
			//
		}
	}
}
</script>

<style>
.grey-text{
  display: -webkit-box;
  -webkit-line-clamp:3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
