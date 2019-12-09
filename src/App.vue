<template>
  <div id="app">
    <!--bind the title data in app.vue with title data in title component -->
    <Title :title="title" />
    <!--bind the clickedAnimal data in app.vue with clickedAnimal data in intro component -->
    <Intro :clickedAnimal="clickedAnimal" />
    <!--bind the imagesArray data in app.vue with imagesArray data in tile component -->
    <Tile @speciesClick="getSpecies" :imagesArray="imagesArray" />
    <!--bind the historyImages data in app.vue with historyImages data in history component -->
    <History :historyImages="historyImages" @historyClick="makeSound"/>
    <Footer />
  </div>
</template>

<script>
  let myaudio = new Audio(require('./assets/audio/blueWhale.mp3'));
  // import HelloWorld from './components/HelloWorld.vue'
  import Title from './components/Header.vue'
  import Intro from './components/Desc.vue'
  import Tile from './components/Tile.vue'
  import History from './components/History.vue'
  import Footer from './components/Footer.vue'

  export default {
    name: 'app',
    components: {
      Title,
      Intro,
      Tile,
      History,
      Footer
    },

    data() {
      return {
        title: "KIDS' AQUARIUM",
        imagesArray: [{
            imgsrc: require('./assets/blueWhale.png')
          },
          {
            imgsrc: require('./assets/dolphin.png')
          },
          {
            imgsrc: require('./assets/hippo.png')
          },
          {
            imgsrc: require('./assets/jellyfish.png')
          },
          {
            imgsrc: require('./assets/octopus.png')
          },
          {
            imgsrc: require('./assets/seaLion.png')
          },
          {
            imgsrc: require('./assets/shark.png')
          },
          {
            imgsrc: require('./assets/squid.png')
          },
          {
            imgsrc: require('./assets/turtle.png')
          }
        ],
        historyImages: [

        ],

        animalCards: [{
            name: "Whale",
            desc: "Whales are a widely distributed and diverse group of fully aquatic placental marine mammals. They are an informal grouping within the infraorder Cetacea, usually excluding dolphins and porpoises. Whales are a widely distributed and diverse group of fully aquatic placental marine mammals. Whales are creatures of the open ocean."
          },
          { 
            name: "Dolphin",
            desc: "Dolphin is a common name of aquatic mammals ,they range in size from the 1.7 m (5.6 ft) long and 50 kg (110 lb) Maui's dolphin to the 9.5 m (31 ft) and 10 t (11 short tons) killer whale.Although dolphins are widespread, most species prefer the warmer waters of the tropic zones, but some, like the right whale dolphin, prefer colder climates."
          },
          {
            name: "Hippo",
            desc: "The common hippopotamus or hippo, is a large, mostly herbivorous, semiaquatic mammal and ungulate native to sub-Saharan Africa.The common hippo inhabits rivers, lakes and mangrove swamps, where territorial bulls preside over a stretch of river and groups of five to thirty females and young. "
          },
          {
            name: "Jellyfish",
            desc: "Jellyfish are mainly free-swimming marine animals with umbrella-shaped bells and trailing tentacles, although a few are not mobile, being anchored to the seabed by stalks.Jellyfish are found all over the world, from surface waters to the deep sea. Scyphozoans are exclusively marine, but some hydrozoans with a similar appearance live in freshwater."
          },
          { 
            name: "Octopus",
            desc: "The octopus (plural octopuses) is a soft-bodied, eight-limbed mollusc of the order Octopoda. Around 300 species are recognised, and the order is grouped within the class Cephalopoda with squids. Octopuses inhabit various regions of the ocean, including coral reefs, pelagic waters, and the seabed; some live in the intertidal zone and others at abyssal depths. "
          },
          {
            name: "Sealion",
            desc: "Sea lions are pinnipeds characterized by external ear flaps, long foreflippers, the ability to walk on all fours, short, thick hair, and a big chest and belly.Sea lions are related to walruses and seals. Together with the fur seals, they constitute the family Otariidae, collectively known as eared seals. "
          },
          { 
            name: "Shark",
            desc: "Sharks are a group of elasmobranch fish characterized by a cartilaginous skeleton, five to seven gill slits on the sides of the head, and pectoral fins that are not fused to the head.Under this broader definition, the earliest known sharks date back to more than 420 million years ago. Acanthodians are often referred to as spiny sharks"
          },
          {
            name: "Squid",
            desc: "Squid are cephalopods in the superorder Decapodiformes with elongated bodies, large eyes, eight arms and two tentacles. Squid can change colour for camouflage and signalling. Some species are bioluminescent, using their light for counter-illumination camouflage, while many species can eject a cloud of ink to distract predators"
          },
          {
            name: "Turtle",
            desc: "Turtles are reptiles of the order Testudines characterized by a special bony or cartilaginous shell developed from their ribs and acting as a shield. Turtles are ectotherms—animals commonly called cold-blooded—meaning that their internal temperature varies according to the ambient environment."
          },
        ],
        clickedAnimal: []
      }
    },

    methods: {
      getSpecies(value, index) {
        this.clickedAnimal.pop();
        this.clickedAnimal.push(this.animalCards[index]);

        this.historyImages.unshift({
          src:value,
          number:index
        });
        if (this.historyImages.length > 10) {
          this.historyImages.pop();
          this.historyImages.unshift();
        }
        
        if (index == 0) {
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/blueWhale.mp3'));
          myaudio.play();
        }else if(index == 1){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/dolphin.mp3'));
          myaudio.play();
        }else if(index == 2){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/hippo.mp3'));
          myaudio.play();
        }else if(index == 3){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/jellyfish.mp3'));
          myaudio.play();
        }else if(index == 4){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/octopus.mp3'));
          myaudio.play();
        }else if(index == 5){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/seaLion.mp3'));
          myaudio.play();
        }else if(index == 6){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/shark.mp3'));
          myaudio.play();
        }else if(index == 7){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/squid.mp3'));
          myaudio.play();
        }else if(index == 8){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/turtle.mp3'));
          myaudio.play();
        }


      },
      
      makeSound(index){
        if (index == 0) {
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/blueWhale.mp3'));
          myaudio.play();
        }else if(index == 1){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/dolphin.mp3'));
          myaudio.play();
        }else if(index == 2){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/hippo.mp3'));
          myaudio.play();
        }else if(index == 3){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/jellyfish.mp3'));
          myaudio.play();
        }else if(index == 4){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/octopus.mp3'));
          myaudio.play();
        }else if(index == 5){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/seaLion.mp3'));
          myaudio.play();
        }else if(index == 6){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/shark.mp3'));
          myaudio.play();
        }else if(index == 7){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/squid.mp3'));
          myaudio.play();
        }else if(index == 8){
          myaudio.pause();
          myaudio = new Audio(require('./assets/audio/turtle.mp3'));
          myaudio.play();
        }
      }


    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
    margin: 0;
    padding: 0;

  }
</style>