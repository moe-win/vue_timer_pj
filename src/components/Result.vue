<template>
  <p>This is Score {{reactiontime}}</p>
  <div v-if="reactiontime<300">
    <p>You Are Too Fast Now CONGRA!!!</p>
  </div>
  <div v-else-if="reactiontime>300 && reactiontime<800">
    <p>You are Normal GOOD!!!!</p>
  </div>
  <div v-else>
    <p>You are Too Slow TRY AGAIN!!!!</p>
  </div>
</template>

<script>
export default {
    props:['reactiontime']
}
</script>

<style>

</style>