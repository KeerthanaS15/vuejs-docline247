<template>
<div>
  <div class="p-doctor__category" >
    <div class="m-category" v-for="category of categories" :key="category.id">
        <a href="" class="m-category__item m-category-inner">
          <img v-bind:src="category.icon" alt="" class="m-category-inner__img">

          <span class="m-category-inner__name">{{category.name}}</span>
        </a>
    </div>
    <a href="" class="m-category__item m-category-inner">
      <img src="../assets/images/viewall.png" alt="viewall" class="m-category-inner__img">

      <span class="m-category-inner__name">View all</span>
    </a>
  </div>

  
</div>
</template>

<script>
import axios from "axios";
export default {
  data () {
    return {
        categories:[],
        doctorDetails:[]
    }
  },
async mounted() {
    try {
      const res = await axios.get(`http://localhost:3001/categories`);
      this.categories = res.data;
    } catch (error) {
      console.log(error);
    }
    try {
      const res = await axios.get(`http://localhost:3001/doctorDetails`);
      this.doctorDetails = res.data;
    } catch (error) {
      console.log(error);
    }
  }
}
</script>

<style lang='scss' scoped>
.p-doctor{
    height: 100vh;
    &__category{
        margin: 5%;
        display: flex;
        flex-flow: row;
        justify-content: space-between;
    }
 
}
.m-category{
    display: flex;
    flex-direction: row;
    column-gap: 22px;
    justify-content: space-evenly;    
}
.m-category-inner{
    text-decoration: none;
    &__img{
        background-color: #BFD7E0;
        width: 60px;
        height: 60px;
        padding: 10px;
        border-radius: 50%;
    }

    &__name{
        text-align: center;
        color: #000;
        display: block;
    }
}

</style>
