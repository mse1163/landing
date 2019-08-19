<template>
  <v-app>
    <div id="header">
      <main-header/>
    </div>

    <v-content>
      <router-view/>
    </v-content>

    <div id="footer">
      <main-footer/>
    </div>
  </v-app>

</template>

<script>
import store from './store'
import Header from './components/Header'
import Footer from './components/Footer'


export default {
	name: 'App',
	store,
	data() {
    menu:[
      {
        href:'/',
        title:' Dashboard',
        icon: 'fa fa-user'
      },
      {
        href: '#',
        title: 'Charts',
        icon: 'fa fa-chart-area'
      }
    ]
		return {
			//
		}
	},
  components: {
    'main-header' : Header,
    'main-footer' : Footer,

  }

}
</script>
