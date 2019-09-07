<template>
  <div id="app">
    <!--{{components}}-->
    <!--<img src="./assets/logo.png">-->
    <!--<HelloWorld></HelloWorld>-->
    <!--<Container></Container>-->
    <!--<Editer></Editer>-->
    <!--<CContainer v-bind:components="components"></CContainer>-->
    <!--<router-view/>-->
    <ChuangContainer></ChuangContainer>
    <!--<TestContainer></TestContainer>-->
  </div>
</template>

<script>
  import HelloWorld from "./components/HelloWorld"
  import Container from './components/layout/Container'
  import Editer from './components/editer/Editer'
  import CContainer from './components/layout/CContainer'
  import TestContainer from './components/view/TestContainer'
  import ChuangContainer from './components/layout/ChuangContainer'
export default {
  name: 'App',
  data:function (){
    return {
    components:[{name:"button"},{name:"form"}]
    }
  },
  created:function(){
    console.log(this);
  },
  components:{
    HelloWorld,
    Container,
    Editer,
    CContainer,
    TestContainer,
    ChuangContainer
  }
}
</script>

<style>

</style>
