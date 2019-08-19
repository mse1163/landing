<template>
  <div>
  <v-toolbar fixed>
      <!-- home 버튼 구현 -->
      <!--화면전환시 제일 상단보이게 하는 기능-->
      <div @click='goTop()'>
      <router-link :to="{ name: 'home', params: {} }" style="text-decoration: none"><v-icon medium>home</v-icon></router-link>
    </div>
    <v-toolbar-title>JinSeon`s Blog</v-toolbar-title>
    <v-spacer></v-spacer>

    <!--툴바 구현, 툴바 메뉴-->
      <v-toolbar-side-icon class="hidden-md-and-up gery-text" @click.stop="drawer = !drawer" style="color:black;"></v-toolbar-side-icon>

      <v-toolbar-items class="hidden-sm-and-down">
            <router-link :to="{ name: 'post', params: {} }" style="text-decoration: none"><v-btn flat>Post</v-btn></router-link>
            <router-link :to="{ name: 'portfolio', params: {} }" style="text-decoration: none"><v-btn flat>Portfolio</v-btn></router-link>
            <router-link :to="{ name: 'login', params: {} }" style="text-decoration: none"><v-btn flat>Login</v-btn></router-link>
            <v-btn flat @click="add()">즐겨찾기 추가</v-btn>
          </v-toolbar-items>

    </v-toolbar>

       <!-- 사이드바 메뉴 -->
       <v-navigation-drawer app v-model="drawer" class="sidebar" :mini-variant="mini" temporary>

         <v-list class="pa-1">
             <v-list-tile v-if="mini" @click.stop="mini = !mini">
               <v-list-tile-action>
                 <v-icon>chevron_right</v-icon>
               </v-list-tile-action>
             </v-list-tile>

             <v-list-tile avatar tag="div">
               <v-list-tile-avatar>
               </v-list-tile-avatar>

               <v-list-tile-content>
                 <v-list-tile-title> JinSeon`s blog</v-list-tile-title>
               </v-list-tile-content>

               <v-list-tile-action>
                 <v-btn icon @click.stop="mini = !mini">
                   <v-icon>chevron_right</v-icon>
                 </v-btn>
               </v-list-tile-action>
             </v-list-tile>
           </v-list>

           <v-list class="pt-0" dense>
              <v-divider light></v-divider>
              <v-list-tile>
                <v-list-tile-action >
                  <router-link :to="{ name: 'home', params: {} }"  tag="none" class="hover-effect"><v-icon>home</v-icon></router-link>
                </v-list-tile-action>
                <v-list-tile-content>
                   <v-list-tile-title>
                     <router-link :to="{ name: 'home', params: {} }"  tag="none" class="hover-effect">home</router-link>
                    </v-list-tile-title>
                </v-list-tile-content>
              </v-list-tile>

              <v-list-tile>
                <v-list-tile-action>
                  <router-link :to="{ name: 'post', params: {} }"  tag="none" class="hover-effect"><v-icon>dashboard</v-icon></router-link>
                </v-list-tile-action>
                <v-list-tile-content>
                  <router-link :to="{ name: 'post', params: {} }"  tag="none" class="hover-effect">Post</router-link>
                </v-list-tile-content>
              </v-list-tile>

              <v-list-tile>
                <v-list-tile-action>
                  <router-link :to="{ name: 'portfolio', params: {} }"  tag="none" class="hover-effect"><v-icon>chrome_reader_mode</v-icon></router-link>
                </v-list-tile-action>
                <v-list-tile-content>
                  <router-link :to="{ name: 'portfolio', params: {} }"  tag="none" class="hover-effect">Portfolio</router-link>
                </v-list-tile-content>
              </v-list-tile>

              <v-list-tile>
                <v-list-tile-action>
                  <router-link :to="{ name: 'login', params: {} }"  tag="none" class="hover-effect"><v-icon>portrait</v-icon></router-link>
                </v-list-tile-action>
                <v-list-tile-content>
                  <router-link :to="{ name: 'login', params: {} }"  tag="none" class="hover-effect">login</router-link>
                </v-list-tile-content>
              </v-list-tile>
            </v-list>
         </v-navigation-drawer>
<go-top bg-color="#FF0040" :size="50"></go-top>


</div>

</template>

<script>
import GoTop from '@inotom/vue-go-top';

export default {
  name: 'main-header',
  data () {
        return {
          drawer: null,
          items: [
            { title: 'Home', icon: 'dashboard' },
            { title: 'About', icon: 'question_answer' }
          ],
          mini: false,
          right: null
        }
      },
      components: {
        GoTop

      },
      methods: {
        add(){
          alert("ctrl+D를 눌러 추가하세요.");
        },
        goTop(){
          window.scrollTo(0,0);
        }
      }

}

</script>

<style scoped>
  .fixed_header{
    background: #F2F2F2;
    width: 100%;
    height: 100px;
    position: fixed;
    z-index: 3;
  }

</style>
