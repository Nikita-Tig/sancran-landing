<template>
  <div class="item" :class="$attrs.class">
    <div class="description">
      <h1 class="heading">
        <slot name="heading"></slot>
      </h1>
      <h2 v-if="$slots.subHeading" class="sub-heading">
        <slot name="subHeading"></slot>
      </h2>
      <div v-if="$slots.default" class="default">
        <slot></slot>
      </div>
      <div v-if="$slots.extra" class="extra">
        <slot name="extra"></slot>
      </div>
    </div>
    <div v-if="$slots.illustration" class="illustration">
      <slot name="illustration"></slot>
    </div>
  </div>
</template>

<style scoped>
.item {
  display: flex;
  flex-direction: column;
  contain: content;
  width: 100%;
  max-width: 1200px;
  min-width: 360px;
  background: var(--color-background-soft);
}

.heading {
  font: var(--font-h1);
}

.sub-heading {
  font: var(--font-h2);
}

.description {
  display: flex;
  flex-direction: column;
  width: 100%;
  padding: 12px;
  gap: 8px;
  background-color: var(--color-background-soft);
  z-index: 1;
}

.illustration {
  display: flex;
  align-items: center;
  justify-content: center;
  max-height: 450px;
  width: 100%;
}

@media (min-width: 1024px) {
  .item {
    position: relative;
    flex-direction: row;
    background: var(--color-background-soft);
  }

  .item.right {
    flex-direction: row-reverse;
  }

  .item.center {
    padding: 48px;
  }

  .description {
    display: flex;
    flex-direction: column;
    gap: 32px;
    height: 100%;
    width: 40%;
    min-width: 530px;
    min-height: 660px;
  }

  .left .description {
    background: linear-gradient(
      95deg,
      var(--color-background-soft) 85%,
      var(--color-separator) 86%,
      transparent 90%
    );
    padding: 48px 48px 12px;
  }

  .right .description {
    background: linear-gradient(
      275deg,
      var(--color-background-soft) 85%,
      var(--color-separator) 86%,
      transparent 90%
    );
    padding: 48px 48px 12px 96px;
  }

  .center .description {
    width: 100%;
  }

  .illustration {
    justify-content: start;
    max-height: 660px;
    position: relative;
    top: 0;
  }

  .left .illustration {
    left: -8%;
  }

  .right .illustration {
    right: -8%;
  }
}
</style>
