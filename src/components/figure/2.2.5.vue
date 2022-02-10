<template>
    <div class="demo-image__preview" >
        <div v-for="url in urls" :key="url" >
          <span style="float: left;">
            <el-image  :src="url" lazy :preview-src-list="srcList" style="width: 100px; height: 100px">
            </el-image>
          </span>
        </div>
        <div>
            <el-image-viewer v-if="showViewer" :initial-index="1" :on-close="onClose" :on-switch="onSwitch" :url-list="srcList"/>
        </div>
    </div>
</template>

<script lang="ts">
  import { defineComponent, ref } from 'vue'

  export default defineComponent({
    setup() {
      const urls = ref([
        require('../../assets/png/2.2.5.1.png'),
        require('../../assets/png/2.2.5.2.png'),
        require('../../assets/png/2.2.5.3.png'),
        require('../../assets/png/2.2.5.4.png'),
      ])
      const srcList = ref([
        require('../../assets/png/2.2.5.1.png'),
        require('../../assets/png/2.2.5.2.png'),
        require('../../assets/png/2.2.5.3.png'),
        require('../../assets/png/2.2.5.4.png'),
      ])
      const onClose = () =>{
        this.showViewer = false
      }
      const onSwitch = () =>{

      }

      return {
        showViewer: false,
        urls,
        srcList,
        onClose,
        onSwitch,
      }
    },
    /*methods: {
      // 关闭图片预览
      onClose() {
        this.showViewer = false
      },
      // 切换图片 index为图片下标值
      onSwitch(index) {
        console.log(index)
      }
    }*/
  })
</script>
<style scoped lang="scss">
    .demo-image__preview {
        /*text-align: center;*/
        /*height: 400px;
        overflow-y: auto;

        .el-image {
            display: block;
            min-height: 200px;
            margin-bottom: 10px;

            &:last-child {
                margin-bottom: 0;
            }
        }*/
    }
</style>
