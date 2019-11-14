## Installation
```bash
npm install wavesurfer-vue
```

## Module
As a global vue-cli plugin
```javascript
import Vue from 'vue'
import VueWaveSurfer from 'wavesurfer-vue'

Vue.use(VueWaveSurfer)
```
As a nuxt global plugin
```javascript
// plugins/wavesurfer-vue.js
import Vue from 'vue'
import VueWaveSurfer from 'wavesurfer-vue'

Vue.use(VueWaveSurfer)
```

```javascript
// nuxt.config.js
export default {
  plugins: [
    '~/plugins/wavesurfer-vue'
  ]
}
```
As a component plugin
```javascript
import VueWaveSurfer from 'wavesurfer-vue'
export default {
  components: {
    VueWaveSurfer
  }
}
```

## Usage
```vue
<template>
  <vue-wave-surfer :src="file" :options="options"></vue-wave-surfer>
</template>
<script>
export default {
  data() {
    return {
      options: {
      },
      file: 'http://example.com/file.mp3'
    }
  }
}
</script>
```

## Options
See the list of options in the [official documentation](https://wavesurfer-js.org/docs/options.html)

## Using Plugins
An example implenting the [Cursor](https://wavesurfer-js.org/plugins/cursor.html) plugin
```vue
<script>
import Cursor from 'wavesurfer.js/dist/plugin/wavesurfer.cursor';
export default {
  data() {
    return {
      options: {
        plugins: [
          Cursor.create()
        ]
      }
    }
  }
}
</script>
```