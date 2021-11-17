<template>
    <div>
        <input v-model="writer" type="text" placeholder="글쓴이"/>
        <input v-model="title" type="text" placeholder="제목"/>
        <textarea v-model="content" type="text" placeholder="내용"/>
        <button @click="write" >작성</button>
    </div>
</template>

<script>
import data from '@/data'

export default {
    name: 'Create',
    data(){
        return {
            data: data,
            writer: "",
            title: "",
            content:""
        }
        // /Create 에서 ""안에 작성이 가능함
    },
    methods: {
        write(){
            this.data.push({
                writer: this.writer,
                title: this.title,
                content: this.content,
            })
            this.$router.push({
                path: '/'
            })
            // 작성한 데이터 값을 localhost에 넘기면서 돌아감
        }
    }
}
</script>