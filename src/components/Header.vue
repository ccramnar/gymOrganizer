<template>
    <div id="header" style="flex: none">
        <div
            class="menu_icon"
            @click="onToggleMenu"
        ></div>
    <section class="menu"  v-show="isMenuToggle">
        <div
            class="start"
            @click="onToggleStartPage"
        > </div>
       <div
            class="push"
            @click="onTogglePushPage"
        > </div>
        <div
            class="lower_body"
            @click="onToggleLowerBodyPage"
        > </div>
        <div
            class="pull"
            @click="onTogglePullPage"
        > </div>
        <div
            class="cardio"
            @click="onToggleCardioPage"
        > </div>
    </section>
    </div>
</template>

<script>
export default {
    name: "HeaderNavigationBar",
    emits: ["show-push-page", "show-start-page"],
    data() {
        return {
            isMenuToggle: false
        }
    },
    methods: {
        onToggleMenu() {
            this.isMenuToggle = !this.isMenuToggle;
            const top = document.getElementById("header");
			if (this.isSurfacesPropertiesOpen) {
				top.style = "flex: 1";
			} else {
				top.style = "flex: none";
			}
        },
        onTogglePushPage() {
            this.$emit("show-push-page");
        },
        onToggleStartPage() {
            this.$emit("show-start-page");
        }
    }

}
</script>

<style lang="less">
    .menu_icon {
		width: 30px;
		height: 30px;
		align-items: center;

		background-color: #8c8c8c;

		-webkit-mask-image: url("../assets/navBar/list.png");
		mask-image: url("../assets/navBar/list.png");
		-webkit-mask-size: 30px 30px;
		mask-size: 30px 30px;
		-webkit-mask-position: center;
		mask-position: center;

		&:hover {
			background-color: #acacac;
		}
	}
    .menu {
       display: flex;
		flex-flow: column nowrap;
		justify-content: flex-start;
		align-items: left; 
        padding: 25px 0px 0px 0px;
    }
    .push {
        width: 30px;
		height: 30px;
		align-items: center;

		background-color: #8c8c8c;

		-webkit-mask-image: url("../assets/navBar/push.png");
		mask-image: url("../assets/navBar/push.png");
		-webkit-mask-size: 30px 30px;
		mask-size: 30px 30px;
		-webkit-mask-position: center;
		mask-position: center;

		&:hover {
			background-color: #acacac;
		}
    }
    .pull {
        width: 30px;
		height: 30px;
		align-items: center;

		background-color: #8c8c8c;

		-webkit-mask-image: url("../assets/navBar/push.png");
		mask-image: url("../assets/navBar/push.png");
		-webkit-mask-size: 30px 30px;
		mask-size: 30px 30px;
		-webkit-mask-position: center;
		mask-position: center;

		&:hover {
			background-color: #acacac;
		}
    }
    .lower_body {
        width: 30px;
		height: 30px;
		align-items: center;

		background-color: #8c8c8c;

		-webkit-mask-image: url("../assets/navBar/push.png");
		mask-image: url("../assets/navBar/push.png");
		-webkit-mask-size: 30px 30px;
		mask-size: 30px 30px;
		-webkit-mask-position: center;
		mask-position: center;

		&:hover {
			background-color: #acacac;
		}
    }
    .cardio {
        width: 30px;
		height: 30px;
		align-items: center;

		background-color: #8c8c8c;

		-webkit-mask-image: url("../assets/navBar/push.png");
		mask-image: url("../assets/navBar/push.png");
		-webkit-mask-size: 30px 30px;
		mask-size: 30px 30px;
		-webkit-mask-position: center;
		mask-position: center;

		&:hover {
			background-color: #acacac;
		}
    }
    .start {
        width: 30px;
		height: 30px;
		align-items: center;

		background-color: #8c8c8c;

		-webkit-mask-image: url("../assets/navBar/gym.png");
		mask-image: url("../assets/navBar/gym.png");
		-webkit-mask-size: 30px 30px;
		mask-size: 30px 30px;
		-webkit-mask-position: center;
		mask-position: center;

		&:hover {
			background-color: #acacac;
		}
    }

</style>