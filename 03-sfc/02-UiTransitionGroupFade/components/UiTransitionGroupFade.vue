<template>
  <TransitionGroup :tag="tag" name="fade-list" class="fade-list">
      <slot />
  </TransitionGroup>
</template>

<script>
export default {
  name: 'UiTransitionGroupFade',

  props: {
    tag: {
      type: [String, Object, Function],
      default: 'div',
    },
  },
};
</script>

<style scoped>
/* _transitions.css */

.fade-list {
  position: relative;
}

.fade-list :deep( > *) {
  opacity: 1;
  transition: opacity 0.3s ease-out;
}

.fade-list :deep(.fade-list-leave-active) {
  position: absolute !important;
  left: 0;
  right: 0;
}

.fade-list :deep(.fade-list-enter-from),
.fade-list :deep(.fade-list-leave-to) {
  opacity: 0;
}

.fade-list :deep(.fade-list-move) {
  transition: transform 0.3s;
}
</style>
