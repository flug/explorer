<template>
  <span
    :class="{
      'text-red': transaction.sender === $route.params.address,
      'text-green': transaction.recipient === $route.params.address && isTransfer,
    }"
  >{{ readableCrypto(transaction.amount) }}</span>
</template>

<script type="text/ecmascript-6">
export default {
  name: 'TransactionAmount',

  props: {
    transaction: {
      type: Object,
      required: true
    },
    type: {
      type: Number,
      required: true
    }
  },

  computed: {
    isTransfer () {
      if (this.type !== undefined) {
        // 0 = transfer, 6 = timelock transfer, 7 = multipayment
        return this.type === 0 || this.type === 6 || this.type === 7
      }
      return false
    }
  }
}
</script>
