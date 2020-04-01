<template>
  <el-form ref="postForm" :model="postForm">
    <stickey :class-name="'sub-navbar'">
      <el-button v-if="!isEdit" @click="showGuide">显示帮助</el-button>
      <el-button
        v-loading="loading"
        type="success"
        style="margin-left: 10px"
        @click="submitForm"
      >
        {{ isEdit ? '编辑电子书' : '新增电子书' }}
      </el-button>
    </stickey>
    <div class="detail-container">
      <el-row>
        <warning />
        <el-col :span="24">
          <!-- 表单控件的具体样式 -->
        </el-col>
      </el-row>
    </div>
    <div />
  </el-form>
</template>

<script>
import Stickey from '@/components/Sticky'
import Warning from './Warning'
export default {
  components: {
    Stickey,
    Warning
  },
  props: {
    isEdit: Boolean
  },
  data() {
    return {
      loading: false,
      postForm: {
        status: ''
      }
    }
  },
  methods: {
    submitForm() {
      this.loading = true
    },
    showGuide() {
    }
  }
}
</script>

<style lang="scss" scoped>
  .detail-container {
    padding: 40px 50px 20px;
  }
</style>
