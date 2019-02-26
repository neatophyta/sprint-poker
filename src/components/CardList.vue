<template>
	<div class="card-wrapper">
		<div class="card-controls">
			<a v-on:click="flip" class="link-button" href="#">Flip</a>
		</div>
		<div class="card-list">
			<div class="card" v-for="card in cards" :key="card.id">
				<div class="front face" v-bind:class="[flipped ? '' : 'hidden']"> {{ card.score }} </div>
				<div class="back face" v-bind:class="[flipped ? 'hidden' : '', cardBack]"></div>
				<div class="label"> {{ card.name }} </div>
			</div>
		</div>
	</div>
</template>

<script>

export default {
	name: 'CardList',
    props: {
        cards: Array
    },
	data: function () {
	    return {
	        flipped: false,
            cardBack: 'waves'
	    }
	},
	methods: {
		flip: function () {
		  	this.flipped = !this.flipped;
		}
	},
    mounted() {
      if (localStorage.getItem('cardBack')) this.cardBack = localStorage.getItem('cardBack');
    }
}
</script>

<style scoped>
	.card-controls {
		margin: 20px 0;
	}

	.card-list {
		display: flex;
		margin-bottom: 20px;
	}

	.card {
		height: 170px;
		margin: 10px;
		position: relative;
	    width: 100px;
	    text-align: center;
	}

	.card .face {
	    border-radius: 6px;
	    font-size: 3em;
	    height: 140px;
	    line-height: 140px;
	    width: 100px;

	    position: absolute;

	    transition: transform 1s;
	    -webkit-backface-visibility: hidden;
	    backface-visibility: hidden;
	}

    .card .face.front {
        background-color: #fff;
        border: 2px solid;
    }

	.card .face.hidden {
		-webkit-transform: translateZ(-260px) rotateY(-180deg);
	            transform: translateZ(-260px) rotateY(-180deg);
	}

	.card .label {
		position: absolute;
		top: 150px;
		width: 100%;
	}
</style>
