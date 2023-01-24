<template>
  <div class="content-item">
    <h2><slot name="title"></slot></h2>
    <h3><slot name="subtitle"></slot></h3>
    <h4><slot name="period"></slot></h4>
    <h4><slot name="location"></slot></h4>
    <p class="with-bullets"><slot name="blurb"></slot></p>
    <slot name="detail"></slot>
  </div>
</template>

<style scoped>
.content-item {
  margin-bottom: 0.75em;
  padding-bottom: 0.75em;
  border-bottom: 1px solid #ccc;
  display: block;
  position: relative;
}

.content-item p {
  margin: 0.75em 0 1em 0;
}

p.with-bullets {
  margin-bottom: 0;
}
ul.bullets {
  padding-left: 2em;
  padding-inline-start: 0;
}

.content-item h4 {
  position: absolute;
  top: 0.35em;
  right: 0;
  text-align: center;
}

.content-item.last {
  border: none;
  padding-bottom: 0em;
  margin-bottom: 0.5em;
  margin-top: 0em;
}
</style>
