<template>
  <div class="container">
    <div class="links">
      <a href="/" rel="noopener noreferrer" class="button--green">
        index
      </a>
    </div>
    <h1>{{ activityInfo.title }}</h1>

    <div class="message">
      <!-- <h2>{{ dataList }}</h2> -->
      <br />
    </div>

    <div class="message">
      <!-- <h2>{{ activityInfo }}</h2> -->
      <br />
    </div>

    <section v-show="dataList" class=" cfix">
      <div v-for="(tplData, tplIndex) in dataList" :key="tplIndex">
        <h5>模块：{{ tplData.tpl }}</h5>
        <div>
          <component :is="tplData.tpl" :tpl-data="tplData" :activityId="activityInfo.id"></component>
        </div>
      </div>
    </section>

    <!-- 删除了v-if：v-if="!hideFixedButton"-->
    <template>
      <shortcut></shortcut>
      <back-top></back-top>
    </template>
  </div>
</template>

<script>
// activityId
// 3647
// 2905
// 6430
export default {
  methods: {},

  async asyncData({ $axios }) {
    const activity = await $axios.$post('https://apidev.bangbangtown.cn/o/uc/1.0/uiww/activity?id=6430')
    let data = activity.data
    let dataList = []
    let activityInfo = {}
    if (data) {
      dataList = data.tplDataList || []
      activityInfo = data.activityInfo || {}
    }
    return { dataList, activityInfo }
  }
}
</script>

<style>
h1 {
  height: 200px;
  overflow: auto;
  font-size: 100px;
}

.message {
  height: 200px;
  margin-bottom: 20px;
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

.banner__row {
  display: flex;
  align-items: center;
  font-size: 0;
}

.banner__el {
  display: block;
  flex: 1;
  width: 100%;
}

.banner__img {
  display: block;
  width: 100%;
}
</style>
