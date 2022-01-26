<template>
<header>
  <h1> {{ title }} </h1>
  <p>{{ cardMode }}</p>
  </header>
</template>

<script>
export default {
props: {
    title: String,
    cardMode: String
}
}
</script>

<style>

</style>