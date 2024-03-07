<template>
  <Card class="card-scrim-black">
    <div class="">
      <strong class="text-loader--content card-text--body" tabindex="-1"><span>春日礼遇-限时现车福利</span></strong>
      <div class="text-loader--content card-text--caption" tabindex="-1">
        <span
          >现款Model 3后轮驱动版现车，通过合作保险机构购买相应车险，可享 8000元保险补贴，需3月31日前交付<br /><br />现款及原款Model
          3现车，指定付费车漆仅需2000元（差价在交付前减免），需3月31日前交付<br /><br />现款及原款Model
          3后轮驱动版现车，可申请年费率低至1.99%起（折合年化利率3.65%起，适用于部分银行），其他在售现车年费率低至2.5%起（折合年化利率4.58%起），需3月31日前交付<br /><br /><a
            href="https://www.tesla.cn/inventory/new/m3?TRIM=M3RWD"
            class="card-link result-disclaimer-button"
            target="_blank"
            rel="noopener noreferrer"
            >抢购现车</a
          ></span
        >
      </div>
    </div>
  </Card>
</template>
<script setup lang="ts">
import Card from '@/components/Card.vue';
</script>
<style lang="scss" scoped>
.card-scrim-black {
  margin-top: var(--app-size--1x);
  color: var(--app-text--white);
  background: radial-gradient(ellipse at 50% -50%, #6c94ff 0, #000 100%);
}
.text-loader--content {
  outline: none;
}
.card-text-body {
  font-size: 14px;
  line-height: 20px;
}
.card-text--caption {
  padding-block-start: 12px;
  padding-top: var(--app-size-1x);
  font-size: 12px;
  line-height: 18px;
  .card-link {
    position: relative;
    padding: 0;
    font-size: 12px;
    font-weight: 400;
    color: var(--app-color--white);
    text-align: initial;
    cursor: pointer;
    background-color: transparent;
    border: 0;
    box-shadow: 0 1px 0 0 currentColor;
    transition:
      box-shadow 0.33s var(--app-bezier),
      color 0.33s ease;
    &:hover {
      box-shadow: 0 2px 0 0 currentColor;
    }
  }
}
</style>
