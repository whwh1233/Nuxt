<template>
  <div class="container">
    <div class="links">
      <a href="/" rel="noopener noreferrer" class="button--green">
        index
      </a>
    </div>
    <div class="detail">
      <div class="detail__c2cskuinfo">
        {{ detail.data.c2cSkuInfo }}
        <br />
        {{ detail.data.c2cSkuInfo.content }}
        <br />
        <img :src="detail.data.c2cSkuInfo.picList[0].picUri" style="width:200px;height:200px" />
        <br />
        {{ detail.data.c2cSkuInfo.deliveryAddress }}
      </div>
      <br />
      <div class="detail__userInfo">
        {{ detail.data.userInfo }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // detail: '暂无信息'w
    }
  },
  async asyncData({ $axios }) {
    const detail = await $axios.$post('http://apidev.bangbangtown.cn/o/cc/1.0/uic2c/getSellC2cSku', {
      c2cSkuId: 1001168
    })
    // console.log(detail.data.c2cSkuInfo)
    return { detail }
  }
}
</script>

<style scoped>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.detail {
  width: 60%;
}
</style>
