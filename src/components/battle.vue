<template>
    <!-- !!add attack val as a factor!! have current health go down with each battle
    take current health, divide it by the max health and multiply that by a random num
    that value will be deducted from the other bot and that will become it's new current health,  and vice versa 
    whichever bot does the most damage wins and their victory count goes up
    when current health = 0 does the bot retires in a hall of fame with victories labled-->

    <!-- ((current health + attckval)/totalhealth) * randomNumber-->
    <div></div>
</template>

<script>
    methods: {
        botBattle: function(bot1, bot2) {
            
        let randomNum = Math.floor(Math.random() * 255)
        bot1val = ((bot1.current + attack)/totalhealth) * randomNum
        }
    }
</script>