<template>
  <section class="item-row" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
    <infinite-panel :show-spinner="!onePage" :busy="loadingItem" :is-end="tplData.isEnd" @loadmore="loadMoreItems">
      <item-list :list="itemList"></item-list>
    </infinite-panel>
  </section>
</template>

<script>
// import infinitePanel from 'components/base/infinite-panel'
// import itemList from 'components/item/list'
// import API from 'api/api'

var Model = function() {
  return {
    errCount: 0,
    loadingItem: false,
    cantShowEndText: this.tplData.isEnd
  }
}

var Props = {
  tplData: {
    type: Object
  }
}

var ComputedModel = {
  onePage() {
    return this.tplData.count < 0
  },
  showEnd() {
    return this.$root.showGuide
  },
  itemList() {
    return this.tplData.itemList
  },
  isEnd() {
    return this.tplData.isEnd
  },
  boundaryId() {
    return this.tplData.startId
  },
  param() {
    var param = {
      mode: 'getItemList',
      actid: this.$parent.activityInfo.id,
      connid: this.tplData.connId
    }
    param['data[startId]'] = this.boundaryId
    return param
  }
}

var Components = {
  // infinitePanel,
  // itemList
}

export default {
  data: Model,
  props: Props,
  computed: ComputedModel,
  components: Components,
  methods: {
    async loadMoreItems() {
      this.loadingItem = true
      try {
        let res = await this.request.get(API.actgetdata, {
          params: this.param
        })
        console.log(res.data)
        if (res.data.errno == 0) {
          let _data = res.data.data

          this.tplData.isEnd = _data.isEnd
          this.tplData.itemList = this.tplData.itemList.concat(_data.itemList)
          this.tplData.startId = _data.startId
        } else {
          this.errCount++
          if (this.errCount >= 3) {
            this.tplData.isEnd = true
          }
        }
      } catch (e) {
        alert('网络错误')
        console.log(e)
      } finally {
        this.loadingItem = false
      }
    }
  }
}
</script>
