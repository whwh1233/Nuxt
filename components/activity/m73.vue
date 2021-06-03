<style>
.m73__container {
  display: flex;
  align-items: center;
  margin: 20px auto;
  width: 66.66667%;
  height: 120px;
  border-radius: 10px;
  background: rgba(0, 0, 0, 0.75);
}

.m73__img {
  display: block;
  margin-left: 10px;
  width: 70px;
  height: 100px;
  border-radius: 5px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
.m73__rest {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-left: 20px;
  margin-right: 10px;
  height: 84px;
  overflow: hidden;
}
.m73__text {
  width: 100%;
  color: #fff;
  font-size: 22px;
  line-height: 1;
}
.m73__text--rd {
  color: #f95555;
}
.m73__flex {
  display: flex;
  flex-direction: column;
}
.m73__user {
  display: flex;
  align-items: center;
  color: #999999;
}
.m73__user:before {
  display: block;
  content: '恭喜';
  margin: 0 10px 0 0;
  color: #f95555;
}
.m73__user:after {
  display: block;
  content: '购买的';
  margin: 0 0 0 10px;
  color: #ffffff;
}
</style>

<template>
  <top-notice :show="!!noticeFlag">
    <div @click.stop="link" class="m73__container">
      <template v-if="noticeFlag">
        <div class="m73__img" :style="notice ? 'background-image:url(' + notice.picUrl + ')' : ''"></div>
        <div class="m73__rest">
          <p class="m73__text m73__flex">
            <span class="m73__user truncate">{{ notice ? notice.user : '' }}</span>
          </p>
          <p class="m73__text truncate">{{ notice ? notice.name : '' }}</p>
          <p class="m73__text m73__text--rd">被免单了</p>
        </div>
      </template>
    </div>
  </top-notice>
</template>

<script>
//TODO
// import TopNotice from 'top-notice'

export default {
  data() {
    return {
      notice: null,
      noticeFlag: true,
      topNoticeTop: ''
    }
  },
  props: {
    tplData: {
      type: Object,
      default: () => {}
    }
  },
  computed: {
    itemList() {
      let list = this.shuffle(
        this.tplData.itemList.map(item => {
          item.user = item.user.replace(/./g, (m, i) => {
            return i > 0 ? '*' : m
          })
          return item
        })
      )
      console.log(list)
      return list
    }
  },
  components: {
    // TopNotice
  },
  methods: {
    shuffle(array, size) {
      var index = -1,
        length = array.length,
        lastIndex = length - 1
      size = size === undefined ? length : size
      while (++index < size) {
        var rand = index + Math.floor(Math.random() * (lastIndex - index + 1))
        let value = array[rand]
        array[rand] = array[index]
        array[index] = value
      }
      array.length = size
      return array
    },
    link() {
      if (!this.notice) return
      this.navTo(this.notice.itemUrl)
    }
  },
  mounted() {
    let i = 0
    let showNotice = () => {
      if (++i === this.itemList.length) {
        i = 0
      }
      this.notice = this.itemList[i]
      this.noticeFlag = true
      setTimeout(() => {
        this.noticeFlag = false
      }, 2500)
    }
    setInterval(() => {
      showNotice()
    }, 10000)
    showNotice()
  }
}
</script>
