<script lang="ts" setup>
import { ref, h } from "vue";
import { NDataTable } from "naive-ui";
import { TableColumns } from "naive-ui/lib/data-table/src/interface";

const columns = ref<TableColumns>([
  {
    type: "selection",
    fixed: "left",
  },
  {
    title: "Name",
    key: "name",
    width: 200,
    fixed: "left",
  },
  {
    title: "Age",
    key: "age",
    width: 300,
    fixed: "left",
    render: () =>
      h("img", {
        src: "https://pic1.zhimg.com/v2-ac10615816634de22ca8404670ec24f6_1440w.jpg?source=172ae18b",
        style: {
          width: "200px",
        },
      }),
  },
  {
    title: "Row",
    key: "row",
    render(row, index) {
      return h("span", ["row ", index]);
    },
    width: 200,
  },
  {
    title: "Row1",
    key: "row1",
    render(row, index) {
      return h("span", ["row ", index]);
    },
    width: 200,
  },
  {
    title: "Row2",
    key: "row2",
    render(row, index) {
      return h("span", ["row ", index]);
    },
    width: 100,
  },
  {
    title: "Address",
    key: "address",
    width: 200,
  },
  {
    title: "Row1",
    key: "row1",
    render(row, index) {
      return h("span", ["row ", index]);
    },
    width: 200,
  },
  {
    title: "Row2",
    key: "row2",
    render(row, index) {
      return h("span", ["row ", index]);
    },
    width: 100,
  },
  {
    title: "Address",
    key: "address",
    width: 200,
  },
  {
    title: "Row1",
    key: "row1",
    render(row, index) {
      return h("span", ["row ", index]);
    },
    width: 200,
  },
  {
    title: "Row2",
    key: "row2",
    render(row, index) {
      return h("span", ["row ", index]);
    },
    width: 100,
  },
  {
    title: "Address",
    key: "address",
    width: 200,
  },
  {
    title: "Row1",
    key: "row1",
    render(row, index) {
      return h("span", ["row ", index]);
    },
    width: 200,
  },
  {
    title: "Row2",
    key: "row2",
    render(row, index) {
      return h("span", ["row ", index]);
    },
    width: 100,
  },
  {
    title: "Address",
    key: "address",
    width: 200,
  },
]);

const data = Array.apply(null, new Array(5000)).map((_, index) => ({
  key: index,
  name: `Edward King ${index}`,
  age: 32,
  address: `London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}London, Park Lane no. ${index}`,
}));
const refresh = ref(Date.now());
</script>

<template>
  <div class="home">
    <h1>
      在macos系统下(目前测试的浏览器为safari、chrome)，鼠标快速滚动时会出现新展示的数据出现空白的情况（可以通过上下反复滚动来复现bug）。
      该Bug在Windows上没有复现
    </h1>

    <div class="description">
      <p>系统版本：MacOS Monterey(12.1)</p>
      <p>测试使用的浏览器：Chrome、Safari</p>
      <p>组件：Data Table</p>
      <p>可以复现bug的props：virtual-scroll</p>
    </div>

    <n-data-table
      ref="table"
      :columns="columns"
      :data="data"
      :max-height="600"
      virtual-scroll
      :key="refresh"
    />
  </div>
</template>

<style lang="scss">
.description {
  background-color: #efefef;
  border-radius: 4px;
  padding: 10px 24px;
  margin-bottom: 20px;
}
</style>
