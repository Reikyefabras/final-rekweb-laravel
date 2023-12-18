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
}
</style>
<template>
    <div class="post__create">

        <form @submit.prevent="form.post('/post')">
        <div>
            <label>Judul Film</label><br>
            <input type="text" v-model="form.title" class="input text" />
        </div>
        <div>
            <label>Sutradara</label><br>
            <input type="text" v-model="form.author" class="input text"/>
        </div>
        <div>
            <label>Sinopsis Film</label><br>
            <textarea v-model="form.content" class="input text-area"></textarea>
        </div>
        <div>
            <input type="submit" value="Create new post" class="buttom"/>
        </div>
        </form>
    </div>
</template>

<script setup>
    import { useForm } from '@inertiajs/vue3'

    const form = useForm({
        title: '',
        author: '',
        content: ''
    });
</script>