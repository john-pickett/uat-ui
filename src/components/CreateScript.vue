<template>
	<v-container grid-list-md>
		<h3 class="display-2 mb-3">Create Feature Script</h3>
        <v-layout wrap>
            <v-flex mb-5 sm6>
				<v-card>
					<v-card-text>
						<v-text-field
							label="Name"
							hint="Give this script a name."
                            v-model="script.name"
						></v-text-field>
                        <v-text-field
							label="Initial URL"
							hint="The URL that your user should go to to start testing the new feature."
                            v-model="script.url"
						></v-text-field>
						<v-textarea
							label="Overall Description"
							hint="Describe the feature being demonstrated and the overall goal to the user."
                            v-model="script.description"
						></v-textarea>
                        <v-text-field
                            label="Action"
                            hint="Describe the action your user should take."
                            v-model="script.steps[0].action"
                        ></v-text-field>
                        <v-text-field
                            label="Desired Outcome"
                            hint="Describe what they should see as a result of the action."
                            v-model="script.steps[0].outcome"
                        ></v-text-field>
                        <v-text-field
                            label="Action"
                            hint="Describe the action your user should take."
                            v-model="script.steps[1].action"
                        ></v-text-field>
                        <v-text-field
                            label="Desired Outcome"
                            hint="Describe what they should see as a result of the action."
                            v-model="script.steps[1].outcome"
                        ></v-text-field>
					</v-card-text>
					<v-card-actions>
						<v-btn color="error" id="clear-script-btn">Clear Script</v-btn>
						<v-btn color="green" id="save-script-btn" @click="postScript()">Save</v-btn>
					</v-card-actions>
				</v-card>
			</v-flex>
			<v-flex mb-5 sm6>
				<!-- <div v-for="i in totalSteps" :key=i :id="'script_input_' + i">
					<script-input :steps="totalSteps"></script-input>
                    
				</div> -->
                <v-card>
                <v-card-text>
                        <v-text-field
                            label="Action"
                            hint="Describe the action your user should take."
                            v-model="script.steps[2].action"
                        ></v-text-field>
                        <v-text-field
                            label="Desired Outcome"
                            hint="Describe what they should see as a result of the action."
                            v-model="script.steps[2].outcome"
                        ></v-text-field>
                        <v-text-field
                            label="Action"
                            hint="Describe the action your user should take."
                            v-model="script.steps[3].action"
                        ></v-text-field>
                        <v-text-field
                            label="Desired Outcome"
                            hint="Describe what they should see as a result of the action."
                            v-model="script.steps[3].outcome"
                        ></v-text-field>
                         <v-text-field
                            label="Action"
                            hint="Describe the action your user should take."
                            v-model="script.steps[4].action"
                        ></v-text-field>
                        <v-text-field
                            label="Desired Outcome"
                            hint="Describe what they should see as a result of the action."
                            v-model="script.steps[4].outcome"
                        ></v-text-field>
                         <v-text-field
                            label="Action"
                            hint="Describe the action your user should take."
                            v-model="script.steps[5].action"
                        ></v-text-field>
                        <v-text-field
                            label="Desired Outcome"
                            hint="Describe what they should see as a result of the action."
                            v-model="script.steps[5].outcome"
                        ></v-text-field>
					</v-card-text>
                    </v-card>
			</v-flex>
            
		</v-layout>
	</v-container>
</template>

<script>
	import ScriptInput from './ScriptInput.vue';
    import DummyInput from './DummyInput.vue';
    import axios from 'axios';

	export default {
		components: {
            ScriptInput,
            DummyInput
		},
		data: () => ({
            script: {
                feature_id: '',
                name: '',
                url: '',
                description: '',
                steps: [{}, {}, {}, {}, {}, {}]
            }
		}),
		methods: {
			addStep () {
				this.totalSteps += 1;
			},
			removeStep () {
				if (this.totalSteps > 1) {
					this.totalSteps -= 1;
				}
            },
            postScript () {
                axios.post('http://localhost:3000/scripts', {
                    "name": this.script.name,
                    "description": this.script.description,
                    "url": this.script.url,
                    "feature_id": "ca5150ea-11c5-4cba-b3cf-3536e5751249",
                    "steps": this.script.steps
                }).then((res) => {
                    console.log(JSON.stringify(res.data))
                })
            }
		}
	}
</script>

<style>
	#add-step-btn {
		color: white;
	}

</style>
