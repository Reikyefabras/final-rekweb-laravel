<style scoped>
.post__create{
    margin: 20px 10px;

}

form{
display:flex;
flex-direction:column;
row-gap: 15px;
}
.input{
    width: 60%;
}
.text{
    height: 30px;
}
.text-area{
    height: 80px;
}

.buttom{
    padding: 5px;
    border: 1px solid;
    text-decoration: none;
    color:white;
    border-radius: 8px;
    background-color: rgb(52, 115, 230);
}
label{
    font-weight: 700;
    font-size: 20px;
    
}
</style>
<template>
    <div class="post__create">

        <form @submit.prevent="form.put(`/post/update/${post.id}`)">
        <div>
            <label>Title</label><br>
            <input type="text" v-model="form.title" class="input text" />
        </div>
        <div>
            <label>Author</label><br>
            <input type="text" v-model="form.author" class="input text" />
        </div>
        <div>
            <label>Content</label><br>
            <textarea v-model="form.content" class="input text-area"></textarea>
        </div>
        <div>
            <input type="submit" value="Update post" class="buttom"/>
        </div>
        </form>
    </div>
</template>

<script setup>
    import { useForm } from '@inertiajs/vue3'
    import { defineProps } from 'vue';

    let props = defineProps({
        post: Object
    })

    const form = useForm({
        title: props.post.title,
        author: props.post.author,
        content: props.post.content
    });
</script>