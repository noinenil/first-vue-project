<template>
	<div class="car">
		<h3>Name: {{ carName }}  \ {{ reverseName }}</h3>
		<p>Year: {{ carYear }}</p>
		<button @click="changeName">Change name</button>
		<button @click="changeFunc()">Change from parent</button>
		<button @click="updateCounter">Update counter</button>
	</div>
</template>

<style>	
  .car {
  	display: inline-block;  	
  	border: 1px solid black;
  	padding: 5px 150px 5px 150px;

  }
  .car h3 {
  	margin-bottom: 5px;		
  }
  button {
  	margin: 5px;
  }
</style>

<script>
	export default {
		// data: function () {
		// }
		props: {
			carName: String,
			carYear: Number,
			changeFunc: Function,
			counter: Number,
		},
		methods: {
			changeName () {
				this.carName = 'Mazda'
				this.$emit('nameChanged', this.carName)
			},
			updateCounter() {
				this.$emit('counterUpdated', this.counter + 1)
			}
		},
		computed: {
		    reverseName() {
		      return this.carName.split('').reverse().join('')

    }
  },
	}
</script>

