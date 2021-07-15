<template>
  <main>
    <div class="container">
      <div class="row">
        <Cards
          v-for="(element, index) in albums"
          :key="index"
          :poster="element.poster"
          :author="element.author"
          :title="element.title"
          :genre="element.genre"
        />
      </div>
    </div>
  </main>
</template>

<script>
import Cards from './Cards.vue';
export default {
  name: 'Main',
  components: {
    Cards,
  },
  props: {
    albums: Array,
  },
};
</script>

<style scoped lang="scss">
main {
}
</style>