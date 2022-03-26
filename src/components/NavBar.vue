<template>
    <header class="m-header">
        <a href="#" class="m-header__img">
            <img src="../assets/images/home.svg" alt="go-to-home">
        </a>

        <span class="m-header__heading h4">DOCTORS INFORMATION</span>
    </header>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>

<style lang='scss'>
.m-header{
    height: 58px;
    background-color: #237d9e;
    display: flex;
    align-items: center;
    justify-content: space-evenly;

    &__img{
        height: 26px;
    }

    &__heading{
        color: #fff !important;
        font-weight: bold !important;
    }
    
}
</style>
