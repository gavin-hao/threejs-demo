<template>
  <div class="showroom-container">
    <div class="car-show-container"></div>
    <div class="car-option-container">
      <div class="option-group-container">
        <div class="aside-section flex-section">
          <Banner />
        </div>
        <div class="aside-section">
          <div class="">
            <!-- <Specs id="BATTERY_AND_DRIVE" /> -->
          </div>
        </div>
      </div>
      <div></div>
    </div>
  </div>
</template>
<script setup lang="ts">
import Banner from './components/Banner.vue';
// import Specs from './components/Specs.vue';
</script>
<style lang="scss">
.showroom-container {
  --app-size--6x: calc(var(--app-size--1x) * 6);
  display: grid;
  grid-template: 'main aside' 1fr/9fr minmax(320px, 1fr);
  grid-gap: 0 var(--app-size--6x);
  height: 100%;
  padding-inline-end: var(--app-size--6x);
  scroll-margin-top: var(--app-shell-header-height);
  .car-show-container {
    position: sticky;
    top: 0;
    grid-area: main;
    height: 100vh;
    max-height: 100%;
    overflow: hidden;
    background-color: aliceblue;
  }
  .car-option-container {
    grid-area: aside;
    overflow: visible;

    > :first-child {
      padding-top: var(--app-shell-header-height);
    }
    // .aside-section {
    // }
    .flex-section {
      display: flex;
      flex-flow: column wrap;
      justify-content: center;
      padding: 0;
      margin: 0;
      list-style: none;
    }
    @media (min-width: 600px) {
      .flex-section {
        flex-flow: row wrap;
      }
    }
  }
}
</style>
