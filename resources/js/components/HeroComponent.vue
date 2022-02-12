<template>
<div class="main">
    <nav class="d-flex nav-logo">
        <navigation></navigation>
        <div class="slogan">Your Health</div>
    </nav>
    <ul class="navigation-options d-flex">
        <li>Forms</li>
        <li>Doctors</li>
    </ul>

<div class="main-hero-content row d-flex justify-content-center">
    <div class="hero-heading col-6">
        <h1>To cure diseases<br>
            we need communication</h1>
        <p><span>Good news:</span> The data is out there</p>
        <p><span>Bad news:</span> It is inaccessible & unusable</p>
    </div>
        <div class="hero-imgs col-6 d-flex">
            <div>
                <img :src="require('/Users/alina/code/health/public/assets/images/1.png').default" alt="" class="" >
            </div>
            <div>
                <img :src="require('/Users/alina/code/health/public/assets/images/2.png').default" alt="" class="" >
            </div>
            <div>
                <img :src="require('/Users/alina/code/health/public/assets/images/3.svg').default" alt="" class="" >
            </div>
            <div>
                <img :src="require('/Users/alina/code/health/public/assets/images/4.png').default" alt="" class="" >
            </div>
        </div>
</div>


</div>
</template>

<script>
import Navigation from "./nav-components/Navigation";
export default {
    name: "HeroComponent",
    components: {Navigation}
}
</script>

<style scoped lang="scss">
$breakpoint-tablet: 768px;

.main {
    width: 100%;
    height: 100vh;
    background:linear-gradient(132deg, rgba(179, 219, 255, 1) 8%, rgba(217, 210, 254, 1) 30%, rgba(255, 255, 255, 1) 55%);
    overflow: hidden;

    .nav-logo {
        justify-items: center;
        align-items: center;
        padding-top: 15px;

        .slogan {
            font-size: 29px;
            margin-left: 130px;
            position: absolute;
            color: #38447f;
        }
    }

    .navigation-options {
        position: absolute;
        width: 230px;
        justify-content: space-around;
        right: 40px;
        top: 35px;
        color: #38447f;
        font-size: 1.2rem;
        list-style: none;
        li {
            cursor: pointer;
            display: inline-block;
            position: relative;
            &:after {
                content: '';
                position: absolute;
                width: 100%;
                transform: scaleX(0);
                height: 2px;
                bottom: 0;
                left: 0;
                background-color: #38447f;
                transform-origin: bottom right;
                transition: transform 0.25s ease-out;
            }
            &:hover:after {
                transform: scaleX(1);
                transform-origin: bottom left;
            }
        }
    }

.main-hero-content {
    .hero-heading {
        margin-top: 100px;

        h1 {
            color: #3b4483;
            font-family: "Poppins", Sans-serif;
            font-size: 4rem;
            font-weight: 400;
        }

        p {
            font-size: 1.6rem;
            color: #3b4483;
            font-weight: 400;
        }

        p:first-of-type  {
            margin-top: 40px;
            span {
                color: #149178;
                font-weight: 800;
            }
        }

        p:nth-child(3) {
            span {
                color: #ab4848;
                font-weight: 800;
            }
        }
    }

      .hero-imgs {
        max-width: 580px;
        justify-content: space-evenly;

        div {
            border-radius: 20px;
            transition: 0.4s;
            height: 350px;
            width: 125px;
            overflow: hidden;
        }

        div:nth-of-type(1) {
            background-color: #fdc37a;
            margin-top: 85px;
            img {
                margin-top: 45px;
                width: auto;
                height: 211px;
                margin-left: 20px;
            }
            &:hover {
                margin-top: 20px;
            }
        }

        div:nth-of-type(2) {
            background-color: #f082d3;
            margin-top: 25px;
            img {
                width: 141%;
                height: 55%;
                margin-top: 20px;
            }
            &:hover {
                margin-top: -2px;
            }
        }

        div:nth-of-type(3) {
            background-color: #f3f3f3;
            margin-top: 80px;
            img {
                width: 141%;
                height: 55%;
                margin-top: 20px;
            }
            &:hover {
                margin-top: 20px;
            }
        }

        div:nth-of-type(4) {
            background-color: #99d9f1;
            height: 350px;
            width: 140px;
            margin-top: 160px;
            img {
                margin-top: 75px;
                width: auto;
                height: 211px;
            }
            &:hover {
                margin-top: 70px;
            }
        }
    }
}

}

</style>
