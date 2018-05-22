<template>
  <div>
    <input type="checkbox" v-model="checked" @click="checkAll"/>
    <template v-for="check in checkbox">
      <input type="checkbox" name="checkboxInput" v-model="checkboxModel" :value="check.id"/>{{check.value}}
    </template>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    data() {
      return {
        checked: false,
        checkboxModel: [1,2],
        checkbox: [
          {
            id: "1",
            value: "Æ»¹û",
          },
          {
            id: "2",
            value: "Ïã½¶",
          },
          {
            id: "3",
            value: "²ÝÝ®",
          },
          {
            id: "4",
            value: "»ðÁú¹û",
          }
        ]
      }
    },
    methods: {
      checkAll() {
        if (this.checked) {
          this.checkboxModel = []
          return
        }
        this.checkbox.forEach(item => {
          this.checkboxModel.push(item.id)
        })
      }
    }
  }
</script>

<style lang="css" rel="stylesheet/css">
</style>
