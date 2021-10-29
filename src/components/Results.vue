<template>
    <div>
        <p><b><i>Reaction Time: {{ score }} ms</i></b></p>
        <p class="rank">{{ rank }}</p>
    </div>
</template>

<script>
    /* import { ref, reactive } from 'vue';*/

export default {
    props: ['score'],
    data() {
        return {
            rank: null,
        };
    },
    mounted() {
      if (this.score < 350) {
          this.rank = 'Damn!!! YOU ARE INCREDIBLY FAST'
      } else if (this.score < 400) {
          this.rank = 'You have rapid reflexes'
      }else if (this.score < 500){
          this.rank = 'You are slow....'
      }else {
          this.rank = 'YOU ARE INCREDIBLY SLOW'
      }
    },
    methods: {
        
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