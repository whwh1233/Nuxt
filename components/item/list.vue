<style>
.item-list {
  padding: 20px;
  background: #fff;
}

.item-list.item-list--single {
  padding: 0;
}

.item__el {
  float: left;
  margin-right: 2.536%;
  margin-bottom: 20px;
  width: 48.732%;
  border-radius: 12px;
  overflow: hidden;
}

.item__el:nth-of-type(2n + 2) {
  margin-right: 0;
}

.item__el--single {
  margin: 0 30px;
  padding: 30px 0;
  border-bottom: 1px solid #eee;
}

.item__el--single:last-of-type {
  border: 0;
}
</style>

<template>
  <div v-show="list && list.length" class="item-list" :class="{ 'item-list--single': single }">
    <ul class="cfix">
      <template v-if="single">
        <li v-for="(item, index) in list" :key="item.itemId" class="item__el--single">
          <item-element-single v-bind="$attrs" v-on="$listeners" :item="item" :index="index"></item-element-single>
        </li>
      </template>
      <template v-else>
        <li v-for="(item, index) in list" :key="item.itemId" class="item__el">
          <item-element v-bind="$attrs" v-on="$listeners" :item="item" :index="index"></item-element>
        </li>
      </template>
    </ul>
  </div>
</template>

<script>
import itemElement from './element'
import itemElementSingle from './element-single'

export default {
  props: {
    list: {
      type: Array,
      default() {
        return []
      }
    },
    single: {
      type: Boolean,
      default: false
    }
  },
  components: {
    itemElement,
    itemElementSingle
  }
}
</script>
