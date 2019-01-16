<template>
  <div>
    <div id="show-viewport">
      <div class="one">
        <el-button @click="showExcelPreview">预览excel文件</el-button>
      </div>
      <div class="two">
        <el-button @click="showWordPreview">预览word文件</el-button>
      </div>
      <div class="three">
        <el-button @click="showPptPreview">预览ppt文件</el-button>
      </div>
      <div class="four">
        <el-button @click="showPdfPreview">预览pdf文件</el-button>
      </div>
    </div>
    <PreviewDocument :visible="isShowDialog" :previewUrl="url" @close="closeDialog"></PreviewDocument>
  </div>
</template>
<script>
import PreviewDocument from '@/components/previewDocument'
export default {
  name: 'viewPort',
  components: {
    PreviewDocument
  },
  data () {
    return {
      isShowDialog: false,
      url: 'https://view.officeapps.live.com/op/view.aspx?src=http://storage.xuetangx.com/public_assets/xuetangx/PDF/1.xls'
    }
  },
  methods: {
    showExcelPreview () {
      this.isShowDialog = true
      this.url = 'https://view.officeapps.live.com/op/view.aspx?src=http://storage.xuetangx.com/public_assets/xuetangx/PDF/1.xls'
    },
    showWordPreview () {
      this.isShowDialog = true
      this.url = 'http://view.officeapps.live.com/op/view.aspx?src=newteach.pbworks.com%2Ff%2Fele%2Bnewsletter.docx'
    },
    showPptPreview () {
      this.isShowDialog = true
      this.url = 'http://view.officeapps.live.com/op/view.aspx?src=http%3a%2f%2fvideo.ch9.ms%2fbuild%2f2011%2fslides%2fTOOL-532T_Sutter.pptx'
    },
    showPdfPreview () {
      this.isShowDialog = true
      // 必须为.pdf的文件才能下载
      this.url = 'http://storage.xuetangx.com/public_assets/xuetangx/PDF/PlayerAPI_v1.0.6.pdf'
    },
    closeDialog () {
      this.isShowDialog = false
    }
  }
}
</script>
<style>
  #show-viewport{
    width: 100%;
  }
  #show-viewport div{
    float: left;
    width: 4rem;
    height: 200px;
    text-align: center;
  }
  .one{
    background-color: burlywood;
  }
  .two{
    background-color: lightcoral;
  }
  .three{
    background-color: paleturquoise;
  }
  .four{
    background-color: goldenrod;
  }
  .el-dialog__header{
    height: .2rem;
    line-height: .2rem;
  }
</style>
