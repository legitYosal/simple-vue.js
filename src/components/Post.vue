<template>
    <div class="post">
        Post
        <p v-if="!editing" class="post-text">{{text}}</p>
        <input v-else v-model="edited_text" type="text">
        <button @click="toggle_edit">
            <div v-if="editing">submit</div>
            <div v-else>edit</div>
        </button>
    </div>
</template>

<script>
export default {
    name: 'Post',
    props: {
        text: {type: String, default: 'Enter text'},
    },
    data() {
        return {
            editing: false,
            edited_text: null,
        }
    },
    methods: {
        toggle_edit() {
            if (this.editing && this.text !== this.edited_text) {
                // emit event to parent component
                this.$emit('change_text', this.edited_text)
            }
            this.editing = !this.editing
        }
    },
    // mounted is called after a component renders for one time
    mounted() {
        this.edited_text = this.text
    }
}
</script>

<style>
.post {
    background: rgb(210, 245, 141);
    width: 30%;
    margin: auto;
    height: 100px;
}
.post-text {
    background: #eee;
    width: 90%;
    margin: auto;
}
</style>