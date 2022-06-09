<template>
  <div class="color-type">
    <input v-model="modelColor" class="value" />
  </div>
</template>

<script lang="ts">
import { computed, defineComponent } from 'vue'

export default defineComponent({
  props: {
    name: {
      type: String,
      default: '',
    },
    color: {
      type: String,
      default: '',
    },
  },
  emits: ['inputColor'],
  setup(props, { emit }) {
    const modelColor = computed({
      get() {
        return props.color || ''
      },
      set(val) {
        emit('inputColor', val)
      },
    })
    return {
      modelColor,
    }
  },
})
</script>

<style lang="scss">
.color-type {
  display: flex;
  margin-top: 0px;
  font-size: 12px;
  .value {
    flex: 1;
    height: 30px;
    width: 80px;
    min-width: 60px;
    padding: 0 10px;
    border: 0;
    color: #fff;
    background: #2e333a;
    box-sizing: border-box;
  }
}
</style>
