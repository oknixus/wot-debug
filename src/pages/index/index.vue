<!-- 使用 type="home" 属性设置首页，其他页面不需要设置，默认为page；推荐使用json5，更强大，且允许注释 -->
<route lang="json5" type="home">
{
style: {
navigationStyle: 'custom',
navigationBarTitleText: '首页',
},
}
</route>
<template>
  <view
    class="bg-white overflow-hidden pt-2 px-4"
    :style="{ marginTop: safeAreaInsets?.top + 'px' }"
  >
    <view class="mt-12">
      <image src="/static/logo.svg" alt="" class="w-28 h-28 block mx-auto" />
    </view>
    <view>
      <wd-checkbox-group v-model="author" shape="button">
        <wd-checkbox
          :modelValue="'菲鸽'"
          custom-label-class="b-1 b-solid b-pink bg-pink rounded-0"
          value="菲鸽"
        >
          菲鸽
        </wd-checkbox>
        <wd-checkbox value="小黑" :modelValue="'小黑'">小黑</wd-checkbox>
      </wd-checkbox-group>
    </view>
  </view>
</template>

<script lang="ts" setup>
defineOptions({ name: "Home" });

// 获取屏幕边界到安全区域距离
const { safeAreaInsets } = uni.getSystemInfoSync();
const author = ref([]);
// 测试 uni API 自动引入
onLoad(() => {
  console.log(author);
});
</script>

<style>
.main-title-color {
  color: #d14328;
}
</style>
