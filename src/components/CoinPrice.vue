<template>
    <div id="counter" class="bg-warning text-white">
        <div class="row p-3">
            <div class="col-2">
                <i class="fas fa-dollar-sign fa-4x"></i>
            </div>
            <div class="col-10 text-right">
                <h2>{{ format(price.amount) }} <span class="align-middle" v-html="formatState"></span></h2>
                ${{ difference }}
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'CoinPrice',
        computed: {
            price() {
                return this.$store.getters.currentPrice;
            },
            difference() {
                return this.$store.getters.difference;
            },
            formatState() {
                return this.$store.getters.stateChanges;
              }
        },
        methods: {
            format: price => {
                return price.toFixed(2);
            }
        }
    }
</script>
<style></style>