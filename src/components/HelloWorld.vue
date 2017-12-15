<template>
  <div class="hello">
    <input type="file" v-on:change="Upload()">
  </div>
</template>

<script>
import {uplo} from './firebase'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: ''
    }
  },
  methods: {
    Upload (e) {
      const file = event.target.files[0]
      const storeRef = uplo.ref('gg/' + file.name)
      storeRef.put(file)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
