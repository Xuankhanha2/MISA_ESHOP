<template>
  <div class="navbar_collapse">
    <!-- phần logo box  -->
    <div class="logo_box_collapse">
      <div class="icon_collapse" @click="handleClick(false)"></div>
    </div>
    <!-- end phần logo box -->
    <div class="nav_box_collapse">
      <div
        class="nav_item_collapse"
        v-for="(item, index) in nav"
        :key="index" 
        @click="hightline_navitem(index, item.nav_selected)"
        :class="{ item_selected: item.nav_selected }"
        ref="nav_item"
      >
        <div class="highline" v-show="item.nav_selected"></div>
        <div class="nav_item_icon" :class="item.nav_icon"></div>
        <div class="small_arrow_collapse" v-if="item.small_arrow"></div>
        <div class="sub_menu_collapse" v-show="item.nav_selected">
          <div
            class="sub_menu_item_collapse"
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
      collapse_menu: false,
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
    hightline_navitem: function (selected_item, check) {
      for (var i = 0; i < this.nav.length; i++) {
        this.nav[i].nav_selected = false;
      }
      if (!check) this.nav[selected_item].nav_selected = true;
      else this.nav[selected_item].nav_selected = false;
    },
    handleClick: function () {
      this.$emit("nav_collapse_change");
    }
  },
};
</script>

<style>
.navbar_collapse {
  width: auto;
  height: 100vh;
  background-color: #1e235a;
}
/* logo box */
.logo_box_collapse {
  padding-left: 16px;
  padding-right: 16px;
  margin: 0px;
  line-height: 60px;
  height: 60px;
  background-color: #1e235a;
  display: flex;
  align-items: center;
}
.icon_collapse {
  width: 30px;
  height: 30px;
  background-image: url("~@/assets/icon/logo-qlts.svg");
  background-position: center;
  background-size: contain;
  cursor: pointer;
}
/*end logo box */

/* nav box */
.nav_box_collapse {
  margin: 0px;
  width: 100%;
  height: calc(100vh - 60px);
}
/* nav - item */
.nav_item_collapse {
  height: 44px;
  display: flex;
  align-items: center;
  display: flex;
  justify-content: space-around;
  position: relative;
  cursor: pointer;
  padding: 0px;
}
.nav_item_collapse:hover {
  background-color: #2b3173;
}
.nav_item_collapse .highline {
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
.item_selected {
  background-color: #2b3173;
}
.small_arrow_collapse {
  background-image: url("~@/assets/icon/i_arrow_up_small.svg");
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
  width: 8px;
  height: 8px;
  transform: rotate(-45deg);
  position: absolute;
  z-index: 12;
  bottom: 0px;
  right: 0px;
}
/* sub menu */
.sub_menu_collapse {
  position: absolute;
  left: 62px;
  top: 0px;
  width: 150px;
  text-align: left;
  z-index: 12;
  box-shadow: 2px 2px 6px #ebebeb;
  background-color: #FFF;
}
.sub_menu_item_collapse {
  padding-left: 24px;
  line-height: 36px;
  font-size: 13px;
}
/* end sub menu */
/* nav - item */
/* end nav box */
/*  */
</style>