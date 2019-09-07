<template>
    <div>
      <p class="item" v-for="c in components">
        {{c.name}}
      </p>
    </div>
</template>

<script>
    export default {
        name: "CContainer",
        props:{components:Object},
        data:function () {
          return {};
        }
    }
</script>

<style scoped>
  .item{
    width: 100%;
    font-size: 24px;
    padding:5px 0px;
    border-bottom: solid silver 1px;
  }

  .item:hover{
    background: aqua;
  }
  .active{
    background: aqua;
  }
</style>
