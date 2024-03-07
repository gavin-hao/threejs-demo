<template>
  <div class="group-section--container" :data-group-id="id">
    <h1 class="text-loader--content tds-text--center text-loader--subtitle" tabindex="-1">
      <span>{{ name }}</span>
    </h1>
    <div style="filter: blur(0px); opacity: 1; transition: all 150ms var(--bezier)">
      <p
        class="estimated-delivery-date text-loader--BATTERY_AND_DRIVE tds--vertical_padding-bottom tds-text--center"
        data-id="estimated-delivery-date"
      >
        预计交付日期：{{ deliveryDate }}
      </p>
    </div>
    <div class="group-block specs-block tds--vertical_padding">
      <ol class="tds-list tds-list--horizontal tds-o-list--box" aria-live="polite" aria-atomic="true">
        <li class="tds-list-item tds-o-list-item">
          <div class="tds-text--h1 tds-list-item_title tds-text_color--black tds--no_padding" data-id="range">
            606<span class="specs--value-label">公里</span>
          </div>
          <span class="cf-range-est--container tds-text--caption" data-id="range-label"
            ><span>续航里程</span>
            <div data-id="top-speed-disclaimer-link">
              <button
                class="tds-link action-trigger--link text-loader--content tds-text--caption text-loader--range-info tds-link"
              >
                <span>CLTC综合工况</span>
              </button>
            </div></span
          >
        </li>
        <li class="tds-list-item tds-o-list-item">
          <div class="tds-text--h1 tds-list-item_title tds-text_color--black tds--no_padding" data-id="top-speed">
            200<span class="specs--value-label">公里/时</span>
          </div>
          <span class="tds-text--caption" data-id="top-speed-label">最高时速</span>
        </li>
        <li class="tds-list-item tds-o-list-item">
          <div class="tds-text--h1 tds-list-item_title tds-text_color--black tds--no_padding" data-id="acceleration">
            6.1<span class="specs--value-label">秒</span>
          </div>
          <span class="tds-text--caption" data-id="acceleration-label"><span>百公里加速</span></span>
        </li>
      </ol>
    </div>
  </div>
</template>
<script setup lang="ts">
export interface Props {
  id: string;
  name: string;
  deliveryDate: string;
  specs: {
    range: number;
    topSpeed: number;
    acceleration: number;
  };
}

withDefaults(defineProps<Props>(), { id: 'BATTERY_AND_DRIVE', name: 'Model 3', deliveryDate: '2-6 周' });
</script>
<!-- <style lang="scss" scoped></style> -->
