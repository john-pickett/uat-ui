<template>
	<div :id="id" class="my-1">
		<v-card>
			<v-card-title class="text-sm-right">
				<h3 class="headline">Step One</h3>
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
		</v-card>
		
	</div>
</template>

<script>
export default {
	props: ['steps', 'stepNumber'],
	data: () => ({
		id: null
	}),
	mounted () {
		this.id = this._uid
	}
}
</script>
