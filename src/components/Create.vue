<template>
    <div>
        <input v-model='bot' placeholder="Bot Name*"/>
        <input v-model='attVal' placeholder="Attack Value*"/>
        <input v-model='healthVal' placeholder="Health Value*"/>
        <button @click='submit' v-if='bot && attVal && healthVal' class='fullSubmit'>Submit</button>
        <button v-else  class='greySubmit'>Submit</button>
        <button @click='clearInput'>Clear</button>
    </div>
</template>

<script>
    export default{
        data: function(){
            return{
                bot: '',
                attVal: '',
                healthVal: '',
                currentHealth: '',
                bots: []
            }
        },
        methods: {
            clearInput: function() {
                this.bot = '',
                this.attVal = '',
                this.healthVal = ''
            },
            submit: function(){
                this.submited(this.bot, this.attVal, this.healthVal) 
                this.clearInput()
            }
        },
        props: ['submited']
    }
</script>

<style>
.greySubmit{
    background:grey
}
</style>

