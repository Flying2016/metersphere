<template>
  <el-form :model="editData" label-position="right" label-width="80px" size="small" ref="form">
    <el-form-item :label="$t('api_test.variable_name')" prop="name">
      <el-input v-model="editData.name" :placeholder="$t('api_test.variable_name')" ref="nameInput"></el-input>
    </el-form-item>

    <el-form-item :label="$t('commons.description')" prop="description">
      <el-input class="ms-http-textarea"
                v-model="editData.description"
                type="textarea"
                :autosize="{ minRows: 2, maxRows: 10}"
                :rows="2" size="small"/>
    </el-form-item>

    <el-form-item :label="$t('api_test.value')" prop="value">
      <el-input v-model="editData.value" :placeholder="$t('api_test.value')"></el-input>
    </el-form-item>
  </el-form>
</template>

<script>
  export default {
    name: "MsEditConstant",
    components: {},
    props: {
      editData: {},
    },
    created() {
      this.$nextTick(() => {
        this.$refs.nameInput.focus();
      });
    },
    watch: {
      editData() {
        this.$refs.nameInput.focus();
      }
    }
  }
</script>

<style scoped>

</style>
