<template>
  <div class="block">
    <p>
        Reaction time in milliseconds: {{score}}
    </p>
    <h4>Rank</h4>
    <p class="rank">{{rank}}</p>
  </div>
</template>

<script>
export default {
    name: 'Results',
    props: ['score'],
    data(){
        return{
            rank: null
        }
    },
    mounted(){
        if(this.score < 250){
            this.rank = 'Ninja Fingers'
        }else if(this.score < 400){
            this.rank = 'Rapid Reflexes'
        }else{
            this.rank = 'Snail Pace...'
        }
    }
}
</script>

<style scoped>
    .block{
        width: 400px;
        border-radius: 20px;
        background: #046085;
        color: white;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;
    }

    .rank{
        font-size: 1.2em;
        color: #0faf87;
        font-weight: bold;
    }
</style>