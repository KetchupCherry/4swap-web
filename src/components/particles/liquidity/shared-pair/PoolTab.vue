<template>
  <div>
    <base-asset-amount-item :asset="baseAsset" :amount="meta.totalBaseAmount" />
    <base-asset-amount-item
      :asset="quoteAsset"
      :amount="meta.totalQuoteAmount"
    />
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";

@Component
class PoolTab extends Vue {
  @Prop() pair!: API.Pair;

  @Prop() baseAsset!: API.Asset;

  @Prop() quoteAsset!: API.Asset;

  get meta() {
    const totalBaseAmount = Number(this.pair?.base_amount ?? 0);
    const totalQuoteAmount = Number(this.pair?.quote_amount ?? 0);
    return {
      totalBaseAmount,
      totalQuoteAmount,
    };
  }
}
export default PoolTab;
</script>
