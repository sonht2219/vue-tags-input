<template>
  <section>
    <h1>Simple Draggale</h1>
    <vue-tags-input
      style="margin-bottom: 20px"
      v-model="tag"
      :tags="tags"
      :autocomplete-items="filteredItems"
      :is-draggable="true"
      :draggable-group="{name: 'tags', pull: 'clone', put: false}"
      :draggable-animation="300"
      :autocomplete-filter-duplicates="false"
      :autocomplete-min-length="0"
      @tags-changed="newTags => tags = newTags"
    />
    <vue-tags-input
      v-model="tag"
      :tags="tags"
      :autocomplete-items="filteredItems"
      :is-draggable="true"
      :draggable-group="'tags'"
      @tags-changed="newTags => tags = newTags"
    />
    <el-code lang="html" :code="require('./example1.demo.html')" />
  </section>
</template>

<script>
import VueTagsInput from '@johmun/vue-tags-input';
import ElCode from '@components/el-code';

export default {
  components: {
    VueTagsInput,
    ElCode,
  },
  data() {
    return {
      tag: '',
      tags: [],
      autocompleteItems: [{
        text: 'Spain',
      }, {
        text: 'France',
      }, {
        text: 'USA',
      }, {
        text: 'Germany',
      }, {
        text: 'China',
      }],
    };
  },
  computed: {
    filteredItems() {
      return this.autocompleteItems.filter(i => {
        return i.text.toLowerCase().indexOf(this.tag.toLowerCase()) !== -1;
      });
    },
  },
};
</script>
