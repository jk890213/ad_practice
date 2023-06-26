<template>
    <nav class="mobile_nav">
        <ul>
            <li v-for="{ title, linkUrl } in links">
                <a :href="linkUrl" target="_blank"> {{ title }} </a>
            </li>
        </ul>
    </nav>
</template>

<script setup lang="ts">
const links = [{
    title: '地圖導航',
    linkUrl: 'https://bit.ly/3PC5EGa'
}, {
    title: '撥打電話',
    linkUrl: 'tel:+886-2-25674588'
}, {
    title: 'Facebook',
    linkUrl: 'https://bit.ly/3oBWSMA'
}, {
    title: 'Line@',
    linkUrl: "https://lin.ee/B9sG5h7"
},]
</script>

<style lang="scss" scoped>
.mobile_nav {
    height: 60px;
    width: 100%;
    position: fixed;
    bottom: 0;
    z-index: 100;

    @include desktops {
        display: none;
    }

    ul {
        height: 100%;
        display: flex;

        li {
            flex-grow: 1;
            background-color: #325e46;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;

            a {
                color: #fff;
                text-decoration: none;
            }
        }

        li+li {
            border-left: 1px solid #fff;
        }
    }
}
</style>