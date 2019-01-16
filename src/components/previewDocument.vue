<template>
  <div>
    <el-dialog
      title="预览文件"
      :visible.sync="visible"
      width="900px"
      :before-close="closeDialog"
      >
      <iframe v-if="isShow" :src="previewUrl" width='100%' height='600px' frameborder='1'></iframe>
      <span slot="footer" class="dialog-footer">
        <!-- <el-button @click="visible = false">取 消</el-button>
        <el-button type="primary" @click="visible = false">确 定</el-button> -->
      </span>
    </el-dialog>
    <iframe src="" frameborder="0"></iframe>
  </div>
</template>
<script>
export default {
  name: 'preview-document',
  props: {
    visible: { // 是否显示弹窗
      type: Boolean
    },
    previewUrl: { // 预览的地址
      type: String
    }
  },
  data () {
    return {
      isShow: true
    }
  },
  methods: {
    closeDialog () {
      this.$emit('close')
    }
  }
}
</script>
