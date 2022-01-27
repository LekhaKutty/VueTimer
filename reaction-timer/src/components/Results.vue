<template>
  <h4>Your reaction time is: {{score}}</h4>
  <p class="rank">{{rank}}</p>
</template>

<script>
export default {
    props: ['score'],
    data () {
        return {
            rank: null
        }
    },
    mounted() {
        if (this.score < 250) {
            this.rank = "Too Fast"
        } else if (this.score < 400) {
            this.rank = "Medium fast"
        } else {
            this.rank = "Too slow"
        }
    }

}
</script>

<style>
.rank {
    font-size: 1.4em;
    color: #0faf87;
    font-weight: bold;
  }

</style>