<template>
    <div>
        <v-textarea
          outlined
          v-model="memo"
          label="투두리스트를 입력해주세요(TODOLIST)"
          value=""
        ></v-textarea>
        <v-btn @click="listAdd">리스트 추가</v-btn>
    </div>
</template>

<script>
export default {
    data() {
        return {
            memo: null
        }
    },
    methods: {
        listAdd() {
            // console.log('리스트 추가')
            if(this.memo === null){
                alert('내용을 입력해 주세요.')
                // alert("이 페이지에서 알림 비허용 하지 말아주세요")
            }
            this.$emit('listAdd', this.memo)
        }
    }
}
</script>