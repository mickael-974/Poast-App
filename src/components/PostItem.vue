<template>
    <div class="post">
        <div class="post-stats">
            <img src="@/assets/like_button.png" alt="" class="post-btn">
            <span> {{ postInfos.nb_likes }} </span>
        </div>
        <div class="post-body">
            <span class="post-header"> {{ postInfos.date }} by {{ username }} </span>
            <span class="post-content"> {{ postInfos.content }} </span>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'MyPosts',
        props: {
            postInfos: {
                type: Object,
                default: {}
            },
            username: {
                type: String,
                default:''
            },
        },
    }
</script>

<style lang="scss" scoped>
.post {
    width: 400px;
    height: 125px;
    border: 3px solid #45AAF2;
    border-radius: 7px;
    display: flex;
    font-family: 'Open Sans', sans-serif;
}
.post-stats {
    width: 25px;
    padding-top: 5px;
    background-color: #45AAF2;
    color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.post-body {
    width: 300px;
    padding: 5px;
    display: flex;
    flex-direction: column;
    .post-header {
        font-weight: 700;
        text-decoration: underline;
    }
}
</style>