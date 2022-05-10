/<template>
    <div class="pr_page" style="display: flex; flex-direction: column">
        <div class="pr_header">
            <div
                class="toggle_triangle"
                :class="{ is_inverse: !isPrOpen }"
                @click="onTogglePr"
            ></div>
            <div class="pr_title">
                {{ title }}
            </div>
        </div>
        <section v-if="isPrOpen" class="form">
				<div class="field">
					<label class="name">{{ exerciseData.exerciseName }}</label>
                    <label class="pR">{{ exerciseData.PR }}</label>
				</div>
			</section>
    </div>
</template>

<script>
export default {
    name: "PR",
    data() {
        return {
            title: "PRs!",
            isPrOpen: true,
            exerciseData: //[
                {
                    "exerciseName" : "Chest Press",
                    "PR": 10
                },
                /*
                {
                    "exerciseName" : "tricpDips",
                    "PR": 10
                }
            ]*/
        }
    },
    created() {
        this.isPrOpen = true;
    },
    methods: {
        onTogglePr() {
            this.isPrOpen = !this.isPrOpen;
        }
    }
}
</script>

<style lang=less>
    .pr_page {

    }
    .pr_header {
        display: flex;
		flex-flow: row nowrap;
		justify-content: flex-start;
		align-items: left; 
        padding: 10px 10px 10px 10px;
    }
    .pr_title {
		font-size: 30px;
		padding: 0 0px 0px 10px;
	}
    .field {
		display: flex;

		flex-flow: row nowrap;
		justify-content: flex-start;
		align-items: center;

		height: 100%;

		padding:10px 10px 10px 10px;

		background-color: transparent;
	}
    .name {
        padding:10px 10px 10px 10px;
        color: red;
    }
    .pR {
        padding:10px 10px 10px 10px;
        color: blue;
    }
</style>