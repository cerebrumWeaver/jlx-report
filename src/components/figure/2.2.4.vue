<template>
    <div class="demo-image__preview">
        <el-image
                :src="url"
                :preview-src-list="srcList"
                fit="scale-down"
        >
        </el-image>
    </div>
</template>

<script lang="ts">
  import { defineComponent, ref } from 'vue'

  export default defineComponent({
    setup() {
      const url = ref(
        require('../../assets/png/2.2.4.png'),
      )
      const srcList = ref([
        require('../../assets/png/2.2.4.png'),
      ])

      return {
        url,
        srcList,
      }
    },
  })
</script>
<style scoped lang="scss">
    .demo-image__preview {
        text-align: center;
    }
</style>
