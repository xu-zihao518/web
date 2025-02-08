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
            items: ['关注', '发现', '深圳']
        };
    },
    methods: {
        getLink(item) {
            if (item === '关注') {
                return '/follow';
            }
            return '#';
        }
    }
};
</script>

<style scoped>
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
    padding: 10px 60px;
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