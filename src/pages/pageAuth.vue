<template>
	<q-page padding>
		<q-card class="auth-tabs">
		  <q-tabs
		    v-model="tab"
		    dense
		    class="text-grey"
		    active-color="primary"
		    indicator-color="primary"
		    align="justify"
		    narrow-indicator
		  >
		    <q-tab name="login" label="Login" />
		    <q-tab name="daftar" label="Daftar" />
		  </q-tabs>

		  <q-separator />

		  <q-tab-panels v-model="tab" animated>
		    <q-tab-panel name="login">
		      <login-daftar :tab="tab" />
		    </q-tab-panel>

		    <q-tab-panel name="daftar">
		      <login-daftar :tab="tab" />
		    </q-tab-panel>

		  </q-tab-panels>
		</q-card>
	</q-page>
</template>

<script>
	export default {
		data () {
	    return {
	      tab: 'daftar'
	    }
	  },
	  components: {
	  	'login-daftar' : require('components/Auth/LoginRegister.vue').default
	  }
	}
</script>

<style>
	.auth-tabs {
		max-width: 500px;
		margin: 0 auto;
	}
</style>