<template>
    <section>
        <ul>
            <li v-for="(item, index) in propsdata" :key="index" class="shadow">
                <i class="checkBtn fa fa-check" area-hidden="true"></i>
                {{item}}
                <span class="removeBtn" type="button" @click="removeTodo(item, index)">
                    <i class="fa fa-trash-o" aria-hidden="true"></i>
                </span>
            </li>
        </ul>
    </section>
</template>

<script>
export default {
    props: ['propsdata'],
    methods: {
        removeTodo(todoItem, index) {
            localStorage.removeItem(todoItem);
            this.todoItems.splice(index, 1);
        }
    },
    beforeCreated(e) {
        console.log('beforeCreated', e)
    },
    created(e) {
        console.log('created', e)
    },
    mounted(e) {
        console.log('mounted', e)
    }
}
</script>

<style>
    ul {
        list-style-type: none;
        padding-left: 0px;
        margin-top: 0;
        text-align: left;
    }

    li {
        display: flex;
        min-height: 50px;
        height: 50px;
        line-height: 50px;
        margin: 0.5rem 0;
        padding: 0 0.9rem;
        background: white;
        border-radius: 5px;
    }

    .checkBtn {
        line-height: 45px;
        color: #62acde;
        margin-right: 5px; 
    }

    .removeBtn {
        margin-left: auto;;
        color: #de4343;
    }
</style>
