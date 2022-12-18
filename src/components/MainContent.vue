<script setup>
import Class from './Class.vue';
const toolsColl = [
    {
        name: '软件资源',
        content: [
            ["jetbrains破解无限期激活码", "https://3.jetbra.in"],
            ["MSDN(获取windows镜像)", "https://msdn.itellyou.cn/"],
            ["PPT导航网站", "http://www.hippter.com/"],
            ["谷歌插件网(墙内)", "http://chromecj.com/"],
            ["异次元软件推荐", "https://www.iplaysoft.com/"],
            
        ]
    },
    {
        name: '设计工具',
        content: [
            ["设计导航", "https://hao.uisdc.com/"]
        ]
    },
    {
        name: '奇妙网站',
        content: [
            ["pixiv墙内特供", "https://pixivic.com/"],
            ["在线办公", "https://uzer.me/"],
            ["格式转换大全", "https://cn.office-converter.com"],
            ["临时邮箱", "http://24mail.chacuo.net/"],
            ["BigJPG--图片放大", "https://bigjpg.com/"],
            ["奇趣网站收藏家", "https://fuun.fun/"],

        ]
    },
    {
        name: '影视资源',
        content: [
            ["pilipili--美剧动漫", "https://pilipali.cc/"],
            ["全球电视直播", "http://bddn.cn/zb.htm"],
        ]
    },
    {
        name: '优质博客',
        content: [
            ["刘明野的博客", "https://www.liumingye.cn/"]
        ]
    }
]
</script>

<template>
    <div id="container">
        <Class v-for="col in toolsColl" :name="col.name" :content="col.content"></Class>
    </div>

</template>

<style scoped>
#container {
    padding: 3em 6em 1.5em;
    height: 100vh;
    display: flex;
    flex-wrap: nowrap;
    align-items: center;
    overflow-y: auto;
}

#container>*+* {
    margin-left: 3em;
}
</style>
