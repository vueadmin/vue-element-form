<template>
  <div class="home">
    <VueForm
      :formItems="formItems"
      @handleInput="handleInput"
      @handleChange="handleChange"
    />
  </div>
</template>

<script>
import VueForm from "@/components/VueForm.vue";

export default {
  name: "Home",
  components: {
    VueForm,
  },
  data() {
    return {
      formItems: [
        {
          component: "input",
          prop: "name",
          label: "姓名",
          placeholder: "11",
          methods: {
            input: "handleInput",
            change: "handleChange",
          },
        },
        {
          component: "input",
          prop: "age1",
          label: "年龄",
          placeholder: "22",
          methods: {
            input: "handleInput",
            change: "handleChange",
          },
        },
        {
          component: "switch",
          prop: "age",
          label: "已就业",
          placeholder: "33",
          methods: {},
        },
        {
          component: "input",
          type: "textarea",
          prop: "desc",
          label: "备注",
          placeholder: "44",
          methods: {},
        },
        {
          component: "select",
          prop: "region",
          label: "选择",
          placeholder: "55",
          methods: {},
          option: [
            {
              label: "区域一",
              value: "shanghai",
            },
            {
              label: "区域二",
              value: "beijing",
            },
          ],
        },
      ],
    };
  },
  methods: {
    handleInput(v, items) {
      console.log("handleInput ===> ", v, items);
    },
    handleChange(v, items) {
      console.log("handleChange ===> ", v, items);
    },
  },
};
</script>
<style scoped>
.home {
  width: 50vw;
  margin: 20px auto;
}
</style>
