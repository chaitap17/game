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
                {name: 'Gaara' ,hp: 200 ,image:'./assets/3.jpg' }
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