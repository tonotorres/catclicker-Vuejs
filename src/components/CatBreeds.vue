<template>
    <div class="cat-breeds">
        <h1 class="title sub-title">Razas</h1>
        <div class="cat-breeds-info" >
            <div v-for="cat in cats" v-bind:key="cat.name">
                <CatCard :cat="cat" @catDescription="catDescription($event)"/>
            </div>
        </div>
    </div>
</template>

<script>
import CatCard from './CatCard.vue'

export default {
  name: 'CatManager',
  props: {
    cats: Array
  },
  components: {
      CatCard
  },
  methods: {
    catDescription(cat){
      this.$emit('catDescription', cat)
    }
  }
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
    
    background-color: rgba(255, 255, 255, 0.603);
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
}
.cat-breeds-info::-webkit-scrollbar {
    display: none;
}
.sub-title {
    padding: 0;
}
</style>
