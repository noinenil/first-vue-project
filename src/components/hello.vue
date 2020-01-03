<template>
	<div class="hello">
		<h1>{{myString}}</h1>
		<p align="left">{{myText}}</p>
	</div>
</template>

<script>
	export default {
		name: 'hello',
		created: function() {
				var h1 = setInterval(this.writerLetters, 300);
				setInterval(this.writerText, 100);
				if (this.phrase.length < this.counter) {
					clearInterval(h1);
				}
			
		},
		data: function() {
			return ({
				counter:0,
				counterText:0,
				phrase:'This is my first VUE component!\n',
				text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Provident, deleniti?\n',
				myString: '',
				myText: '',
			})

		},
		methods: {
			writerLetters: function() {
				if (this.phrase.length > this.counter) {
				this.myString += this.phrase[this.counter]
				this.counter++	
				}		
			},
			writerText: function() {
				if (this.text.length > this.counterText) {
				this.myText += this.text[this.counterText]
				this.counterText++
				} else {
					this.counterText = 0
				}	
			}
		},
	}

</script>