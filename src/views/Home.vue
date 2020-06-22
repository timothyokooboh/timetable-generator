<template>
  <div class="home">

    <div class="banner">
      <div class="manual-schedule">
       <h1> Say Goodbye to manual scheduling </h1>
       <p> Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt vitae sed quisquam molestiae, nesciunt, commodi dolorum mollitia velit expedita dolore ad praesentium cumque hic dolores? Qui, laudantium! Dicta, facilis odio! </p>
       <v-btn type="submit" id="fancy-button">Generate TimeTable </v-btn>
      </div>

      <div>
        <img src="/images/side-image.jpg" alt="" id="side-image">
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
    background-color: #009FA1;
  }

  #side-image {
    height: 30em;
    object-fit: cover;
    width: 100%;
  }

  /* Media Queries */
@media (min-width:1024px) { /* big landscape tablets, laptops, and desktops */
.banner {
  display: flex;
}

.manual-schedule {
  margin-top: 5em;
  margin-left: 4em;
}

.side-image {
  margin-left: 2em;
}
}
</style>
