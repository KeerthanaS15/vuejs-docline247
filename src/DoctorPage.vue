<template>
    <div>
        <app-navbar></app-navbar>

        <doc-category></doc-category>

        <doc-detail></doc-detail>
  </div>
</template>

<script>
import Navbar from "./components/NavBar.vue"
import DocCategory from "./components/DocCategory.vue"
import DoctorDetail from "./components/DoctorDetail.vue"
export default {
  components:{
   'app-navbar': Navbar,
   'doc-category':DocCategory,
   'doc-detail':DoctorDetail
  },
  data () {
    return {
    }
  }
}
</script>

<style lang='scss'>

</style>
