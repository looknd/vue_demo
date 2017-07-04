<template>
  <div>
    <p class="title">Dom更新延迟回调-nextTick</p>
    <div class="clear"></div>
    <div class="content">
      <p ref="mgs">{{mgs}}</p>
      <button @click="updateDom">点击更新DOM</button>
    </div>
    <div class="remark">
      请查看控制台，观察输出；<br/>
      mgs更新后，console.log(this.$refs.mgs.innerHTML)输出没有更新，
      this.$nextTick输出更新<br/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'nextTick',
  data:function () {
    return {
      mgs:"DOM"
    }
  },
  methods:{
      updateDom:function () {
          this.mgs = "update Dom";
          console.log(this.$refs.mgs.innerHTML);
          this.$nextTick(function () {
            console.log(this.$refs.mgs.innerHTML);
          })
      }
  }
  //mounted:function () {
  //  this.updateDom()
  //}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
