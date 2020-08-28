<template>
  <div id="app" class="playGameScreen">

      <div class="row a">

        <div class="col-md-5 ">
          <br>
          <h1>{{bird_name}}  HP ; {{bird_hp}}</h1>
          <div class="heroTile tile">
            <img :src="b_img" alt class="img-fluid image" :width="bird_hp + 'px'" />
          </div>
        </div>
        <div class="col-md-2 ">
          <h1><img src="./assets/img/vs.png" alt="" width="100%"></h1>
        </div>
        <div class="col-md-5">
        <br>
          <h1>{{pig_name}}  HP ; {{pig_hp}}</h1>
          <div class="enemyTile tile">
            <img :src="p_img" alt class="img-fluid image" :width="pig_hp + 'px'" />
          </div>
        </div>
      </div>

      <game
        @B_name="b_name"
        @B_hp="b_hp"
        @B_image="b_image"
        @P_name="p_name"
        @P_hp="p_hp"
        @P_image="p_image"
        @B_atk="b_atk"
        @P_atk="p_atk"
        @B_SATK="b_satk"
        @P_SATK="p_satk"
      ></game>

  </div>
</template>
<script>
// import HelloWorld from './components/HelloWorld.vue'
import game from "./components/game";
export default {
  name: "App",
  components: {
    game,
  },
  data: function () {
    return {
      bird_name: "",
      pig_name: "",
      bird_hp: 0,
      pig_hp: 0,
      attack: 0,
      b_img: "",
      p_img: "",
    };
  },
  methods: {
    //hero
    b_name(value) {
      this.bird_name = value;
      console.log("emit", this.bird_name);
    },
    b_hp(value) {
      this.bird_hp = value;
      console.log("emit", this.bird_hp);
    },
    b_image(value) {
      this.b_img = value;
      console.log("emit", this.b_img);
    },

    // Mon
    p_name(value) {
      this.pig_name = value;
    },
    p_hp(value) {
      this.pig_hp = value;
      
    },
    p_image(value) {
      this.p_img = value;
      

    },
    //Attack hero
    b_atk(value) {
      this.attack = value;
      this.pig_hp -= this.attack;
      console.log("emit", this.pig_hp);
    },
    b_satk(value) {
      this.attack = value;
      this.pig_hp -= this.attack;
    },
    //Attack mon
    p_atk(value) {
      this.attack = value;
      this.bird_hp -= this.attack;
    },

    p_satk(value) {
      this.attack = value;
      this.bird_hp -= this.attack;
    },
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.playGameScreen {
  background-image: url("assets/img/bg.jpg");
  background-repeat: no-repeat;
  background-size: 100% 100%;
}
.a {
  color: rgb(255, 64, 143);
  font-family: 'Lobster', cursive;
  margin: auto;
  width: 90%;
  height: 650px;
}
.tiles {
  position: absolute;
  bottom: 5%;
  width: 100%;
}
.tile {
  display: inline-block;
  margin: 5px;
  bottom: 0;
}
.heroTile {
  float: center;
}
.enemyTile {
  float: bottom;
}
</style>