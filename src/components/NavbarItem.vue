<template>
  <li :is="tag" :class="[className, {'ripple-parent': waves}]" @click="wave">
    <router-link :to="to" class="nav-link"><slot></slot></router-link>
  </li>
</template>

<script>
import classNames from 'classnames';
import waves from '../mixins/waves';

export default {
  props: {
    tag: {
      type: String,
      default: 'li'
    },
    active: {
      type: Boolean,
      default: false
    },
    to: {
      type: String,
      default: '/'
    },
    waves: {
      type: Boolean,
      default: true
    },
    wavesFixed: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      className: classNames(
        'nav-item',
        this.active ? 'active' : ''
      )
    };
  },
  mixins: [waves]
};
</script>

<style scoped>

</style>
