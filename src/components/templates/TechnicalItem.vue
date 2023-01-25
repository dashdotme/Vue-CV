<template>
  <div class="technical">
    <h2><slot name="header"></slot></h2>
    <div class="technical-children"><slot></slot></div>
  </div>
</template>

<style scoped>
.technical {
  text-align: center;
  padding-top: 0.5em;
}

.technical h2 {
  border-bottom: 1px solid #ccc;
  padding-bottom: 0.25em;
  margin-bottom: 0.25em;
  font-size: 132%;
}

.technical:first-child {
  padding-top: 0;
}

.technical:last-child {
  border: none;
}

.technical-children {
    font-size: 90%
}
</style>
