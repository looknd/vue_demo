<template>
  <div>
    <p class="title">自定义指令-directives</p>
    <div class="clear"></div>
    <div class="content">
      <input v-mybind />
    </div>
    <div class="remark">
      自定义v-mybind，调用钩子函数bind: 只调用一次，指令第一次绑定到元素时调用，用这个钩子函数可以定义一个在绑定时执行一次的初始化动作。<br/>
      这里初始化input的值
    </div>
    <div class="content">
      <input v-myinserted />
    </div>
    <div class="remark">
      自定义v-mybind，调用钩子函数inserted: 被绑定元素插入父节点时调用（父节点存在即可调用，不必存在于 document 中）。<br/>
      这里使input自动获取焦点
    </div>
    <div class="remark">
      <p>其他钩子函数:</p>
      update: 被绑定元素所在的模板更新时调用，而不论绑定值是否变化。通过比较更新前后的绑定值，可以忽略不必要的模板更新<br/>
      componentUpdated: 被绑定元素所在模板完成一次更新周期时调用。<br/>
      unbind: 只调用一次， 指令与元素解绑时调用。<br/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data:function () {
    return {
      bind:"",
      inserted:"",
      update:"",
      componentUpdated:"",
      unbind:"",
    }
  },
  directives:{
    mybind:{
        bind:function (el) {
          el.value = "this is mybind-bind"
        }
    },
    myinserted:{
      inserted:function (el) {
        el.focus()
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
