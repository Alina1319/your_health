<template>
    <body>
    <div class="nav">
        <input type="checkbox">
        <img :src="require('/Users/alina/code/health/public/assets/images/website-icon.png').default" alt="" class="" >
        <div class="menu">
            <li class="ms-4"><a href="#">placeholder</a></li>
            <li><a href="#">placeholder</a></li>
            <li><a href="#">placeholder</a></li>
            <li><a href="#">placeholder</a></li>
        </div>
    </div>
    </body>
</template>

<script>
export default {
    name: "navigation",
}
</script>

<style scoped lang="scss">

body {
    margin: 0;
    padding: 0;
    min-height: 100px;
    font-family: 'Open Sans', Verdana, Geneva, Tahoma, sans-serif;
}

body, .nav, .menu {
    display: flex;
    justify-content: start;
    align-items: center;
    background: transparent;
}

.nav {
    position: relative;
    z-index: 20;
    background-color: #fff;
    padding: 20px;
    margin-left: 31px;
    transition: 0.5s;
    border-radius: 50px;
    overflow: hidden;
    box-shadow: 0 8px 15px rgba(0,0,0,.2);
}

.menu {
    margin: 0;
    padding: 0;
    width: 0;
    overflow: hidden;
    transition: 0.5s;
}

.nav input:checked ~ .menu {
    width: 450px;
}

.menu li {
    list-style: none;
    margin: 0 10px;
}

.menu li a {
    text-decoration: none;
    color: #666;
    font-weight: 400;
    transition: 0.5s;
}

.menu li a:hover {
    color: #161919;
}

.nav input {
    width: 40px;
    height: 40px;
    cursor: pointer;
    opacity: 0;
    margin-left: 5px;
}

.nav img{
    position: absolute;
    left: 12px;
    width: 63px;
    height: 60px;
    border-radius: 50px;
    //background-color: #666;
    pointer-events: none;
    transition: 0.5s;
}

</style>
