<template>
    <div>
        <div> {{data.writer}} </div>
        <div> {{data.title}} </div>
        <div> {{data.content}} </div>
        <button @click="updateData">수정</button>
        <button @click="deleteData">삭제</button>
    </div>
</template>

<script>
import data from '@/data'

export default {
    name: 'Detail',
    data(){
        const index = this.$route.params.contentId
        return {
            data: data[index],
            // index 를 가져오기 위해서 작성
            index: index,
        }
    },
    methods: {
        deleteData(){
            data.splice(this.index, 1)
            // data 값을 가져오면서 delete버튼을 클릭시 / 라우터로 변경
            this.$router.push({
                path: '/'
            })
        }
    }
}
</script>