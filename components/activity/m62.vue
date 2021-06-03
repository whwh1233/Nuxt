<style scoped>
.m62-group-list {
  margin: 25px;
}

.m62-group__el {
  position: relative;
  display: block;
  margin-bottom: 24px;
}

.m62-group__el:before {
  content: '';
  position: absolute;
  top: 58px;
  left: 30px;
  right: 30px;
  display: block;
  height: 221px;
  border-radius: 40px;
  z-index: 0;
}

.m62__wrapper {
  position: relative;
  display: flex;
  align-items: center;
  height: 280px;
  border-radius: 40px;
  background: #fff;
  z-index: 1;
}

.m62-group__img {
  position: relative;
  width: 280px;
  height: 280px;
  border-radius: 40px 0 0 40px;
  background: no-repeat center/contain;
}

.m62-group__img:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 40px 0 0 40px;
  background: rgba(0, 0, 0, 0.02);
}

.m62-group__info {
  flex: 1;
  margin: 18px 30px 13px 22px;
}

.m62__top {
  height: 120px;
}

.m62__groupsize {
  padding: 2px 11px;
  color: #dbb676;
  font-size: 20px;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
  border: 2px solid #dbb676;
  border-radius: 10px;
  background: #fff9ea;
}

.discount__group {
  color: #c68f61;
  border: 2px solid #c68f61;
  background: #fff9f3;
}

.m62__brand {
  flex: 1;
  margin-left: 16px;
  color: #bbb;
  font-size: 28px;
}

.m62__name {
  margin-top: 9px;
  height: 72px;
  line-height: 36px;
  font-size: 28px;
}

.m62__name span {
  display: inline-block;
  vertical-align: middle;
}

.m62__name .m62__name__txt {
  display: inline;
}

.m62__unlimit {
  margin-right: 4px;
  width: 80px;
  height: 36px;
  color: #fff;
  font-size: 20px;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
  line-height: 36px;
  text-align: center;
  border-radius: 8px;
  background: linear-gradient(180deg, #f5515f, #e72341);
}

.m62__prefix {
  margin-top: 35px;
  font-size: 20px;
  color: #fb5352;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
}

.m62__price {
  display: flex;
  align-items: center;
  margin-top: -5px;
  color: #fb5352;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
}

.m62__sellprice__unit {
  margin-top: 14px;
  font-size: 30px;
}

.m62__sellprice {
  margin-right: 16px;
  font-size: 50px;
}

.m62__originprice {
  margin-top: 14px;
  color: #aaa;
  font-family: PingFangSC-Regular, PingFangTC-Regular, PingFangHK-Regular, sans-serif;
  font-weight: normal;
  text-decoration: line-through;
}

.m62__btn {
  position: absolute;
  right: 26px;
  bottom: 26px;
  width: 130px;
  height: 52px;
  color: #fff;
  font-size: 24px;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
  line-height: 52px;
  text-align: center;
  border-radius: 26px;
  background: linear-gradient(180deg, #ff9f74 0, #fe5f3a 100%);
  box-shadow: 0 4px 6px 0 #ffd0c0;
}

.m62__btn--pre {
  background: linear-gradient(180deg, #acacac 0, #9b9b9b 100%);
  box-shadow: 0 4px 6px 0 #e0e0e0;
}

.sale_num {
  padding: 4px 16px;
  background: rgba(255, 231, 231, 1);
  border-radius: 8px;
  font-family: PingFangSC-Semibold;
  color: #f95555;
  font-size: 20px;
  display: inline-block;
  font-style: italic;
  font-weight: bold;
}
.m62__soldout-img,
.m62__remain-img {
  position: absolute;
  display: block;
  top: 50%;
  left: 50%;
  margin: -98px 0 0 -98px;
  width: 196px;
  height: 196px;
  z-index: 80;
}
</style>

<template>
  <div class="m62-group-list">
    <navigator v-for="(group, index) in groupList" :key="index" class="m62-group__el" :url="group.groupUrl" :self-data="group.selfData" data-emergence="hidden" prefix="m62">
      <div class="m62__wrapper">
        <div class="m62-group__img" :style="{ backgroundImage: 'url(' + group.itemPicUrl + ')' }">
          <template v-if="group.soldOut">
            <img src="https://pic.wanwustore.cn/Fp01CrHd8u_xRY-wY8e0_bFJWJXW" class="m62__soldout-img" />
          </template>
          <template v-else>
            <img v-if="group.itemStatus && group.itemStatus === 'ready'" src="https://pic.wanwustore.cn/FumoB7hgF5Nda_yt7byUbK6w7Bs-" class="m62__remain-img" />
          </template>
        </div>
        <div class="m62-group__info">
          <div class="m62__top" :style="{ paddingTop: !group.saleText ? '10px' : '' }">
            <!-- <div class="m62__groupsize" :class="{'discount__group':groupType==='discount'}">{{groupType==='discount'?'阶梯团':group.groupPerNum+'人团'}}</div>
            <p class="m62__brand line line-1">{{group.brandName}}</p> -->
            <div class="sale_num" v-if="group.saleText">{{ group.saleText }}</div>
            <div class="m62__name line line-2">
              <span v-if="group.groupType == 2" class="m62__unlimit">无限续</span><span class="m62__name__txt">{{ group.groupName }}</span>
            </div>
          </div>
          <p class="m62__prefix">{{ groupType === 'discount' ? '最低到手价:' : '拼团价:' }}</p>
          <div class="m62__price">
            <p class="m62__sellprice__unit">￥</p>
            <p class="m62__sellprice">{{ group.sellPrice }}</p>
            <p v-if="group.originPrice" class="m62__originprice">{{ group.originPrice }}</p>
          </div>
          <div class="m62__btn" :class="{ 'm62__btn--pre': !group.active }">{{ group.btnStr }}</div>
        </div>
      </div>
    </navigator>
  </div>
</template>

<script>
export default {
  props: {
    tplData: {
      type: Object,
      default() {
        return {}
      }
    },
    activityId: {
      type: String,
      default: ''
    }
  },
  computed: {
    groupType() {
      return this.tplData.groupType
    },
    btnStr() {
      return '去开团'
    },
    groupList() {
      if (!this.tplData.groupInfoList) return []
      return this.tplData.groupInfoList.map((group, index) => {
        if (group.groupStatus === 10) {
          let date = new Date(group.startTime * 1000)
          let d = date.getDate()
          let hour = date.getHours()
          group.active = false
          group.btnStr = `未开始`
        } else if (group.groupStatus === 20) {
          group.active = true
          group.btnStr = this.btnStr
        } else {
          group.active = false
          group.btnStr = '已结束'
        }
        // 埋点
        let obj = {
          eleType: 'groupItem',
          activityTpl: 'm62',
          connid: this.tplData.connId,
          itemId: group.itemId,
          groupId: group.groupId,
          logId: group.logId,
          activityId: this.activityId,
          index: index,
          realItemId: group.realItemId
        }
        let selfData = JSON.stringify(obj)
        this.$set(this.tplData.groupInfoList[index], 'selfData', selfData)
        return group
      })
    }
  }
}
</script>
