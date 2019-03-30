<template>
	<div :id="id" class="my-1">
		<v-card>
			<v-card-title class="text-sm-right">
				<h3 class="headline">Step</h3>
			</v-card-title>
			<v-card-text>
				<v-text-field
					label="Action"
					hint="Describe the action your user should take."
				></v-text-field>
				<v-text-field
					label="Desired Outcome"
					hint="Describe what they should see as a result of the action."
				></v-text-field>
			</v-card-text>
            <v-card-actions>
                <v-btn flat color="error" @click="removeStep" id="remove-step-btn">Remove This Step</v-btn>
				<v-btn flat color="green" @click="addStep" id="add-step-btn">Add Step</v-btn>
            </v-card-actions>
		</v-card>
		
	</div>
</template>

<script>
export default {
	props: ['steps', 'currentStep'],
	data: () => ({
		id: null
	}),
	mounted () {
		this.id = this._uid
	}
}
</script>
