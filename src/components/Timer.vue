<template>
  <div class="hello">
    <v-container
      id="input-interval"
      fluid
      >
      <v-row>
        <v-col cols="3">
        </v-col>
        <v-col cols="3">
          <v-autocomplete
            v-model="minutes"
            :items="minuteItems"
            dense
            label="Minits"
          ></v-autocomplete>
        </v-col>
        <v-col cols="3">
          <v-autocomplete
            v-model="seconds"
            :items="secondItems"
            dense
            label="Seconds"
          ></v-autocomplete>
        </v-col>
        <v-col cols="3">
        </v-col>
      </v-row>
    </v-container>
    <div id="app">
      <Pomodoro :minutes="minutes"
                :pomodoro-label="pomodoroLabel"
                :start-label="startLabel"
                :pause-label="pauseLabel"
                :reset-label="resetLabel"
                :theme="theme" />
    </div>
  </div>
</template>

<script>
import Pomodoro from 'vuemodoro'

let minute = 50
let second = 0

let minuteItems = []
for (let i = 0; i <= 99; i++) {
  minuteItems.push(i)
}

let secondItems = []
for (let i = 0; i <= 59; i++) {
  secondItems.push(i)
}

export default {
  name: 'App',
  components: {
    Pomodoro
  },
  data () {
    return {
      minutes: minute,
      seconds: second,
      pomodoroLabel: 'カウントダウン',
      startLabel: 'スタート',
      pauseLabel: 'ストップ',
      resetLabel: 'リセット',
      theme: 'light',

      minuteItems: minuteItems,
      secondItems: secondItems
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
