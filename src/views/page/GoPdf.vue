<template>
  <div class="content g2-content">
    <object :data="url" type="application/pdf" name="file.pdf">
      <embed :src="url" type="application/pdf" />
    </object>
    <!-- <pdf src="./path/to/static/relativity.pdf"></pdf> -->
<h1>{{url}}</h1>

  </div>
</template>

<script>
import { decode64 } from "@utils/AcrouUtil";
// import pdf from 'vue-pdf'

export default {
  // components: {
  //   pdf
  // },
  data: function() {
    return {};
  },
  computed: {
    url() {
      if (this.$route.params.path) {
        // console.log(this.$route.params.path);
      
        return decode64(this.$route.params.path);
      }
      return ''
    }
  },
  methods: {}
};
</script>

<style scoped>
object{
    width: 100%;
    height: -webkit-fill-available;
}
</style>