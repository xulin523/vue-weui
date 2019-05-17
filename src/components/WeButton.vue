<template>
     <button @click="$emit('click')" class="weui-btn" :class="[typeStyle,disabledStyle,sizeStyle,loadingStyle]" >
        <i class="weui-loading" v-if="loading"></i>
       <slot></slot>
      </button>
</template>
<script>
export default {
  props: {
    type: {
      type: String,
      default: "default"
    },
    props: {},
    // 负责禁用/启用
    disabled: {
      type: Boolean,
      default: false
    },
    // 线框
    plain: {
      type: Boolean,
      default: false
    },
    // 按钮大小
    size: {
      type: String,
      default: "default"
    }
  },
  computed: {
    typeStyle() {
      let s = "";
      switch (this.type) {
        case "primary":
          s = this.plain? "weui-btn_plain-primary":"weui-btn_primary";
          break;
        case "warning":
          s =  "weui-btn_warn";
          break;
        default:
          s =  this.plain? "weui-btn_plain-default":"weui-btn_default";
          break;
      }
      return s;
    },
    disabledStyle(){
        return this.disabled?'weui-btn_disabled ':'';
    },
    sizeStyle(){
        let s = '';
        switch(this.size){
            case 'mini':s='weui-btn_mini';break;
            case 'large':s='weui-btn_block';break;
            default:s='';break;
        }
        return s;
    },

  }
};
</script>
<style>
</style>
