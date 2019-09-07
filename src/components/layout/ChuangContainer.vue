<template>
    <div class="layout">
      <Layout>
        <Sider>
          <!--组件列表-->
          <Menu active-name="1-2" theme="light" width="auto" :open-names="['1']">
            <Submenu v-bind:name="index" v-for="(c, index) in compoments">
              <template slot="title">
                <Icon v-bind:type="c.icon == '' ? 'ios-navigate': c.icon"></Icon>
                {{c.description}}
              </template>
              <!--嵌入拖拽-->
              <draggable class="list-group" :list="c.list" group="people" @change="log" @dragstart="dragstart">
              <MenuItem v-bind:name="index-lindex" v-for="(l,lindex) in c.list" >{{l.description}}</MenuItem>
              </draggable>
            </Submenu>
          </Menu>
        </Sider>
        <Layout class="center" >
          <p @mouseenter="enter" @mouseleave="leave" @click="click">{{message}}</p>
        </Layout>
        <Sider class="right">
          <p> right</p>
        </Sider>
      </Layout>
    </div>
</template>

<script>
    /*
    * Created by:zjh
    * Created:20190904
    * Comment:川式布局
    * */
    import draggable from "vuedraggable";

    export default {
        name: "ChuangContainer",
        components: {
          draggable
        },
        data:function(){
          return {
            compoments:[
              {
                type:"component",
                icon:"md-albums",
                description:"组件",
                list:[
                  {type:"color",description:"Color色彩"},
                  {type:"font",description:"Font字体"},
                  {type:"button",description:"Button按钮"},
                ]
              },
              {
                type:"layout",
                icon:"md-browsers",
                description:"布局",
                list:[]
              },
              {
                type:"nav",
                icon:"",
                description:"导航",
                list:[]
              },
              {
                type:"layout",
                icon:"",
                description:"布局",
                list:[]
              },
              {
                type:"form",
                icon:"",
                description:"表单",
                list:[]
              }
            ],
            message:"center"
          };
        },
      methods: {
          enter:function () {
            this.message="enter";
            window.console.log("enter");
          },
          leave:function(){
            this.message="leave";
          },
          click:function () {
            this.message="click";
          },
          dragstart:function (e) {
            window.console.log(e);
          },
          log:function (e) {
            window.console.log(e);
          }
      }
    }
</script>

<style scoped>
  .layout{
    border: 1px solid #d7dde4;
    background: #f5f7f9;
    position: relative;
    border-radius: 4px;
    overflow: hidden;
    height: 100%;
  }
  .left{
    width: 20%;
    background: aqua;
    height: 100%;
  }
  .center{
    width: 60%;
    background: silver;
    height: 100%;
  }
  .right{
    width: 20%;
    background: aquamarine;
    height: 100%;
  }
</style>
