<template>
	<v-container>
		<v-layout wrap>
			<v-flex text-xs-center mb-4 sm12>
				<h3 class="display-2 mb-3">Create Script</h3>
			</v-flex>
			<v-flex mb-5 xs12 sm6>
				<v-card>
					<v-card-title>
						<p class="headline">Feature</p>
					</v-card-title>
					<v-card-text>
						<span class="title">Starting URL: <a href="http://www.cnn.com" target="_blank">www.cnn.com</a></span>
					</v-card-text>
					<v-card-actions>
						<v-btn color="green" @click="addStep" id="add-step-btn">Add Step</v-btn>
						<v-btn color="error" @click="removeStep" id="remove-step-btn">Remove Last Step</v-btn>
					</v-card-actions>
				</v-card>
				<div v-for="n in totalSteps" :key=n>
					<script-input :steps="totalSteps"></script-input>
				</div>
			</v-flex>
		</v-layout>
	</v-container>
</template>

<script>
	import ScriptInput from './ScriptInput.vue';

	export default {
		components: {
			ScriptInput
		},
		data: () => ({
			totalSteps: 1
		}),
		methods: {
			addStep () {
				this.totalSteps += 1;
			},
			removeStep () {
				if (this.totalSteps > 1) {
					this.totalSteps -= 1;
				}
			}
		}
	}
</script>

<style>
	#add-step-btn {
		color: white;
	}

</style>
