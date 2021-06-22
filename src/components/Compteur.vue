<template>
    <h1>Mon super compteur</h1>
    <p @click="increment">Vous avez cliqué {{ total }} fois.</p>
    <p>Le total de vueX est de {{ totalGeneral }}.</p>
    <p>Le double du total de vueX est de {{ doubleDuTotal }}.</p>
</template>

<script>
export default {
    name: 'Compteur',
    data() {
        return {
            total: 0,
        };
    },
    computed: {
        totalGeneral() {
            return this.$store.state.totalFromVueX;
        },
        doubleDuTotal() {
            return this.$store.getters.doubleDuTotal;
        },
    },
    methods: {
        increment() {
            this.total++;
            this.$store.commit('setTotalFromVueX', this.totalGeneral+=1);
        },
    },
    props: {
        msg: String,
    },
};
</script>

<style scoped></style>
