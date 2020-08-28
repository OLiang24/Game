<<<<<<< HEAD
<template>
<div>
    <button v-on:click="Start()" class="button-a btn btn-outline-info " id="start">Start</button>
    <button v-on:click="Attack()" class="button-a btn btn-outline-success" id="atk">Attack</button> 
    <button v-on:click="Special()" class="button-a btn btn-outline-danger" id="atk">Special Attack</button>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      //     aplayer: { name: " player", hp: 1000, image: "" },
      //     amonster: { name: "monster", hp: 1000, image: "" },
      player: [
        { name: "Red", hp: 200, image: require("../assets/img/red.png") },
        { name: "Chuck ", hp: 225, image: require("../assets/img/chuck.png") },
        { name: "Bomb", hp: 250, image: require("../assets/img/bomb.png") },
        { name: "Matilda", hp: 275, image: require("../assets/img/matilda.png") },
        { name: "Terence", hp: 300, image: require("../assets/img/terence.png") },
      ],

      monster: [
        { name: "pigs", hp: 200, image: require("../assets/img/pig.png") },
        { name: "fermale pigs", hp: 225, image: require("../assets/img/female.png") },
        { name: "armor pigs", hp: 250, image: require("../assets/img/armor.png") },
        { name: "mushed pigs", hp: 275, image: require("../assets/img/mushed.png") },
        { name: "king pigs", hp: 300, image: require("../assets/img/king.png") },
      ],
    };
  },
  methods: {
    randomm: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },

    Start: function () {
      //1.random player 1-3
      //2.random monster 1-3
      this.randomB = this.randomm(1, 5) - 1;
      this.randomP = this.randomm(1, 5) - 1;

      //สุ่มค่า player 1-5 --->ชื่อ ค่า hp รูป
      this.name_player = this.player[this.randomB].name;
      this.$emit("B_name", this.name_player);
      console.log("emit", this.name_player);

      this.hp_player = this.player[this.randomB].hp;
      this.$emit("B_hp", this.hp_player);
      console.log("hp", this.hp_player);

      this.image_player = this.player[this.randomB].image;
      this.$emit("B_image", this.image_player);
      console.log("im", this.image_player);

      //สุ่มค่า Monster 1-5 --->ชื่อ ค่า hp รูป
      this.name_monster = this.monster[this.randomP].name;
      console.log("emit", this.name_monster);
      this.$emit("P_name", this.name_monster);

      this.hp_monster = this.monster[this.randomP].hp;
      this.$emit("P_hp", this.hp_monster);

      this.image_monster = this.monster[this.randomP].image;
      this.$emit("P_image", this.image_monster);
    },

    Attack: function () {
      //1.player --> monster
      this.atk = this.randomm(5, 15);
      this.$emit("B_atk", this.atk);
      console.log("Attack :", this.atk);

      this.atk = this.randomm(5, 15);
      this.$emit("P_atk", this.atk);
      console.log("Atk back", this.atk);

      //3.player.HP <=0 ===>!
      //4.monster.HP <=0 ===>!
      //5.END GAME
    },
    Special: function () {
      this.s_atk = this.randomm(20, 50);
      this.$emit("B_SATK", this.s_atk);
      console.log("Special Attack :", this.s_atk);

      //2.player <-- monster
      this.s_atk = this.randomm(20, 50);
      this.$emit("P_SATK", this.s_atk);
      console.log("SPATK back :", this.s_atk);
    },
  },
};
</script>
<style >
.f {
  font-size: 50px;
}

.button-a {
  font-size: 20px;
  background-color: #f5dbab;
  border: rgb(238, 25, 149);
  padding: 10px 10px 10px 10px;
  text-align: center;
  display: inline-block;
  margin: 20px 10px;
}
</style>
=======
<template>
    <div>
        <p>HP Player {{ randomNo(1,3) }} 
            {{ player[randomNo(1,3)-1].name }}
        </p> 
        <img src="" alt="รูป">
        <hr />
            name = {{ aPlayer.name }}
            hp = {{ aPlayer.hp }}
            image = {{ aPlayer.image }}
        <hr />
        <p>HP Monster 150</p> 
        +รูป
        <button @click="start()" >Start</button>
        <button @click="attack()">Attack</button>
    </div>
</template>
<script>
export default {
    data:function(){
        return {
            aPlayer: {name: '' ,hp: 0 , image:'' },
            // ชื่อ player[1].name
            player : [ 
                {name: 'Naruta' ,hp: 90 , image:'a' }, 
                {name: 'kakashi' ,hp: 150 ,image:'b' }, 
                {name: 'Gaara' ,hp: 200 ,image:'' }
            ],
            monster : [
                {name: 'sa' , hp: 300 ,image:'x' },
                {name: 'sw' , hp: 500 ,image:'y' },
                {name: 'se' , hp: 100 ,image:'z' }
            ],
        };
    },
    methods:{
        randomNo: function(min, max){
            return Math.max(Math.floor(Math.random() * max) + 1, min)
        },
        start:function(){
            // 1. random Palyer 1-3 --> ชื่อ hp รูป
            this.aPlayer = this.player[this.randomNo(1, 3) - 1] 
            // {....}

            
            // 2. random Monster 1-3 --> 
        },
        attack:function(){
            // 1. playyer --> monster
            // 2. player <-- monster
            // 3. hP? <=0 ===> ?
            // 4. monster.HP <==0 ===> ?
            // 5. END GAME
        },
    },
}
</script>
<style></style>
>>>>>>> 5c5189ef2632575a81c02a015a7ea14cb026ad0f
