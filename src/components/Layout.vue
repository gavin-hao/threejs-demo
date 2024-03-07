<template>
  <div class="app-container">
    <div class="app-shell-header">
      <header class="app-header">
        <h1 class="app-logo">
          <a class="app-logo-link" href="/"><img class="icon" src="@/assets/tesla-logo.svg" alt="tesla" /></a>
        </h1>
        <div class="app-menu">
          <ol class="app-nav-items">
            <li>
              <span title="Locale Selector" special="localeSelectorNavItem" class="app-nav-item app-nav-item__locale">
                <img class="icon-globe" src="@/assets/locale.svg" alt="" />
                <span class="app-nav-item-text">CN</span></span
              >
            </li>
          </ol>
        </div>
      </header>
    </div>
    <div class="app-shell-content"><slot></slot></div>
    <footer class="app-shell-footer"></footer>
  </div>
</template>
<script setup lang="ts"></script>
<style lang="scss">
.app-container {
  --app-shell-header-height: 52px;
  --app-shell-footer-height: 52px;
  --app-shell-content-height: calc(100vh - var(--app-shell-header-height) - var(--app-shell-footer-height));
  display: grid;
  // grid-template-rows: 0 1fr 0 !important;
  grid-template-areas:
    'app-shell-masthead'
    'app-shell-content'
    'app-shell-footer';
  grid-template-rows: var(--app-shell-header-height) 1fr var(--app-shell-footer-height);

  grid-template-rows: 0 1fr 0 !important;
  grid-template-columns: auto;
  grid-gap: 0 24px;
  min-block-size: 100vh;
  .app-shell-header {
    position: sticky;
    top: 0;
    z-index: 1;
    width: 100%;

    // inline-size: 100%;
    // z-index: 10;
    // position: sticky;
    // top: 0;
    .app-header {
      position: relative;
      z-index: 10;
      display: flex;
      flex-flow: row wrap;
      justify-content: space-between;
      inline-size: 100%;
      min-block-size: var(--app-header-height);
      background: hsla(0, 0%, 100%, 0.75);
      backdrop-filter: blur(48px);
      .app-logo {
        display: flex;
        align-items: center;
        justify-content: flex-start;
        padding-inline-start: var(--app-size--1x);
        .app-logo-link {
          display: inline-flex;
          align-items: center;
          min-block-size: var(--app-size--4x);
          padding: 0 var(--app-size--4x);
          overflow: hidden;
          .icon {
            display: block;
            inline-size: calc(var(--app-icon--size) * 5);
            block-size: var(--app-icon--size);
            content: '';
          }
        }
      }
      .app-menu {
        position: static;
        display: flex;
        align-items: center;
        padding-inline-end: var(--app-size--1x);
        margin: 0;

        .app-nav-items {
          position: relative;
          display: flex;
          align-items: center;
          justify-content: flex-end;
          margin: 0;
          line-height: 20px;
          list-style-type: none;
          transition: transform 0.5s ease;
          .app-nav-item {
            display: inline-flex;
            align-items: center;
            inline-size: var(--app-nav-item--width);
            min-block-size: var(--app-size--4x);
            padding: calc(var(--app-size--1x) / 2) var(--app-size--1x);
            font-weight: var(--app-font-weight--medium);
            white-space: nowrap;
            transition:
              color 0.33s ease,
              background-color 0.33s ease;
            .app-nav-item-text {
              margin: 0 var(--app-size--1x);
              color: var(--app-nav-item--color);
              transition: color 0.33s ease;
            }
          }
          .app-nav-item__locale {
            .icon-globe {
              display: block;
              min-inline-size: var(--app-icon--size);
              max-inline-size: 100%;
              block-size: var(--app-icon--size);
              min-block-size: var(--app-icon--size);
              overflow: hidden;
              text-indent: -9999px;
              content: '';
            }
          }
        }
      }
    }
  }
  .app-shell-content {
    grid-area: app-shell-content;
    max-width: 100vw;
    min-block-size: var(--app-shell-content-height);
    min-height: 100vh;
  }
  .app-shell-footer {
    position: fixed;
    right: 10px;
    bottom: 0;
    left: 10px;
    display: flex;
    flex-flow: row nowrap;
    grid-area: app-shell-footer;
    width: 75%;
  }
}
:root {
  --app-header-height: 56px;
  --app-size--1x: 8px;
  --app-size--3x: 24px;
  --app-size--4x: calc(var(--app-size--1x) * 4);
  --app-icon--bg: transparent;
  --app-icon--size: 24px;
  --app-font-weight--medium: 500;
  --app-nav-item--width: auto;
  --app-color--black: #000;
  --app-color--blue10: #2e4994;
  --app-color--blue20: #3457b1;
  --app-color--blue30: #3e6ae1;
  --app-color--green: #12bb00;
  --app-color--grey10: #171a20;
  --app-color--grey15: #222;
  --app-color--grey20: #393c41;
  --app-color--grey25: #444;
  --app-color--grey30: #5c5e62;
  --app-color--grey35: #8e8e8e;
  --app-color--grey40: #a2a3a5;
  --app-color--grey45: #bbb;
  --app-color--grey50: #d0d1d2;
  --app-color--grey60: #e2e3e3;
  --app-color--grey65: #eee;
  --app-color--grey70: #f4f4f4;
  --app-color--red10: #b74134;
  --app-color--red20: #ed4e3b;
  --app-color--white: #fff;
  --app-color--yellow: #fbb01b;
  --app-text--white: #fff;
  --app-bezier: cubic-bezier(0.5, 0, 0, 0.75);
}
</style>
