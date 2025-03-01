# vue-tags-input

This is forked component from https://github.com/JohMun/vue-tags-input with added drag and drop support.

This is forked component from https://github.com/VojtechLanka/vue-tags-input with added drag and drop options support.
## Features

* No dependencies
* Custom validation rules
* Hooks: Before adding, Before deleting ...
* Edit tags after creation
* Fast setup
* Works with Vuex
* Autocompletion
* Many customization options
* Own templates
* Delete tags on backspace
* Add tags on paste
* Examples & Docs
* Drag and Drop

## Install

NPM
```
npm i @sonht2219/vue-tags-input
```

## Usage with draggable

Draggable is disabled by default. Set prop `:is-draggable` to true to enable it. You can also set `:draggable-handle` to true to enable handle which can be styled with css class `.handle`. Classes for ghost-class and drag-class are `.ghost-tag` and `.drag-tag`.

On drop `tag-order-changed` is emitted with array of tags in new order. Use this array to update your tags to save the new order.

- draggable-group: define group
- draggable-animation: define animation

```html
<template>
  <div>
    <vue-tags-input
      v-model="tag"
      :tags="tags"
      :is-draggable="true"
      :draggable-group="{name: 'tags', pull: clone, put: false}"
      :draggable-animation="200"
      @tags-changed="newTags => tags = newTags"
      @tag-order-changed="newTags => tags = newTags"
    />
  </div>
</template>
```

```javascript
<script>
import VueTagsInput from '@vojtechlanka/vue-tags-input';

export default {
  components: {
    VueTagsInput,
  },
  data() {
    return {
      tag: '',
      tags: [],
    };
  },
};
</script>
```

## License

[MIT](https://opensource.org/licenses/MIT)

Copyright (c) 2019 Johannes Munari
