<template>
  <div class="my-leagues bg-white">
    <div class="header bg-gray-300 py-2">
      Leagues available
    </div>
    <div class="list-leagues mt-4">
      <div class="league p-1" v-for="(lig,i) in usableLeagues" :key="i">
        <League :champion="lig"/>
      </div>
    </div>
  </div>
</template>

<script>
/* eslint-disable */

import League from '@/components/League'
export default {
  name: 'Leagues',
  components: { League },
  data(){
    return {
      pres:'mwaa'
    }
  },
  computed:{
    usableLeagues(){
      return this.$store.state.leagues.loadedLeagues.slice(0,50)
    }
  },
  mounted () {
  }
}
</script>

<style lang="scss" scoped>
.my-leagues{
  border-radius: 10px;
  .header{
    text-align: center;
    font-size: 1.2rem;
  }
}
</style>
