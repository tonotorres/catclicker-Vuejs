<template>
    <div class="cat-manager">
        <div class="container-fluid">
            <div class="row">
                <div class="col">
                    <cat-breeds :cats="cats" @catDescription="catDescription($event)"/>
                </div>
                <div class="col-1">
                    
                </div>
                <div class="col">
                    <cat-description :cat="catShow"/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

import CatBreeds from './CatBreeds.vue'
import CatDescription from './CatDescription.vue'

export default {
    
    name: 'CatManager',
    props: {
        msg: String
    },
    components: {
        CatBreeds,
        CatDescription
    },
    data () {
      return {
          catShow: {name: 'Chartreux Cat Breed', foto: 'chartreux', n_clics: 0, sound: '', description: 'Often called the smiling cat of France, the Chartreux has a sweet, smiling expression. This sturdy, powerful cat has a distinctive blue coat with a resilient wooly undercoat. Historically known as fine mousers with strong hunting instincts, the Chartreux enjoys toys that move. This is a slow-maturing breed that reaches adulthood in three to five years. A loving, gentle companion, the Chartreux forms a close bond with her family.'},
          cats: [
              {name: 'Chartreux Cat Breed', foto: 'chartreux', n_clics: 0, sound: '', description: 'Often called the smiling cat of France, the Chartreux has a sweet, smiling expression. This sturdy, powerful cat has a distinctive blue coat with a resilient wooly undercoat. Historically known as fine mousers with strong hunting instincts, the Chartreux enjoys toys that move. This is a slow-maturing breed that reaches adulthood in three to five years. A loving, gentle companion, the Chartreux forms a close bond with her family.'},
              {name: 'Bombay Cat', foto: 'bombay', n_clics: 0, sound: '', description: 'The Bombay is an easy-going, yet energetic cat. She does well in quiet apartments where she’s the center of attention as well as in lively homes with children and other pets. She’ll talk to you in a distinct voice, and you’re likely to find her in the warmest spot in your home, whether that’s in the sunlight from a window or curled up under the covers in bed with you.'},
              {name: 'Bengal Cat', foto: 'bengal', n_clics: 0, sound: '', description: 'Bengal Cats are curious and confident with the tameness of a domestic tabby and the beauty of an Asian Leopard Cat. Learn more about Bengals and their playful personality, plus information on their health and how to feed them.'},
              {name: 'Exotic Shorthair Cat Breed', foto: 'exotic', n_clics: 0, sound: '', description: 'Known as the lazy man’s Persian, the Exotic Shorthair has the body type and easygoing nature of the Persian but without the coat length and need for daily grooming.'},
              {name: 'Ragdoll Cat Breed', foto: 'ragdoll', n_clics: 0, sound: '', description: 'Ragdolls are loving, smart and playful. They show affection to their people by greeting them, following them around, sitting in their laps and snuggling in bed. Ragdoll cats can also learn tricks and certain behaviors with positive reinforcement.'},
              {name: 'Savannah Cat Breed', foto: 'savana', n_clics: 0, sound: '', description: 'The Savannah Cat’s personality is playful, adventurous and loyal. Unlike most cats, she loves to play in water and can even be trained to walk on a leash and play fetch. Don’t be fooled by her dog-like personality, though.'},
              {name: 'Toyger Cat Breed', foto: 'toyger', n_clics: 0, sound: '', description: 'With her beautiful bold stripes and powerful body, the Toyger looks like a jungle tiger. This breed has a friendly, outgoing temperament and delights in being with people, even strangers, and gets along well with other pets. Highly intelligent, the Toyger is easy to train to go on leash walks and to play fetch. The Toyger is generally robust and healthy.'},
              {name: 'Siberian Cat Breed', foto: 'siberian', n_clics: 0, sound: '', description: 'This friendly and affectionate feline will follow you around as you go about your day, and purr in your lap as you comb her coat. Siberian Cats love their humans but aren’t shy around strangers.'},
          ]
      }
    },
    methods: {
        catDescription(cat) {
            let cat_update = this.cats.findIndex(x => x.name === cat.name);
            this.cats[cat_update].n_clics = this.cats[cat_update].n_clics + 1;
            this.catShow = this.cats[cat_update];
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.cat-manager {
    color: white;
    text-align: center;
    margin-top: 3%;
    height: 75vh;
}
.container-fluid {
    height: 100% !important;
}
.row {
    height: 100%;
}
.col {
    margin-left: 3%;
    margin-right: 3%;
    height: 100%;
}
</style>
