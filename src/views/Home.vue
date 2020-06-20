<template>
  <div class="home">

    <div class="banner">
      <div class="manual-schedule">
       <h1> Say Goodbye to manual scheduling </h1>
       <p> </p>
       <img src="/images/manual2.svg">
      </div>
      <div class="button-click">
        <h1>Generate timetable with a button click </h1>
        <v-btn type="submit" id="fancy-button">Generate TimeTable </v-btn>
      </div>
      <div>
        <h1>Scheduling has never been easier </h1>
        <img src="/images/automatic.jpg">
      </div>
    </div>

   
  </div>
</template>

<script>

export default {
  components: {
    
  }
}
</script>

<style scoped>
  .home {
    width: 90%;
    margin: auto;
    margin-top:4em;
    padding: 2em;
    border: 2px solid white;
    border-radius: 1em;
    background-color: white;
  }

  #fancy-button {
    background-color: var(--primary-color)
  }

  .button-click {
    margin-bottom:7em;
  }
</style>
