<template>
  <div class="intro">
    <slot name="pic"></slot>
    <div class="intro-text">
      <slot name="name"></slot>
    </div>
    <div class="contact-info">
      <slot name="details"></slot>
    </div>
  </div>
</template>

<style scoped>
.intro {
  display: flex;
  flex-flow: row nowrap;
  align-content: flex-start;
  justify-content: flex-start;
  align-items: center;
}

.intro-text {
  display: flex;
  flex: 1 1 auto;
  align-items: center;
  flex-direction: column;
}
</style>
