<template>
  <PageWrapper title="懒加载基础示例" content="向下滚动到可见区域才会加载组件">
    <div class="lazy-base-demo-wrap">
      <h1>向下滚动</h1>

      <div class="lazy-base-demo-box">
        <LazyContainer>
          <TargetContent />
          <template #skeleton>
            <Skeleton :rows="10" />
          </template>
        </LazyContainer>
      </div>
    </div>
  </PageWrapper>
</template>
<script lang="ts">
  import { defineComponent } from 'vue';
  import { Skeleton } from 'ant-design-vue';
  import TargetContent from './TargetContent.vue';
  import { LazyContainer } from '/@/components/Container/index';
  import { PageWrapper } from '/@/components/Page';

  export default defineComponent({
    components: { LazyContainer, PageWrapper, TargetContent, Skeleton },
  });
</script>
<style lang="less">
  .lazy-base-demo {
    &-wrap {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      width: 50%;
      height: 2000px;
      margin: 20px auto;
      background-color: @component-background;
      text-align: center;
    }

    &-box {
      width: 300px;
      height: 300px;
    }

    h1 {
      height: 1300px;
      margin: 20px 0;
    }
  }
</style>
