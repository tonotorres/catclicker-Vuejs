<template>
  <div class="cat-card" v-on:click="showCatDescription()">
    <div class="card-content">
      <img class="cat-image" :src="catImage">
    </div>
    <div class="breed-click">
      <ul>
        <li>
          <span>{{cat.name}}</span>
        </li>
        <li>
          <span class="clics"> {{cat.n_clics}}</span>
        </li>
      </ul>
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'CatCard',
  props: {
    cat: Object
  },
  data () {
    return {
      audio: new Audio(require('../assets/sounds/meow.mp3'))
    }
  },
  computed :{
    catImage: function() {
      return require('../assets/images/' + this.cat.foto +  '.jpg')
    }
  },
  methods: {
    showCatDescription(){
      this.audio.play()
      this.$emit('catDescription', this.cat)
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

ul {
  height: 100%;
  padding-left: 2%;
}
ul li {
  list-style-type: none;
}
.cat-card {
  height: 25%;
  width: 90%;
  background-color: rgb(255, 255, 255);
  margin-left: auto;
  margin-right: auto;
  margin-top: 10px;
  border-top-right-radius: 25px;
  border-bottom-right-radius: 25px;
  display: flex;
  color: black;
}
.cat-card:hover {
  background-color: #1b55a7;
  border: 1px;
  border-color: #2971a3;
  border-style: solid;
  color: white;
  cursor: pointer;
}
.card-content {
  overflow: hidden;
}
.breed-click {
  margin: auto;
  font-family: 'Courier New', Courier, monospace;
  height: 100%;
  text-align: center;
  margin-top: 5%;
}
.clics {
  font-size: 50px;
}
.cat-image {
  max-width:100%;
  max-height:100%;
  transform:scale(1.5);

}
</style>
