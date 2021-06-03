<style>
.m30_fix {
  position: sticky;
  top: 0px;
}
.m30__anchor__el {
  float: left;
}
.m30__anchor__link {
  background: no-repeat center/cover;
}
.m30__anchor__img {
  display: block;
  width: 100%;
}
.m30__anchor-list {
  content: '';
  display: block;
  clear: both;
}
.m30__anchor-list--1 .m30__anchor__el {
  width: 100%;
}
.m30__anchor-list--2 .m30__anchor__el {
  width: 50%;
}
.m30__anchor-list--3 .m30__anchor__el {
  width: 33.3333%;
}
.m30__anchor-list--4 .m30__anchor__el {
  width: 25%;
}
.m30__anchor-list--5 .m30__anchor__el:nth-of-type(-n + 3) {
  width: 33.3333%;
}
.m30__anchor-list--5 .m30__anchor__el:nth-of-type(n + 4) {
  width: 50%;
}
.m30__anchor-list--6 .m30__anchor__el {
  width: 33.3333%;
}
.m30__anchor-list--7 .m30__anchor__el:nth-of-type(-n + 4) {
  width: 25%;
}
.m30__anchor-list--7 .m30__anchor__el:nth-of-type(n + 5) {
  width: 33.3333%;
}
.m30__anchor-list--8 .m30__anchor__el {
  width: 25%;
}
.m30__anchor-list--9 .m30__anchor__el:nth-of-type(-n + 8) {
  width: 25%;
}
.m30__anchor-list--9 .m30__anchor__el:nth-of-type(n + 9) {
  width: 100%;
}
.m30__anchor-list--10 .m30__anchor__el:nth-of-type(-n + 8) {
  width: 25%;
}
.m30__anchor-list--10 .m30__anchor__el:nth-of-type(n + 9) {
  width: 50%;
}
.m30__anchor-list--11 .m30__anchor__el:nth-of-type(-n + 8) {
  width: 25%;
}
.m30__anchor-list--11 .m30__anchor__el:nth-of-type(n + 9) {
  width: 33.3333%;
}
.m30__anchor-list--12 .m30__anchor__el {
  width: 25%;
}
.m30__anchor-list--multi .m30__anchor__el {
  width: 25%;
}
.m30 {
  z-index: 1001;
}
</style>

<template>
  <section class="m30" :class="navFixed ? 'm30_fix' : ''">
    <ul class="m30__anchor-list cfix" :class="'m30__anchor-list--' + size" :data-sort="tplData.sort">
      <li class="m30__anchor__el" v-for="obj in tplData.imgList" :key="$index">
        <a class="m30__anchor__link" @click.stop="judge(obj.linkId)" :style="{ backgroundImage: 'url(' + obj.bgImg + ')' }">
          <img class="m30__anchor__img" :src="obj.bgImg" />
        </a>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  props: {
    tplData: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  computed: {
    navFixed() {
      return this.tplData.fixTop === 'on'
    },
    size() {
      let l = this.tplData.imgList.length
      return l
    },
    $anchorList() {
      return document.querySelector('.m30__anchor-list')
    }
  },
  methods: {
    goAnchor(_id) {
      var $dom = document.querySelector('[data-anchor-id="' + _id + '"]')
      if (!$dom) {
        return
      }
      var _t
      var $anchorList = this.$anchorList
      // var _anchorTop = $anchorList.getBoundingClientRect().top,
      //     _domTop = $dom.getBoundingClientRect().top;
      var _h = 0
      var domSort = Number($dom.dataset.sort) || 1,
        anchorSort = Number($anchorList.dataset.sort) || 0
      if (this.navFixed && domSort > anchorSort) {
        _h += $anchorList.getBoundingClientRect().height
      }
      _t = $dom.offsetTop - _h
      var _now = window.scrollY
      var _diff = _t - _now
      var eachDiff = parseInt(Math.abs(_diff) / 10) < 500 ? (_diff > 0 ? 500 : -500) : parseInt(_diff / 10)
      var _timer = setInterval(function() {
        if (Math.abs(_diff) <= 500) {
          clearInterval(_timer)
          _now = _now + _diff
          window.scrollTo(0, _now)
          return
        } else {
          _diff = _diff - eachDiff
          _now = _now + eachDiff
          window.scrollTo(0, _now)
        }
      }, 30)
    },
    judge(val) {
      if (isNaN(parseInt(val))) {
        this.navTo(val)
      } else {
        this.goAnchor(val)
      }
    }
  },
  mounted() {
    if (this.tplData.fixBottom == 'on') {
      var $lastImg = document.querySelectorAll('.m30__anchor-list--' + this.size + ' .m30__anchor__img')
      $lastImg[$lastImg.length - 1].addEventListener('load', () => {
        var $dom = document.querySelector('.m30__anchor-list--' + this.size)
        document.body.style.paddingBottom = $dom.getBoundingClientRect().height + 'px'
        $dom.parentNode.style.cssText = 'position:fixed;bottom:0px;width:100%'
      })
    }
  }
}
</script>
