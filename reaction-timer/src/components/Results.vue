<template>
  <h4>Your reaction time is: {{score}}</h4>
</template>

<script>
export default {
    props: ['score'],
    data () {
        return {
            showReactionTime: false
        }
    }

}
</script>

<style>

</style>