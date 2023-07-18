<template>
    <div class="header">
        <!-- {{message}}
        <input v-model="message"> -->

        <!-- <button @click="increment">
            {{ count }}
        </button> -->

        <span style="color: red;">{{ publishedBooksMessage }}</span>
        <br/>
        <button @click="awesome = !awesome">Toggle</button>

        <h1 v-if="awesome">Vue is awesome!</h1>
        <h1 v-else>Oh no 😢</h1>
    </div>
    
    
</template>
<script>
    export default{
        data() {
            return {
                // message: 'Header Component',
                // count: 0,
                awesome: true,
                author: {
                    name: 'Vue',
                    books: ['Vue 1', 'Vue 2', 'Vue 3']
                },
                obj: {
                    nested: { count: 0 },
                    arr: ['foo', 'bar']
                }
            }
        },
        methods:{
            increment() {
                this.count++
            },
            // increment: () => {
            //     // BAD: no `this` access here!
            //     //this.count++
            // }
            mutateDeeply() {
            // these will work as expected.
            this.obj.nested.count++
            this.obj.arr.push('baz')
            console.log(this.obj.nested)
            }
        },
        mounted(){
            this.mutateDeeply()
        },
        computed:{
            publishedBooksMessage(){
                return this.author.books.length > 0 ? 'Yes' : 'No'
            }
        }
    }
</script>