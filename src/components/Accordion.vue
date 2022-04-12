<template>
    <div class="accordion-wrapper">
        <div v-for="item in data" :key="item.id" class="accordion-single">
            <!-- Here we send the single accordion id up one layer to App component -->
            <AccordionItem @toggle-item-class="$emit('toggle-item-class', item.id)" :item="item" :active="active"/>
        </div>
    </div>
</template>

<script>
    import AccordionItem from './AccordionItem';

    export default {
        name: 'Accordion',
        components: {
            AccordionItem
        },
        props: {
            data: Array,
            active: Number
        },
        emits: [
            'toggle-item-class'
        ],
    }
</script>

<style scoped>
    .accordion-wrapper {
        max-width: 805px;
        overflow: hidden;
        margin: auto;
        border: 1px solid rgb(222 226 230);;
        border-radius: 0.25rem;
        padding: 1.5rem;
    
    }

        .accordion-wrapper .accordion-single {
            overflow: hidden;
            background-color: #fff;
            border: 1px solid rgba(0,0,0,.125);
            border-top-left-radius: calc(0.25rem - 1px);
            border-top-right-radius: calc(0.25rem - 1px);
        }

    
</style>