<template>
  <div>
    <header>
      <button @click='setCreate'>Create</button>
      <p>Battle Bots</p>
      <button @click='setBots'>Collection</button>
    </header>
    <body>
      <create v-if='view==="create"' :submited='setBotsArr'></create>
      <botlist v-else :botsArr='botsArr'></botlist>
    </body>
  </div>
</template>

<script>
import Create from "./components/Create";
import Botlist from "./components/Botlist";

export default {
  data: function() {
    return {
      view: "create",
      botsArr: []
    };
  },

  methods: {
    setBots: function() {
      this.view = "bots";
    },
    setCreate: function() {
      this.view = "create";
    },
    setBotsArr: function(bot, attack, health) {
      this.botsArr.push({
        bot,
        attack,
        health,
        current: health
      });
      
    }
  },

  components: {
    Create,
    Botlist
  }
};
</script>
