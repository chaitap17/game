<template>
  <div>
  <div class="container">
    <img src="../assets/btn1.png" alt="start" style="width:60%">
    <button @click="randomStart()" class="btn btn-danger"> Start </button><br><br>
  </div>
  <hr>
    <div class="container-fluid">
      <div class="row">
      
        <div class="col-4">
          <div class="alert w3-button w3-indigo" role="alert" > Hero : {{randomPlayer}} HP : {{hp1}} </div> 
          <img :src="image1" width="80%" class="img-fluid" />
        </div>
        <div class="col-4">
          <img src="../assets/3.png" alt="รูป" width="100%" >
        </div>
        <div class="col-4">
          <div class="alert w3-button w3-red"  role="alert"> Monster : {{randomMonster}} HP : {{hp2}} </div> 
          <img :src="image2" width="80%" class="img-fluid" />
        </div>
      </div>
    </div>

    <div class="container-attack">
    <div class="row ">
      <div class="col">
        <img src="../assets/btn1.png" alt="Attack" style="width:100%">
        <button @click="randomDamage(1,30)" class="btn">  Attack  </button>
      </div>
      <div class="col">  
        <img src="../assets/btn1.png" alt="SP Attack" style="width:100%">
        <button @click="randomDamageSP(40,70)" class="btn">  SP Attack  </button>
      </div >
    </div>
  </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      randomAttack: "./assets/img/a1.png",
      randomSpAttack: "",
      image1: "",
      image2: "",
      hp1: "",
      hp2: "",
      win: "./assets/img/10.png", 
      lose: "./assets/img/11.png", 
      
      player: [
        {
          name: "Iron man",
          hp: 300,
          image: "./assets/img/h1.png",
        },
        {
          name: "Groot",
          hp: 250,
          image: "./assets/img/h2.png",
        },
        {
          name: "Docter strange",
          hp: 400,
          image: "./assets/img/h3.png",
        },
      ],
      randomPlayer: "",
      monster: [
        {
          name: "The Green Goblin",
          hp: 450,
          image: "./assets/img/a1.png",
        },
        {
          name: "Loki",
          hp: 250,
          image: "./assets/img/a2.png",
        },
        {
          name: "Magneto",
          hp: 350,
          image: "./assets/img/a3.png",
        },
      ],
      randomMonster: "",
    };
  },

  methods: {
    randomStart: function () {
      var chosenNumber1 = Math.floor(Math.random() * this.player.length);
      this.randomPlayer = this.player[chosenNumber1].name;
      this.hp1 = this.player[chosenNumber1].hp;
      this.image1 = this.player[chosenNumber1].image;

      var chosenNumber2 = Math.floor(Math.random() * this.monster.length);
      this.randomMonster = this.monster[chosenNumber2].name;
      this.hp2 = this.monster[chosenNumber2].hp;
      this.image2 = this.monster[chosenNumber2].image;
    },

    randomDamage: function (min, max) {
      this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp1 -= this.randomAttack;
      }
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp2 -= this.randomAttack;
      }
      if (this.hp1 <= 0) {
        this.hp1 = 0;
        this.image2 = this.win;
        this.image1 = this.lose;

      }
      if (this.hp2 <= 0) {
        this.hp2 = 0;
        this.image2 = this.lose;
        this.image1 = this.win;
      }
    },

    randomDamageSP: function (min, max) {
      this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp2 -= this.randomAttack;
      }
      if (this.hp1 <= 0) {
        this.hp1 = 0;
        this.image2 = this.win;
        this.image1 = this.lose;
      }
      if (this.hp2 <= 0) {
        this.hp2 = 0;
        this.image2 = this.lose;
        this.image1 = this.win;
      }
    },
  },
};
</script>

<style>
.container {
  position: relative;
  width: 100%;
  max-width: 400px;
}

.container img {
  width: 100%;
  height: auto;
}

.container .btn {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  color: rgb(255, 0, 0);
  font-size: 40px;
  padding: 12px 24px;
  border: none;
  cursor: pointer;
  border-radius: 5px;
  text-align: center;
}

.container-attack {
  position: relative;
  width: 100%;
  max-width: 400px;
  left: 35%;
}

.container-attack img {
  width: 100%;
  height: auto;
}  

.container-attack .btn {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  color: white;
  font-size: 35px;
  padding: 12px 24px;
  border: none;
  cursor: pointer;
  border-radius: 5px;
  text-align: center;
}

.container-fluid{
  font-size: 20px;
}


</style>