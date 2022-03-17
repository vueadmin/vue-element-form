<template>
  <el-form ref="form" :model="form" label-width="80px">
    <el-form-item
      v-for="items in formItems"
      :key="items.prop"
      :label="items.label"
    >
      <component
        v-model="form[items.prop]"
        :type="items.type"
        :is="componentList[items.component]"
        :placeholder="items.placeholder"
        @input="handleInput(items.methods.input, $event, items)"
        @change="handleChange(items.methods.change, $event, items)"
      >
        <el-option
          v-for="option in items.option"
          :key="option.value"
          :label="option.label"
          :value="option.value"
        />
      </component>
    </el-form-item>
    <el-form-item>
      <el-button type="primary" @click="onSubmit">立即创建</el-button>
      <el-button>取消</el-button>
    </el-form-item>
  </el-form>
</template>

<script>
export default {
  name: "VueForm",
  props: {
    formItems: Array,
  },
  data() {
    return {
      unique: "select",
      form: {
        region: "shanghai",
      },
      componentList: {
        input: "el-input",
        switch: "el-switch",
        select: "el-select",
      },
    };
  },
  methods: {
    handleInput(v, e, items) {
      if (v !== undefined) {
        this.$emit(v, e, items);
      }
    },
    handleChange(v, e, items) {
      if (v !== undefined) {
        this.$emit(v, e, items);
      }
    },
    onSubmit() {
      console.log(this.form);
    },
  },
};
</script>
