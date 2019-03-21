<template>
	<v-container>
		<v-layout text-xs-center wrap>
			<v-flex mb-4>
				<h1 class="display-2 font-weight-bold mb-3">UAT</h1>
			</v-flex>
			<v-flex mb-5 xs12>
				<p><router-link to="/create"><v-btn color="green">Create Script</v-btn></router-link></p>
				<p><router-link to="/view"><v-btn color="green">View Script</v-btn></router-link></p>
			</v-flex>
		</v-layout>
	</v-container>
</template>

<script>
  export default {
    data: () => ({
      
    })
  }
</script>

<style>
	a {
		text-decoration: none;
	}
</style>
