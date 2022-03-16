<template>
  <div class="AppMain">
    <el-table :data="tableData" style="width: 100%">
      <el-table-column
        v-for="item in columns"
        :key="item.prop"
        :prop="item.prop"
        :label="item.label"
        :width="item.width"
      />
      <template #state="{ row }">
        <t-tag v-if="row.state === 1" theme="danger" variant="light"
          >审核失败</t-tag
        >
        <t-tag v-if="row.state === 2" theme="warning" variant="light"
          >待审核</t-tag
        >
        <t-tag v-if="row.state === 3" theme="success" variant="light"
          >已完成</t-tag
        >
      </template>
    </el-table>
  </div>
</template>

<script>
export default {
  name: "AppMain",
  data() {
    return {
      columns: [
        {
          prop: "date",
          label: "日期",
          width: "180",
        },
        {
          prop: "name",
          label: "姓名",
          width: "180",
        },
        {
          prop: "state",
          label: "状态",
          width: "180",
        },
        {
          prop: "address",
          label: "地址",
        },
      ],
      tableData: [
        {
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄",
          state: 1,
        },
        {
          date: "2016-05-04",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1517 弄",
          state: 2,
        },
        {
          date: "2016-05-01",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1519 弄",
          state: 3,
        },
        {
          date: "2016-05-03",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1516 弄",
          state: 1,
        },
      ],
    };
  },
};
</script>
