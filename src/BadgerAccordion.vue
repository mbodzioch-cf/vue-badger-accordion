<template>
    <div class="component-badger-accordion" ref="badger"><slot></slot></div>
</template>

<script>
import Vue from "vue";

import BadgerAccordion from 'badger-accordion';

Vue.component('BadgerAccordionItem', require('./BadgerAccordionItem.vue'))

export default Vue.extend({
    name: 'BadgerAccordion',
    props: ['options'],
    data() {
        return {
            accordion: null,
        }
    },
    mounted() {
        this.accordion = new BadgerAccordion(this.$refs.badger, (this.options || {})); 
    },
    methods: {
        init() { this.accordion.init() },
        getState() { return this.accordion.getState() },
        open() { this.accordion.open() },
        close() { this.accordion.close() },
        togglePanel() { this.accordion.togglePanel() },
        openAll() { this.accordion.openAll() },
        closeAll() { this.accordion.closeAll() },
        calculateAllPanelsHeight() { this.accordion.calculateAllPanelsHeight() },
        calculatePanelHeight() { this.accordion.calculatePanelHeight() }
    }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss"></style>