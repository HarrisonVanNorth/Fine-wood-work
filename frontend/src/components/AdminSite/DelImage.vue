<template>
  <b-row class="justify-content-md-center">
    <b-col cols="6">
      <h3>Delete Image</h3>
      <b-form  v-on:submit.prevent="onDelete(selected)">
        <b-form-group>
          <b-form-select v-model="selected">
            <option :value="null">please select a file to delete</option>
            <option v-for="image in images" v-bind:key="image.id"> {{ image.key }}</option>
          </b-form-select>
        </b-form-group>
        <b-button type="submit" variant="primary">Submit</b-button>
      </b-form>
    </b-col>
  </b-row>
</template>

<script>

export default {
  name: 'DelImageVue',
  mounted(){
    this.$store.dispatch('getImages')
  },
  computed: {
    images(){
      return this.$store.state.images;
    }
  },
  data(){
    return {
      selected: null,
    }
  },
  methods: {
    onDelete() {
      this.$store.dispatch('postDelete', this.selected)
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
