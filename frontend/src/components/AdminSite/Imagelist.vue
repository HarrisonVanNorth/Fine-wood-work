<template>
  <b-row class="justify-content-md-center">
    <b-col cols="6">
      <h3>Image Files</h3>
      <b-list-group>
        <b-list-group-item v-for="image in images" v-bind:key="image.id">
        <span class="d-flex"><h6>File Name: </h6> {{ image.key }} </span>
        <span class="d-flex"><h6>Category: </h6> {{ image.category }} </span>
        </b-list-group-item>
      </b-list-group>
    </b-col>
  </b-row>
</template>

<script>

export default {
  name: 'ImageListVue',
  mounted(){
    this.$store.dispatch('getImages')
  },
  computed: {
    images(){
      return this.$store.state.images;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
