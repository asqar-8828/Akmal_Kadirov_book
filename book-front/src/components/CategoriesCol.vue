<template>
  <div class="col-12 col-md-2">
    <div class="list-group">
      <router-link
        v-for="category of getCategories"
        v-bind:key="category.id"
        :to="'/categories/' + category.id"
        class="list-group-item list-group-item-action"

      >
        {{ category.name }}

      </router-link>

    </div>
  </div>

</template>

<script>

import {mapActions, mapGetters} from "vuex";
export default {
  name: "CategoriesCol",
  computed: {
    ...mapGetters(['getCategories'])
  },
  methods: {
    ...mapActions(['fetchCategories'])
  },
  mounted() {
    this.fetchCategories()
  }
}
</script>

<style scoped>

</style>