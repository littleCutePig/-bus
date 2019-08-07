<template>
  <div>
    <!-- <input type="text" v-model="modelInp"> -->
    <!-- <VModel :value="modelInp"></VModel> -->
    <VModel @input="ParentFun"></VModel>
  </div>
</template>
<script>
export default {
  data() {
    return {
      modelInp:"定义的属性"
    };
  },
  components: {
    VModel: {
      props: ["value"],
      template: `<div>
                    子组件{{value}}
                    <button @click="ChangeVal">修改</button>
                  </div>`,
      methods:{
        ChangeVal(){
          console.log(1)
          // this.$emit('input','改一改属性')
         }
      }
    }
  },
  methods:{
    ParentFun(){
      // console.log(1)
    }
  }
}
</script>
<style scoped lang="">
</style>