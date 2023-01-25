<template>
  <div class="yui-gf">
    <div class="yui-u first">
      <h2>
        <slot name="heading"></slot>
      </h2>
    </div>
    <div class="yui-u">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.yui-gf {
  margin-bottom: 1.25em;
  padding-bottom: 1.25em;
  border-bottom: 1px solid #ccc;
  display: block;
}

.yui-gf:last-child {
  border: none;
  padding-bottom: 1em;
  margin-bottom: 1em;
  margin-top: 1em;
}

.yui-u.first {
  width: 12.3%;
}

.yui-u:first-child h2 {
  font-style: italic;
  font-size: 152%;
}

.yui-u {
  width: 80.2%;
  float: right;
}
</style>
