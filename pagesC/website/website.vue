<template>
    <view class="app-page">
        <web-view :src="webUrl"></web-view>
    </view>
</template>

<script>
export default {
    data() {
        return {
            title: '',
            webUrl: ''
        };
    },
    onLoad(e) {
        const {title, url} = JSON.parse(e.data);
        this.webUrl = decodeURIComponent(url);
		console.log("webUrl" + this.webUrl)
        if (title) {
            this.fnSetPageTitle(title);
        }
    }
};
</script>

<style scoped>
.app-page {
    width: 100vw;
}
</style>
