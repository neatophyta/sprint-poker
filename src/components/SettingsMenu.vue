<template>
	<div class="settings">
		<div class="settings-header">Settings</div>
		<div class="section">
			<div class="section-title">Point Values</div>
			<div class="section-content numbers">
				<div class="option">
					<input type="checkbox" id="check-0" name="0" value="0" checked>
					<label for="check-0">1</label>
				</div>
				<div class="option">
					<input type="checkbox" id="check-half" name="half" value="0.5" checked>
					<label for="check-half">0.5</label>
				</div>
				<div class="option">
					<input type="checkbox" id="check-1" name="1" value="1" checked>
					<label for="check-1">1</label>
				</div>
				<div class="option">
					<input type="checkbox" id="check-2" name="2" value="2" checked>
					<label for="check-2">2</label>
				</div>
				<div class="option">
					<input type="checkbox" id="check-3" name="3" value="3" checked>
					<label for="check-3">3</label>
				</div>
				<div class="option">
					<input type="checkbox" id="check-5" name="5" value="5" checked>
					<label for="check-5">5</label>
				</div>
				<div class="option">
					<input type="checkbox" id="check-8" name="8" value="8" checked>
					<label for="check-8">8</label>
				</div>
				<div class="option">
					<input type="checkbox" id="check-13" name="13" value="13" checked>
					<label for="check-13">13</label>
				</div>
				<div class="option">
					<input type="checkbox" id="check-20" name="20" value="20" checked>
					<label for="check-20">20</label>
				</div>
				<div class="option">
					<input type="checkbox" id="check-40" name="40" value="40" checked>
					<label for="check-40">40</label>
				</div>
				<div class="option">
					<input type="checkbox" id="check-100" name="100" value="100" checked>
					<label for="check-100">100</label>
				</div>
			</div>
		</div>
		<div class="section">
			<div class="section-title">Card backs</div>
			<div class="section-content">
				<div class="card-list">
					<div>
						<div class="card waves" v-on:click="setCardBack('waves')"></div>
						<div class="card-desc">
							Waves
							<i v-if="cardBack === 'waves'" class="far fa-check-circle"></i>
						</div>
					</div>
					<div>
						<div class="card circuit-board" v-on:click="setCardBack('circuit-board')"></div>
						<div class="card-desc">
							Circuit
							<i v-if="cardBack === 'circuit-board'" class="far fa-check-circle"></i>
						</div>
					</div>
					<div>
						<div class="card bees" v-on:click="setCardBack('bees')"></div>
						<div class="card-desc">
							Bees?
							<i v-if="cardBack === 'bees'" class="far fa-check-circle"></i>
						</div>
					</div>
					<div>
						<div class="card fancy" v-on:click="setCardBack('fancy')"></div>
						<div class="card-desc">
							Fancy
							<i v-if="cardBack === 'fancy'" class="far fa-check-circle"></i>
						</div>
					</div>
					<div>
						<div class="card snacks" v-on:click="setCardBack('snacks')"></div>
						<div class="card-desc">
							Snacks!
							<i v-if="cardBack === 'snacks'" class="far fa-check-circle"></i>
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
	        cardBack: null
	    }
	},
	methods: {
		setCardBack: function (card) {
		  	localStorage.setItem('cardBack', card);
		  	this.cardBack = card;
		}
	},
    mounted() {
      if (localStorage.getItem('cardBack')) this.cardBack = localStorage.getItem('cardBack');
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
