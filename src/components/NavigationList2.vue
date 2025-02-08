<template>
    <div>
        <ul class="common-list">
            <li v-for="(item, index) in items" :key="index" class="common-list-item"><a :href="getLink(item)" class="common-list-link">{{ item }}</a></li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            items: ['搞笑', '游戏', '穿搭', 'Vlog', '科技数码', '运动健身']
        };
    },
    methods: {
        getLink(item) {
            // 根据item返回相应链接，这里只是示例
            if (item === '搞笑') {
                return '/funny';
            }
            return '#';
        }
    }
};
</script>

<style scoped>
/* 可以覆盖或添加特定样式 */
.common-list {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
}

.common-list-item {
    /* 灰色 */
    color: #f5f5f5;
    align-items: center;
    margin: 20px;
    border-bottom: 1px solid #ccc;
}

.common-list-link {
    
    color:#808080;
    text-decoration: none;
}

.common-list-link:hover {
    color: #000000;
}
</style>