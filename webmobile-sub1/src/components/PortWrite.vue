<template>
  <v-container>
    <h1>포트폴리오 작성하시오.</h1>
  </br>
  <v-form>
    <div>
    <label>제목</label>
    <v-text-field v-model="title" type="text" placeholder="제목 입력하시오."></v-text-field>
  </div>
  <div>
  <label>날짜</label>
  <v-text-field v-model="date" type="text" placeholder="날짜 입력하시오."></v-text-field>
</div>
  <div>
      <markdown-editor v-model="body" :options="options" placeholder="내용 입력하시오."></markdown-editor>
  </div>
  <div>
             <v-flex xs12 class="text-xs-center text-sm-center text-md-center text-lg-center">
                             <img :src="imageUrl" height="150" v-if="imageUrl"/>
                             <v-text-field label="Select Image" @click='pickFile' v-model='imageName' prepend-icon='attach_file'></v-text-field>
                             <input
                                  type="file"
                                  style="display: none"
                                  ref="image"
                                  accept="image/*"
                                  @change="onFilePicked"
                             >
                </v-flex>
          </div>
          <div>
            <router-link :to="{ path: 'Portfolio' }"><v-btn class="btn btn-primary" v-on:click="writePortfolio()" type="button">완료</v-btn></router-link>
         </div>


</v-form>
</v-container>
</template>

<script>
import Portfolio from '@/components/Portfolio'
import FirebaseService from '@/services/FirebaseService'

export default{
  name : "PortWrite",
   data() {
      return {
         title : "",
         body : "",
         // img : "https://source.unsplash.com/random",
      img_title: "Image Upload",
      dialog: false,
        imageName: '',
        imageUrl: '',
      imageFile: ''
      }
   },
   components: {
      // Portfolio
   },
   mounted() {
      // this.getPortfolios()
   },
   methods: {
    pickFile () {
            this.$refs.image.click ()
        },
      onFilePicked (e) {
         const files = e.target.files
         if(files[0] !== undefined) {
            this.imageName = files[0].name
            if(this.imageName.lastIndexOf('.') <= 0) {
               return
            }
            const fr = new FileReader ()
            fr.readAsDataURL(files[0])
            fr.addEventListener('load', () => {
               this.imageUrl = fr.result
               this.imageFile = files[0] // this is an image file that can be sent to server...
            })
         } else {
            this.imageName = ''
            this.imageFile = ''
            this.imageUrl = ''
         }
      },
    writePortfolio() {
      console.log("제출버튼 클릭");
      let msg = FirebaseService.postPortfolio(this.title, this.date, this.body, this.imageUrl);
      conosole.log("포트폴리오 작성 결과", msg);
    }
   }
}
</script>
