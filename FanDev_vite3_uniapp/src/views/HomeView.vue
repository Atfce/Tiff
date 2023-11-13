<script setup lang="ts">
</script>

<template>
  <view class="container">
    <text class="title">仓储系统首页</text>

    <!-- 显示产品列表 -->
    <view class="product-list">
      <view v-for="(product, index) in productList" :key="index" class="product-item">
        <text class="product-name">{{ product.name }}</text>
        <text class="product-quantity">{{ product.quantity }}件</text>
      </view>
    </view>

    <!-- 显示库存状态 -->
    <view class="inventory-status">
      <text class="status-title">库存状态</text>
      <view class="status-texts">
        <text class="status-text">总库存：{{ totalInventory }}件</text>
        <text class="status-text">已用库存：{{ usedInventory }}件</text>
        <text class="status-text">剩余库存：{{ remainingInventory }}件</text>
      </view>
    </view>

    <!-- 显示最近的操作记录 -->
    <view class="operation-log">
      <text class="log-title">最近的操作记录</text>
      <view v-for="(log, index) in operationLogs" :key="index" class="log-item">
        <text class="log-time">{{ log.time }}</text>
        <text class="log-action">{{ log.action }}</text>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      productList: [
        { name: '商品1', quantity: 100 },
        { name: '商品2', quantity: 150 },
        { name: '商品2', quantity: 150 },
        { name: '商品2', quantity: 150 },
        { name: '商品2', quantity: 150 },
        { name: '商品2', quantity: 150 },
        // 添加更多产品...

      ],
      totalInventory: 250,
      usedInventory: 200,
      remainingInventory: 50,
      operationLogs: [
        { time: '2023-01-01 10:00', action: '入库商品1，数量：50件' },
        { time: '2023-01-02 14:30', action: '出库商品2，数量：20件' },
        // 添加更多操作记录...
      ],
    };
  },
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  
  padding: 20px;
  height: 100vh;
  width: 100%;
  background-color: #fff;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  
}

.title {
  font-size: 28px;
  font-weight: bold;
  margin-bottom: 20px;
}

.product-list {
  margin-bottom: 20px;
  display: flex;
  width: 400px;
  height: auto;
  flex-wrap: wrap;
}

.product-item {
  /* 让子盒子超出父盒子范围则向下移动 */
  flex-shrink: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  border: 1px solid #ddd;
  padding: 15px;
  margin-bottom: 15px;
  height: 200px;
  width: 200px;
  border-radius: 5px;
  background-color: #f9f9f9;
}

.product-name {
  font-size: 20px;
  font-weight: bold;
  color: #333;
}

.product-quantity {
  font-size: 16px;
  color: #777;
}

.inventory-status {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
  border-top: 2px solid #333;
  border-bottom: 2px solid #333;
  padding: 15px 0;
}

.status-texts {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.status-title {
  box-sizing: border-box;
  font-size: 24px;
  font-weight: bold;
  color: #333;
  margin-bottom: 10px;
  padding-right: 20px;
}

.status-text {
  font-size: 18px;
  margin-bottom: 8px;
  color: #555;
}

.operation-log {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
}

.log-title {
  font-size: 24px;
  font-weight: bold;
  color: #333;
  margin-bottom: 10px;
  margin-right: 10px;
}

.log-item {
  font-size: 18px;
  margin-bottom: 8px;

}

.log-time {
  color: #888;
  margin-right: 10px;
}

.log-action {
  color: #333;
  margin-right: 10px;
}
</style>