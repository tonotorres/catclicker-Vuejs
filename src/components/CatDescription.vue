<template>
    <div class="cat-breeds">
        <h1 class="title sub-title">Descripción</h1>
        <div id="cat" class="cat-breeds-info">
            <div class="row">
                <div class="col">
                    <h1 class="title-description">{{cat.name}}</h1>
                </div>
            </div>
            <div class="row">
                <div class="col">
                    <img class="cat-image" :src="catImage">
                </div>
                <div class="col clics">
                    <span class="n-clics">N clicks: {{cat.n_clics}}</span>
                </div>
            </div>
            <div class="row">
                <div class="col description">
                    <span class="description">{{cat.description}}</span>
                </div>
            </div>
            
            
            
        </div>
    </div>
</template>

<script>

export default {
  name: 'CatDescription',
  props: {
    cat: Object
  },
  watch: {
      cat(){
      }
  },
  components: {
  },
  computed :{
    catImage: function() {
      return require('../assets/images/' + this.cat.foto +  '.jpg')
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.cat-breeds {
    background-color: rgba(255, 255, 255, 0.425);
    height: 100%;
    max-height: 100%;
    text-align: center;
    border-radius: 5px;
    padding-top: 2%;
    padding-bottom: 2%;
    box-shadow: 0px 0px 80px 20px rgba(255, 255, 255, 0.514);
    overflow: hidden;
}
.cat-breeds:hover{
    background-color: rgba(255, 255, 255, 0.637);
}
.cat-breeds-info {
    background-color: rgb(255, 255, 255);
    color: black;
    height: 94%;
    width: 95%;
    margin: auto;
    border-radius: 5px;
    border: 1px;
    border-color: rgb(150, 150, 150);
    border-style: solid;
    -ms-overflow-style: none; /* for Internet Explorer, Edge */
    scrollbar-width: none; /* for Firefox */
    overflow-y: scroll;
    font-family: 'Courier New', Courier, monospace;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
}
.cat-breeds-info::-webkit-scrollbar {
    display: none;
}
.title-description {
    padding-top: 10px;
    color: black;
}
.clics {
    margin: auto;
    width: 50%;
}
.n-clics{
    font-size: 30px;
}
.description {
    padding-right: 5%;
    padding-left: 5%;
}
.sub-title {
    padding: 0;
}
</style>
