<template>
  <div class="navbar">
    <!-- phần logo box  -->
    <div class="logo_box">
      <div class="icon"></div>
      <div class="title">QLTS.VN</div>
      <div class="toogle" @click="handleClick(false)"></div>
    </div>
    <!-- end phần logo box -->
    <div class="nav_box">
      <div
        class="nav_item"
        v-for="(item, index) in nav"
        :key="index"
        @click="hightline_navitem(index)"
        :class="{ item_selected: item.nav_selected }"
        ref="nav_item"
      >
        <div class="highline" v-show="item.nav_selected"></div>
        <div class="nav_item_icon" :class="item.nav_icon"></div>
        <div class="nav_item_content">{{ item.nav_item }}</div>
        <div class="small_arrow" v-if="item.small_arrow"></div>
        <div class="sub_menu" v-show="item.nav_selected">
          <div
            class="sub_menu_item"
            v-for="(sub_item, index) in item.sub_menu"
            :key="index"
          >
            {{ sub_item.sub_item_name }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      item_selected: "item_selected",
      nav: [
        {
          small_arrow: false,
          nav_item: "Tổng quan",
          nav_selected: false,
          nav_icon: "overview_icon",
        },
        {
          small_arrow: true,
          nav_item: "Tài sản",
          nav_selected: false,
          nav_icon: "asset_icon",
          sub_menu: [
            { sub_item_name: "Ghi tăng" },
            { sub_item_name: "Điều chuyển" },
            { sub_item_name: "Tính hao mòn" },
            { sub_item_name: "Ghi giảm" },
          ],
        },
        {
          small_arrow: true,
          nav_item: "Công cụ dụng cụ",
          nav_selected: false,
          nav_icon: "tool_icon",
        },
        {
          small_arrow: true,
          nav_item: "Danh mục",
          nav_selected: false,
          nav_icon: "category_icon",
        },
        {
          small_arrow: false,
          nav_item: "Tra cứu",
          nav_selected: false,
          nav_icon: "search_icon",
        },
        {
          small_arrow: false,
          nav_item: "Hệ thống",
          nav_selected: false,
          nav_icon: "system_icon",
        },
        {
          small_arrow: false,
          nav_item: "Báo cáo",
          nav_selected: false,
          nav_icon: "report_icon",
        },
      ],
    };
  },
  methods: {
    hightline_navitem: function (selected_item) {
      for (var i = 0; i < this.nav.length; i++) {
        this.nav[i].nav_selected = false;
      }
      this.nav[selected_item].nav_selected = true;
    },
    handleClick: function(){
        this.$emit('nav_collapse_change');
    },
    
  },
};
</script>

<style>
.navbar {
  width: 220px;
  height: 100vh;
  background-color: #1e235a;
}
/* logo box */
.logo_box {
  padding-left: 24px;
  margin: 0px;
  line-height: 60px;
  height: 60px;
  background-color: #1e235a;
  display: flex;
  align-items: center;
}
.icon {
  width: 30px;
  height: 30px;
  background-image: url("~@/assets/icon/logo-qlts.svg");
  background-position: center;
  background-size: contain;
}
.title {
  color: #fff;
  font-weight: bold;
  font-size: 24px;
  margin-left: 4px;
  margin-right: 24px;
}
.toogle {
  width: 20px;
  height: 20px;
  background-image: url("~@/assets/icon/hamburger-menu.svg");
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
  cursor: pointer;
}
/*end logo box */

/* nav box */
.nav_box {
  margin: 0px;
  width: 100%;
  height: calc(100vh - 60px);
}
/* nav - item */
.nav_item {
  height: 44px;
  display: flex;
  align-items: center;
  padding-left: 24px;
  position: relative;
  cursor: pointer;
}
.nav_item:hover {
  background-color: #2b3173;
}
.nav_item .highline {
  position: absolute;
  left: 0px;
  top: 0px;
  width: 4px;
  height: 100%;
  background: #00abfe;
  z-index: 10;
}

.nav_item_icon {
  width: 24px;
  height: 24px;
  margin: 0px;
  padding: 0px;
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
}
/* icon image  */
.overview_icon {
  background-image: url("~@/assets/icon/computer-line.svg");
}
.asset_icon {
  background-image: url("~@/assets/icon/community-line.svg");
}
.tool_icon {
  background-image: url("~@/assets/icon/paint-brush-line.svg");
}
.category_icon {
  background-image: url("~@/assets/icon/common.svg");
}
.search_icon {
  background-image: url("~@/assets/icon/search-eye-line.svg");
}
.system_icon {
  background-image: url("~@/assets/icon/settings.svg");
}
.report_icon {
  background-image: url("~@/assets/icon/pie-chart-line.svg");
}
/* end icon image */
.nav_item_content {
  color: #fff;
  font-size: 13px;
  padding-left: 8px;
}
.item_selected {
  background-color: #2b3173;
}
.small_arrow {
  background-image: url("~@/assets/icon/i_arrow_up_small.svg");
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
  width: 8px;
  height: 8px;
  transform: rotate(-90deg);
  position: absolute;
  z-index: 12;
  right: 24px;
}
/* sub menu */
.sub_menu {
  position: absolute;
  left: 220px;
  top: 0px;
  width: 150px;
  text-align: left;
  z-index: 12;
  box-shadow: 2px 2px 6px #ebebeb;
  background-color: #FFF;
}
.sub_menu_item {
  padding-left: 24px;
  line-height: 36px;
  font-size: 13px;
}
/* end sub menu */
/* nav - item */
/* end nav box */
/*  */
</style>