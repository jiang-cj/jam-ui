<template>
  <button
    class="jam-button"
    :class="[
      type ? 'jam-button--' + type : '',
      size ? 'jam-button--' + size : '',
      {
        'is-plain': plain,
        'is-round': round,
        'is-dashed': dashed,
        'is-disabled': disabled,
        'is-text': text,
        'is-loading': loading,
      },
    ]"
  >
    <i v-if="icon && !loading" :class="iconClass"></i>
    <i v-if="loading" style="font-size: 14px" class="iconfont jam-loading"></i>
    <span>
      <slot></slot>
    </span>
  </button>
</template>
<script>
import "./index.scss";
export default {
  name: "jamButton",
  components: {},
  props: {
    type: {
      type: String,
      default: "default",
    },
    plain: {
      type: Boolean,
      default: false,
    },
    round: {
      type: Boolean,
      default: false,
    },
    dashed: {
      type: Boolean,
      default: false,
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      default: "medium",
    },
    text: {
      type: Boolean,
      default: false,
    },
    icon: {
      type: String,
      default: "",
    },
    loading: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    iconClass() {
      return this.icon ? `iconfont ${this.icon}` : "";
    },
  },
};
</script>
<style scoped>
/* @import url('./index.scss'); */
</style>