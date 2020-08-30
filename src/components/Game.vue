<template>
<div>
    <div class="container">
      <img src="../assets/btn1.png" alt="start" style="width:100%">
      <button @click="start()" class="btn"> START </button>
    </div>

    <div class="container-attack">
      <div class="row">
        <div class="col-6">
          <img src="../assets/btn2.png" alt="Attack" style="width:100%">
          <button @click="attack(50,25)" class="btn"> ATTACK </button>
        </div>
        <div class="col-6">  
          <img src="../assets/btn3.png" alt="SP Attack" style="width:100%">
          <button @click="SPattack(35,70)" class="btn">SP ATTACK </button>
        </div >
      </div>
    </div>

    <div class="container-fluid">
      <div class="row">
        <div class="col-4">
          <div class="alert alert-primary" role="alert">
            <svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-life-preserver" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" d="M14.43 10.772l-2.788-1.115a4.015 4.015 0 0 1-1.985 1.985l1.115 2.788a7.025 7.025 0 0 0 3.658-3.658zM5.228 14.43l1.115-2.788a4.015 4.015 0 0 1-1.985-1.985L1.57 10.772a7.025 7.025 0 0 0 3.658 3.658zm9.202-9.202a7.025 7.025 0 0 0-3.658-3.658L9.657 4.358a4.015 4.015 0 0 1 1.985 1.985l2.788-1.115zm-8.087-.87L5.228 1.57A7.025 7.025 0 0 0 1.57 5.228l2.788 1.115a4.015 4.015 0 0 1 1.985-1.985zM8 16A8 8 0 1 0 8 0a8 8 0 0 0 0 16zm0-5a3 3 0 1 0 0-6 3 3 0 0 0 0 6z"/>
            </svg> Hero : {{randomPlayer}} </div> 
          <img :src="image1" width="75%" class="img-fluid" /><br><br>
          <div class="alert alert-primary" role="alert">
            <svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-lightning-fill" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" d="M11.251.068a.5.5 0 0 1 .227.58L9.677 6.5H13a.5.5 0 0 1 .364.843l-8 8.5a.5.5 0 0 1-.842-.49L6.323 9.5H3a.5.5 0 0 1-.364-.843l8-8.5a.5.5 0 0 1 .615-.09z"/>
            </svg> HP : {{hp1}} 
            </div> 
        </div>
        <div class="col-4">
           <img src="../assets/vs.png" alt="vs"  width="100%">
        </div>
        <div class="col-4">
          <div class="alert alert-primary" role="alert">
            <svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-life-preserver" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" d="M14.43 10.772l-2.788-1.115a4.015 4.015 0 0 1-1.985 1.985l1.115 2.788a7.025 7.025 0 0 0 3.658-3.658zM5.228 14.43l1.115-2.788a4.015 4.015 0 0 1-1.985-1.985L1.57 10.772a7.025 7.025 0 0 0 3.658 3.658zm9.202-9.202a7.025 7.025 0 0 0-3.658-3.658L9.657 4.358a4.015 4.015 0 0 1 1.985 1.985l2.788-1.115zm-8.087-.87L5.228 1.57A7.025 7.025 0 0 0 1.57 5.228l2.788 1.115a4.015 4.015 0 0 1 1.985-1.985zM8 16A8 8 0 1 0 8 0a8 8 0 0 0 0 16zm0-5a3 3 0 1 0 0-6 3 3 0 0 0 0 6z"/>
            </svg> Hero : {{randomMonster}} </div>
          <img :src="image2" width="75%" class="img-fluid" /><br><br>
          <div class="alert alert-primary" role="alert">
            <svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-lightning-fill" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" d="M11.251.068a.5.5 0 0 1 .227.58L9.677 6.5H13a.5.5 0 0 1 .364.843l-8 8.5a.5.5 0 0 1-.842-.49L6.323 9.5H3a.5.5 0 0 1-.364-.843l8-8.5a.5.5 0 0 1 .615-.09z"/>
            </svg> HP : {{hp2}} </div>
        </div> 
      </div>  
  </div>

</div>
</template>

<script>

export default {
    data:function(){
        return {
            randomAttack: "",
            randomSpAttack: "",
            image1: "",
            image2: "",
            hp1: "",
            hp2: "",
            win: "./assets/img/win.png", //เปลี่ยน ที่อยู่รูป win
            lose: "./assets/img/lose.png", //เปลี่ยน ที่อยู่รูป lose
            // ชื่อ player[1].name
            player : [ 
                {name: "NARUTO" , hp: 300 , image: "./assets/img/h1.png" }, 
                {name: "SAGE" , hp: 210 , image: "./assets/img/h2.png" }, 
                {name: "GAARA", hp: 260 , image: "./assets/img/h3.png" },
                {name: "KILJOY" , hp: 320 , image:  "./assets/img/h4.png" },
            ],
            randomPlayer: "",
            monster : [
                {name: "JETT" , hp: 350 , image: "./assets/img/a1.png" },
                {name: "KAKASHI" , hp: 310 , image: "./assets/img/a2.png" },
                {name: "RAZE" , hp: 220 , image: "./assets/img/a3.png" },
                {name: "SASUKE" , hp: 250 , image: "./assets/img/a4.png" },
            ],
            randomMonster: "",
        };
    },


    methods:{
        start:function(){
            // 1. random Palyer 1-4 --> ชื่อ hp รูป
            var chosenNumber1 = Math.floor(Math.random() * this.player.length);
            this.randomPlayer = this.player[chosenNumber1].name;
            this.hp1 = this.player[chosenNumber1].hp;
            this.image1 = this.player[chosenNumber1].image;
            

            // 2. random Monster 1-4 --> 
            var chosenNumber2 = Math.floor(Math.random() * this.monster.length);
            this.randomMonster = this.monster[chosenNumber2].name;
            this.hp2 = this.monster[chosenNumber2].hp;
            this.image2 = this.monster[chosenNumber2].image;
        },

        attack:function (min, max) {
            // 1. playyer --> monster
            this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
            if (this.hp1 != 0 && this.hp2 != 0) {
                this.hp1 -= this.randomAttack;
            }
            // 2. player <-- monster
            if (this.hp1 != 0 && this.hp2 != 0) {
                this.hp2 -= this.randomAttack;
            }
            // 3. hP? <=0 ===> ?
            if (this.hp1 <= 0) {
                this.hp1 = 0;
                this.image2 = this.win;
                this.image1 = this.lose;
            }
            // 4. monster.HP <==0 ===> ?
            if (this.hp2 <= 0) {
                this.hp2 = 0;
                this.image2 = this.lose;
                this.image1 = this.win;
            }
            // 5. END GAME
        },

        SPattack: function (min, max) {
            this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
            if (this.hp1 != 0 && this.hp2 != 0) {
                this.hp2 -= this.randomAttack;
            }
            if (this.hp1 <= 0) {
                this.hp1 = 0;
                this.image1 = this.lose;
                this.image2 = this.win;
            }
            if (this.hp2 <= 0) {
                this.hp2 = 0;
                this.image1 = this.win;
                this.image2 = this.lose;
            }
        },
    },
};
</script>

<style>
.container {
  position: relative;
  width: 100%;
  max-width: 300px;
  
  
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
  color: rgb(41, 10, 90);
  font-size: 33px;
  padding: 12px 24px;
  border: none;
  cursor: pointer;
  border-radius: 5px;
  text-align: center;
}

.container-attack {
  position: relative;
  width: 100%;
  max-width: 520px;
  left: 32%;
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
  color: rgb(255, 0, 0);
  font-size: 25px;
  padding: 12px 24px;
  border: none;
  cursor: pointer;
  border-radius: 5px;
  text-align: center;
}

.container-fluid{
  font-size: 20px;
  font-family: Arial, Helvetica, sans-serif;
}

</style>