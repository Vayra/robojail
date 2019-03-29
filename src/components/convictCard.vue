<template>
  <div class="Crime">
    <h3>{{name}}</h3>
    <img v-bind:src="headshot">
    <p><strong>Crime: </strong>{{crime}}</p>
  </div>
</template>

<script>
export default {
  name: "convictCard",
  props: {
    name: String,
    id: Number,
    headshot: String,
    crime: String
  }
};
</script>

<style>
.Crime {
    background: #1c083d;
    border: solid 2px #e94210;
    border-radius: 50px 50px 10px;
    margin-top: 1%;
}

h3, p {
    color: whitesmoke;
}
</style>