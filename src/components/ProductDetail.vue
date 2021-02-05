<template>
  <ul>
    <li :key="index" v-for="(detail, index) in detailData">{{ detail }}</li>
  </ul>
</template>

<script>

export default {
  props: {
    detailData: {
      type: [ String, Number, Array ],
      }
  },
  setup(){
    // const details = props.detailData;
    // console.log(props.detailData)

    return{
      // details
    }
  }

}
</script>

<style scoped>

</style>