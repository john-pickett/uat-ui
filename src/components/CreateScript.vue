<template>
	<v-container grid-list-md>
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
						<v-text-field
							label="Initial URL"
							hint="The URL that your user should go to to start testing the new feature."
						></v-text-field>
						<v-textarea
							label="Overall Description"
							hint="Describe the feature being demonstrated and the overall goal to the user."
						></v-textarea>
					</v-card-text>
					<v-card-actions>
						
					</v-card-actions>
				</v-card>
				<div v-for="i in totalSteps" :key=i :id="'script_input_' + i">
					<script-input :steps="totalSteps"></script-input>
				</div>
				<v-btn color="error" @click="removeStep" id="remove-step-btn">Remove Last Step</v-btn>
				<v-btn color="green" @click="addStep" id="add-step-btn">Add Step</v-btn>
			</v-flex>
			<v-flex mb-5 xs12 sm6>
				<v-card>
					<v-card-title>
						<p class="headline">Script Summary</p>
					</v-card-title>
					<v-card-text>
						
					</v-card-text>
					<v-card-actions>
						<v-btn color="error" @click="removeStep" id="remove-step-btn">Clear Script</v-btn>
						<v-btn color="green" @click="addStep" id="add-step-btn">Save</v-btn>
					</v-card-actions>
				</v-card>
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
