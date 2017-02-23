<template>
  <div>
    <slot></slot><!--内容分发-->
  </div>
</template>
<script type="text/ecmascript-6">
  export default{
    data(){
      return {
        istipSelect: true
      }
    },
    props: {
      value: {},
      multiple: {
        type: Boolean,
        default: false
      }
    },
    mounted(){
    },
    methods: {

    }
  }
</script>
