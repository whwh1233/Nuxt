<template>
  <div class="container">
    <div class="links">
      <a href="/index" rel="noopener noreferrer" class="button--green">
        index
      </a>
    </div>
    <div class="message">
      <h1>{{ dataList }}</h1>
      <br />
      <h2>{{ activityInfo.title }}</h2>
    </div>
    <section v-show="dataList" class=" cfix">
      <div v-for="(tplData, tplIndex) in dataList" :key="tplIndex">
        <h5>模块：{{ tplData.tpl }}</h5>
        <div v-if="tplData.tpl !== 'm56'">
          <component :is="tplData.tpl" :tpl-data="tplData" :activityId="activityInfo.id"></component>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  methods: {},

  async asyncData({ $axios }) {
    const activity = await $axios.$post('http://52.81.25.5:8081/o/uc/1.0/uiww/activity?id=6440')
    let data = activity.data
    console.log(data)
    let dataList = data.tplDataList
    let activityInfo = data.activityInfo
    return { dataList, activityInfo }
  }
}
</script>

<style>
h1 {
  height: 200px;
  overflow: auto;
}

.container {
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.links {
  padding-top: 15px;
}
</style>
