<template>
  <div>
    <slot></slot>
  </div>
</template>
<script type="text/ecmascript-6">
  import Emitter from "../emitter";
  var  underscore = require( "../underscore-min");
  export default{
    mixins: [Emitter],
    componentName:"seltiplist",
    data(){
      return{
        istipSelect: true
      }
    },
    props: {
      value:{},
      multiple:{
        type: Boolean,
        default: false
      }
    },

    mounted(){
      this.$on('handleOptionClick', this.handleOptionSelect);
    },
    methods:{
      handleOptionSelect(val){
        if(this.multiple&&underscore._.isArray(this.value)){
          let optionIndex = this.value.indexOf(val);
          this.value.forEach((item, index) => {
            if (underscore._.isEqual(item,val)) {
              optionIndex = index;
            }
          });
          if( optionIndex<0){
            this.value.push(val);
          }else {
            this.value.splice(optionIndex, 1)
          }
        }else {
          if(val!=this.value){
            this.$emit('input', val);
          }else {
            this.$emit('input', "");
          }
        }

      }
    }
  }
</script>
