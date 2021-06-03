<style scoped>
.spinner {
  padding: 50px 0;
  color: #aaa;
  text-align: center;
  clear: both;
}

.spinner__icon {
  display: inline-block;
  vertical-align: middle;
  margin-right: 12px;
}
</style>

<template>
  <div>
    <div v-infinite-scroll="loadMore" :infinite-scroll-disabled="disabled" infinite-scroll-distance="400">
      <slot></slot>
      <div v-show="!isEnd" class="spinner"><img class="spinner__icon" src="~/assets/images/loading.gif" />加载中</div>
      <div v-if="showSpinner">
        <div class="spinner" v-show="isEnd">没有更多啦</div>
      </div>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'

export default {
  data() {
    return {}
  },
  props: {
    busy: {
      type: Boolean,
      default: false
    },
    isEnd: {
      type: Boolean,
      default: false
    },
    showSpinner: {
      type: Boolean,
      default: true
    }
  },
  computed: {
    disabled() {
      return this.isEnd || this.busy
    }
  },
  methods: {
    loadMore() {
      if (this.disabled) return
      this.$emit('loadmore')
    }
  }
}
</script>
