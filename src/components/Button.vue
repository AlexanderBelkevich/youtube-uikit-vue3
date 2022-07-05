<script setup>
const props = defineProps({
  label: {
    type: String,
    default: 'Button'
  },
  color: {
    type: String,
    default: 'primary'
  },
  disabled: {
    type: Boolean,
    required: false
  },
  rounded: {
    type: Boolean,
    required: false
  },
  outlined: {
    type: Boolean,
    required: false
  },
  icon: {
    type: String,
    required: false
  },
  size: {
    type: String,
    default: 'normal'
  }
})

const emit = defineEmits(['click'])

const clickOnButton = () => {
  emit('click')
}
</script>

<template>
  <button
    :class="['btn', `btn_${color}`, {'btn_rounded': rounded}, {'btn_outlined': outlined}, {'btn_icon': icon}, {'btn_large': size === 'large'}]"
    :disabled="disabled"
    @click="clickOnButton">
      <span v-if="icon">
        <font-awesome-icon :icon="`fa-regular fa-${icon}`" />
      </span>
      <span v-else>{{label}}</span>
    </button>
</template>

<style lang="scss" scoped>
.btn {
  margin-right: 10px;
  margin-bottom: 10px;
  padding: 0 20px;
  height: 40px;
  color: #fff;
  border-radius: 7px;
  border: none;
  cursor: pointer;
  font-size: 15px;
  transition: .2s;
  &_primary {
    background: var(--primary);
    border: 1px solid var(--primary);
    &:enabled:hover {
      background: var(--primary-hover);
    }
  }
  &_second {
    background: var(--second);
    border: 1px solid var(--second);
    &:enabled:hover {
      background: var(--second-hover);
    }
  }
  &_success {
    background: var(--success);
    border: 1px solid var(--success);
    &:enabled:hover {
      background: var(--success-hover);
    }
  }
  &_info {
    background: var(--info);
    border: 1px solid var(--info);
    &:enabled:hover {
      background: var(--info-hover);
    }
  }
  &_warning {
    background: var(--warning);
    border: 1px solid var(--warning);
    &:enabled:hover {
      background: var(--warning-hover);
    }
  }
  &_danger {
    background: var(--danger);
    border: 1px solid var(--danger);
    &:enabled:hover {
      background: var(--danger-hover);
    }
  }
  &:disabled {
    opacity: .6;
    cursor: default;
  }
  &_rounded {
    border-radius: 15px;
  }
  &_outlined {
    background: transparent;
    color: #000;
    &:hover {
      color: #fff;
    }
  }
  &_icon {
    padding: 0;
    width: 40px;
    height: 40px;
    border-radius: 50%;
  }
  &_large {
    height: 48px;
    padding: 0 30px;
  }
}
</style>