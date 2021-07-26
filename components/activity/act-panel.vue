<template>
  <section v-show="dataList" class="cfix">
    <template v-for="tplData in dataList" track-by="$index">
      <component :is="tplData.tpl" :tpl-data="tplData" :activity-info="activityInfo" :activityId="activityInfo.id"></component>
    </template>
  </section>
</template>

<script>
import Vue from 'vue'
// import errorVue from '../../../nuxtjs.org/layouts/error.vue'
// import './activity.css'
// import API from 'api/api'

export default {
  data() {
    return {
      dataList: [],
      activityInfo: []
    }
  },
  props: {
    url: {
      type: String,
      default: ''
    },
    id: {
      type: String,
      default: ''
    }
    // 禁止显示模块组
    // limit: {
    //   type: Array,
    //   default: []
    // }
  },
  computed: {
    actUrl() {
      if (this.id) {
        return `${API.activity}?id=${this.id}`
      }
      let url = this.url
      if (this.isApp && this.url.toLowerCase().indexOf('isapp') < 0) {
        let _appVersion = this.urlUtil.getParam('isapp') || 1
        url = `${url}&isapp${_appVersion}`
      }
      return url.replace('/m/', '/1.0/')
    }
  },
  async fetch() {
    console.log('fetch in act-panel :')
    console.log(this.id)
    let api = 'https://apidev.bangbangtown.cn/o/uc/1.0/uiww/activity?id=' + this.id
    let res = await fetch(api).then(res => res.json())
    if (!res) throw err
    let data = res.data
    this.dataList = data.tplDataList
    this.activityInfo = data.activityInfo
  },
  mounted() {
    // console.log('act-panel:')
    // console.log(this.id)
  }
  // async mounted() {
  //   try {
  //     let res = await this.request.get(this.actUrl)
  //     // let res = await $axios.$post('https://apidev.bangbangtown.cn/o/uc/1.0/uiww/activity?id=3000')
  //     res = res.data
  //     let data = res.data
  //     if (res.errno !== 0) {
  //       return
  //     }
  //     this.dataList = data.tplDataList
  //     this.activityInfo = data.activityInfo
  //     this.activityInfo.activityUrl = window.location.origin + this.actUrl
  //     // this.$emit('actpanel-loaded', this.activityInfo)

  //     let oCSS = data.activityInfo.baseCss
  //     let bgc = oCSS && oCSS.bgcolor ? oCSS.bgcolor : '#FFFFFF'
  //     this.$el.style.backgroundColor = bgc

  //     var obj = {}
  //     var tplDataList = data.tplDataList
  //     //TODO
  //     //动态加载组件的代码删去
  //     // for (let index in tplDataList) {
  //     //   this.dataList[index]['sort'] = index
  //     //   if (tplDataList.hasOwnProperty(index)) {
  //     //     var tpl = tplDataList[index]['tpl']
  //     //     if (tpl && !obj[tpl] && this.limit.indexOf(tpl) === -1) {
  //     //       let path = `src/components/activity/${tpl}.vue`
  //     //       Vue.component(tpl, require(path).default)
  //     //       obj[tpl] = true
  //     //     }
  //     //   }
  //     // }
  //   } catch (e) {
  //     console.error(e)
  //   }
  // }
}
</script>

<style></style>
