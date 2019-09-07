<template>
    <div>
      <vuep v-model="value" :options="{ mode: 'javascript' }" ></vuep>
    </div>
</template>

<script>
    export default {
      name: "Editer",
      data: function(){
        return {
        value: `module.exports = {
        template: '<div>I\\'am {{ name }}</div>',
        data: function () {
          return { name: 'cinwell' }
        }
      }`}
      }
    }
</script>

<style scoped>

</style>
