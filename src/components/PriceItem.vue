<template>
  <li class="list-group-item">
    <div class="row">
      <div class="col-8">${{formatPrice(price.amount)}} <span class="align-middle" v-html="formatState"></span></div>
      <div class="col-4 text-right">{{formatTimestamp(price.timestamp)}}</div>
    </div>
  </li>
</template>
<script>
  export default {
    name: 'PriceItem',
    props: {
      price: Object
    },
    computed: {
      formatState() {
        return this.$store.getters.stateChanges;
      }
    },
    methods: {
      formatTimestamp: timestamp => {
        const date = new Date(timestamp);
        return date.toString().substring(16, 24);
      },
      formatPrice: amount => {
        return amount.toFixed(2);
      }
    },
  };
</script>