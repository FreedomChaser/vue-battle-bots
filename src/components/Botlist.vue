<template>
    <div >
        <h1>Bots</h1>
        <p v-if='bot1'>Bot#1: {{bot1.bot}}</p>
        <p v-else>Bot#1: Select a bot below</p>
        <p v-if='bot2'>Bot#2: {{bot2.bot}}</p>
        <p v-else>Bot#2: Select a bot below</p>
        <button v-if='bot1.bot && bot2.bot' class='fight'>Battle</button>
        <button v-else class='noFight'>Battle</button>
        <button @click='clear'>Clear</button>
        <div v-for='(bot, i) in botsArr' :key='i'>
          <p>Bot: {{bot.bot}}</p>
          <p>Attack Value: {{bot.attack}}</p>
          <p>Health Value: {{bot.current}}</p>
          <button @click='select(bot)'>Select</button>
          <hr>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            bot1: {},
            bot2: {}
        }
    },
    methods:{
        select: function(bot){
            if(this.bot1.bot){
                this.bot2 = bot
            }else{
                this.bot1 = bot
            }
        },
        clear(){
            this.bot1 = {},
            this.bot2 = {}
        }
    },
    props: ["botsArr"]
};
</script>

<style>
    .noFight{
        background: green
    }
</style>