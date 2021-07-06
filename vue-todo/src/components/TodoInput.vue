<template>
  <div>
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
    <button v-on:click="addTodo">add</button>
    <!-- 모달 적용-->
    <Modal v-if="showModal" @close="showModal = false">
      <h3 slot="header">
        내용을 추가합니다
      </h3>
      <h3 slot="body">
        바디내용 재정의
      </h3>
      <h2 slot="footer">
        하단 내용 재정의
      </h2>
    </Modal>
    <!-- 모달 적용-->
  </div>
</template>

<script>
import Modal from "./common/Modal";

export default {
  data: function (){
    return  {
      newTodoItem: "",
      showModal: false
    }
  },
  methods: {
    addTodo(){
      if(this.newTodoItem){
        this.$emit('addTodoItem', this.newTodoItem)
        // 초기화
        this.clearInput()
      }else{
        this.showModal = !this.showModal;
      }
    },
    clearInput: function () {
      this.newTodoItem = '';
    }
  },
  components:{
    Modal:Modal
  }
}
</script>

<style scoped>

</style>
