<template>
  <div class="contact-icon">
    <i>
      <slot name="icon"></slot>
    </i>
    <div class="contact-details">
      <h3>
        <slot name="heading"></slot>
      </h3>
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.contact-icon {
  margin-top: 0.2rem;
  display: flex;
}

.contact-details {
  flex: 1;
  margin-left: 1rem;
}

i {
  display: flex;
  place-items: center;
  place-content: center;
  width: 32px;
}

h3 {
  font-size: 1.2rem;
  font-weight: 500;
  margin-bottom: 0.4rem;
  color: var(--color-heading);
}
</style>
