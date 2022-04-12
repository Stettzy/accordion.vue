<template>
    <div :class="item.id === active ? 'accordion-single-content active' : 'accordion-single-content'">
        <h2 class="accordion-single__title"><button @click="toggleItemClass(item.id)">{{item.title}}</button></h2>
        <div :class="item.id === active ? 'accordion-single-body active' : 'accordion-single-body'">
            <p class="accordion-single__text" v-html="item.body"></p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "AccordionItem",
        props: {
            item: Object,
            active: Number
        },
        methods: {
            // This method will grab the selected accordion id
            // and pass it one layer up to Accordion component 
            toggleItemClass(id) {
                this.$emit('toggle-item-class', id);
            }
        }
    }
</script>

<style scoped>
    h2.accordion-single__title {
        margin: 0;
        padding: 0;
        background-color: #fff;
    }
        h2.accordion-single__title button {
            width: 100%;
            height: 100%;
            text-align: left;
            padding: 16px 20px;
            font-size: 1rem;
            color: rgb(33 37 41);;
            cursor: pointer;
            background-color: #fff;
            border: none;
            font-weight: 500;
        }

    .accordion-single-content.active h2.accordion-single__title button{
        color: #0c63e4;
        background-color: #e7f1ff;
        transition: .5s;
    }

    .accordion-single-body {
        max-height: 0;
        overflow: hidden;
        transition: .5s;
    }

    .accordion-single-body.active  {
        max-height: 175px;
        height: auto;
        transition: .5s;
        overflow-y: auto;
    }

        .accordion-single-body .accordion-single__text {
            padding: 1rem 1.25rem;
        }
</style>