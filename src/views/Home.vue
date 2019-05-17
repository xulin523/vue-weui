<template>
  <div class="home">
    <!-- 主题样式 -->
    <we-button type="primary">按钮</we-button>
    <we-button type="warning">按钮</we-button>
    <we-button type="default" disabled>按钮</we-button>
    <!-- 线框 -->
    <we-button type="primary" plain>按钮</we-button>
    <we-button type="warning" plain>按钮</we-button>
    <we-button type="default" plain disabled>按钮</we-button>
    <we-button type="default" disabled>按钮</we-button>
    <!-- 控制大小 -->
    <we-button type="primary" size="large">按钮</we-button>
    <we-button type="primary" size="default">按钮</we-button>
    <we-button type="primary" size="mini">按钮</we-button>

    <!-- loading -->
    <we-button type="primary"  @click="showDialog"> 显示：{{show}}</we-button>

    <we-dialog v-model="show" title="标题">插槽显示的内容</we-dialog>
    <we-action-sheet v-model="show" title="标题" :action="['操作1','操作1','操作3','操作4']" @action="actionSheetHandler" ></we-action-sheet> 

  </div>


</template>

<script>
// 模块化引入这个按钮组件
import WeButton from "../components/WeButton";
import WeDialog from "../components/WeDialog";
import WeActionsheet from "../components/WeActionsheet";

export default {
 name: "home",
  data(){
    return {
      show:true
    };
  },
  methods:{
    showDialog(){
      this.show = true
    },
    actionSheetHandler(index){
      console.log(index);
    }
  },
  components:{
    WeButton,
    WeDialog,
    WeActionsheet
  }
}
</script>
