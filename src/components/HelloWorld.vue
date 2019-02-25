<template>
    <div class="content">
      <div class="card-wrapper">
        <div class="card-controls">
          <a id="flip" class="link-button" href="#">Flip</a>
        </div>
        <div class="card-list">
          <div class="card">
            <div class="front face hidden"> 5 </div>
            <div class="back face"></div>
            <div class="label">Charli</div>
          </div>
          <div class="card">
            <div class="front face hidden"> 3 </div>
            <div class="back face"></div>
            <div class="label">Charli 1</div>
          </div>
          <div class="card">
            <div class="front face hidden"> 2 </div>
            <div class="back face"></div>
            <div class="label">Charli 2</div>
          </div>
          <div class="card">
            <div class="front face hidden"> 3 </div>
            <div class="back face"></div>
            <div class="label">Charli 3</div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
