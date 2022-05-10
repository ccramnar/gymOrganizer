<template>
  <div class="advanced_lens_editor_content" style="display: flex; flex-direction: row">
    <Header
      @show-push-page="showPage(1)"
      @show-start-page="showPage(0)"
    />
    <StartPage v-if="showStartPage"/>
    <PushPage v-if="showPushPage" />
  </div>
</template>

<script>
import StartPage from  './components/StartPage.vue'
import Header from './components/Header.vue'
import PushPage from './components/Push.vue'

export default {
  name: 'App',
  components: {
    Header,
    StartPage,
    PushPage
  },
  data() {
    return {
      showStartPage: true,
      showPushPage: false,
    }
  },
  created() {
    this.showStartPage = true;
  },
  methods: {
    showPage(pageCode) {
      switch(pageCode) {
        case 0: {
          this.showPushPage = false;
          this.showStartPage = true;
        }
        break;
        case 1: {
          this.showStartPage = false;
          this.showPushPage = true;
        } 
        break;
        default: 
      }
    }
  }
}
</script>

<style lang=less>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
.toggle_triangle {
		width: 20px;
		height: 20px;
		align-items: center;

		background-color: #8c8c8c;

		-webkit-mask-image: url("./assets/navBar//push.png");
		mask-image: url("./assets/navBar/push.png");
		-webkit-mask-size: 20px 20px;
		mask-size: 20px 20px;
		-webkit-mask-position: center;
		mask-position: center;
		rotate: 270deg;

		&:hover {
			background-color: #acacac;
		}
	}
</style>
