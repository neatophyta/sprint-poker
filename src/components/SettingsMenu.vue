<template>
	<div class="settings">
		<div class="settings-header">Settings</div>
		<div class="section">
			<div class="section-title">Point Values</div>
			<div class="section-content numbers">
				<div class="option" v-for="(point, index) in allPoints" :key="point">
					<input type="checkbox" v-bind:id="'check-'+index" v-bind:value="point" v-model="checkedPoints" @change="handlePointChange">
					<label v-bind:for="'check-'+index">{{point}}</label>
				</div>
			</div>
		</div>
		<div class="section">
			<div class="section-title">Card backs</div>
			<div class="section-content">
				<div class="card-list">
					<div v-for="card in cardTypes" :key="card.key">
						<div v-bind:class="[card.key, 'card']" v-on:click="setCardBack(card.key)"></div>
						<div class="card-desc">
							{{ card.label }}
							<i v-if="cardBack === card.key" class="far fa-check-circle"></i>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>

export default {
	name: 'CardList',
	data: function () {
	    return {
	        flipped: false,
	        cardBack: null,
	        checkedPoints: [],
	        allPoints: [0, 0.5, 1, 2, 3, 5, 8, 13, 20, 40, 100],
	        cardTypes: [
	        	{
	        		key: 'waves',
	        		label: 'Waves'
	        	},
	        	{
	        		key: 'circuit',
	        		label: 'Circuit'
	        	},
	        	{
	        		key: 'bees',
	        		label: 'Bees?'
	        	},
	        	{
	        		key: 'fancy',
	        		label: 'Fancy'
	        	},
	        	{
	        		key: 'snacks',
	        		label: 'Snacks!'
	        	}
	        ]
	        	
	    }
	},
	methods: {
		setCardBack: function (card) {
		  	localStorage.setItem('cardBack', card);
		  	this.cardBack = card;
		},
		handlePointChange: function () {
		  	localStorage.setItem('checkedPoints', JSON.stringify(this.checkedPoints));
		}
	},
    mounted() {
    	//get selected card
      	if (localStorage.getItem('cardBack')) this.cardBack = localStorage.getItem('cardBack');
      	//get selected point values
      	if (localStorage.getItem('checkedPoints')) this.checkedPoints = JSON.parse(localStorage.getItem('checkedPoints'));
    }
}
</script>

<style scoped>

	.settings-header {
		margin: 1em;
		font-size: 2em;
	}

	.section {
		margin: 20px 0;
	}

	.section-title {
		font-size: 1.2em;
		font-weight: bold;
		margin: .5em;
	}

	.section-content.numbers {
		display: flex;
		justify-content: space-between;
	}

	.option {
		margin: 0 10px;
	}

	input {
		margin-right: 5px;
		vertical-align: bottom;
	}

	.card-list {
		display: flex;
		margin-bottom: 20px;
	}

	.card {
		border-radius: 6px;
		cursor: pointer;
		height: 140px;
		margin: 10px;
		position: relative;
		width: 100px;
	}

	.fa-check-circle {
		color: #7CB342;
	}

</style>
