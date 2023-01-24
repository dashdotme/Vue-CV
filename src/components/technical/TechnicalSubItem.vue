<template>
  <div class="sub-item-box">
    <h3>
      <slot name="header"></slot>
    </h3>
    <ul class="bullets">
      <slot name="detail"></slot>
    </ul>
    <i>
      <slot name="score"></slot>
    </i>
    <div class="sub-item">
      <slot name="subTools"></slot>
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
i {
  display: flex;
  place-items: center;
  place-content: center;
}

.sub-item {
  padding: 0.25em;
}

.sub-item-box {
  text-align: center;
  vertical-align: text-top;
  display: inline-block;
  padding-right: 1.5em;
}

.sub-item.sub-item {
  transform: scale(0.7);
}

.sub-item-box:last-child {
  padding-right: 0;
}
</style>
