<script>
import CustomButton from "../components/CustomButton.vue"
import { store } from "../store.js"
export default {
    components: { CustomButton },
    data() {
        return {
            store,
            mainGreenColor: 'rgb(53, 255, 191)',
            mainRedColor: 'rgb(247, 30, 58)',
            backgroundImage: "../assets/images/portrait-of-young-architect-woman-on-meeting-KFZCE3A.jpg"
        }
    },
    methods: {
        getImageUrl(imgName) {
            return new URL(imgName, import.meta.url).href;
        },
        changeImage() {
            this.backgroundImage = "../assets/images/hover/client-hover.png"
        },
        restoreImage() {
            this.backgroundImage = "../assets/images/portrait-of-young-architect-woman-on-meeting-KFZCE3A.jpg";
        }
    }
}
</script>
<template>
    <div class="header">
        <nav class="fixed-top">
            <div class="logo">
                <img src="../assets/images/logotype.png" alt="logo">
            </div>
            <ul class="nav-links text-light">
                <li v-for="(link, index) in store.links" :key="index">
                    <a href="">{{ link }}</a>
                </li>
            </ul>
        </nav>
        <div class="header-left">
            <div class="description">
                <div class="subtitle d-flex">
                    <span class="green-line"></span>
                    <p>always the best way you need it</p>
                </div>
                <h2>
                    the best business consulting
                </h2>
                <div class="buttons">
                    <CustomButton :initialColor="mainGreenColor" :buttonText="'read me'" />
                    <span class="icon-container">
                        <i class="fa-solid fa-play"></i>
                    </span>
                </div>
            </div>
        </div>
        <div class="header-right">
            <div class="image-container">
                <img :src="getImageUrl(backgroundImage)" alt="" @mouseover="changeImage" @mouseout="restoreImage">
            </div>
        </div>


    </div>
</template>
<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.header {
    display: flex;
    flex-direction: row;
    width: 100vw;

    nav {
        @include flex(row, space-between, center);
        background-color: rgba(0, 0, 0, 0);
        height: 80px;
        margin-left: $margin-left;
        margin-right: $margin-right;
        overflow: hidden;

        .logo img {
            height: 1rem;
            width: auto;
            display: block;
        }

        ul {
            @include flex(row, space-between, center);
            gap: 20px;
            list-style-type: none;
            height: 100%;
            margin: 0;
            padding: 0;
            position: relative;

            li {
                text-transform: uppercase;
                height: 100%;
                @include flex(column, center, center);
                position: relative;

                a {
                    text-decoration: none;
                    color: white;
                    cursor: pointer;
                    padding: 4px;
                }

                &::before {
                    content: '';
                    position: absolute;
                    left: 0;
                    top: 4px;
                    background-color: white;
                    height: 4px;
                    opacity: 0;
                    transition: opacity 0.2s ease;
                    width: 100%;
                }

                &:hover::before {
                    opacity: 1;
                }
            }
        }
    }
}

.header-left {
    width: 35%;
    margin-top: 80px;
    color: white;
    margin-left: $margin-left;
    padding-bottom: 80px;
    @include flex(column, center, start);

    .description {
        @include flex(column, center, start);
        .subtitle {
            position: relative;
            .green-line {
                position: absolute;
                top: 25%;
                left: 0;
                height: 4px;
                width: 40px;
                background-color: $main-green-color;
                vertical-align: bottom;
            }
            p {
               text-transform: uppercase; 
               margin-left: 50px;
            }
        }

        h2 {
            font-size: 120px;
            text-transform: uppercase;
            z-index: 1;
        }

        .buttons {
            @include flex(row, center, center);
            gap: 30px;
            .icon-container {
                display: inline-block;
                width: 30px;
                height: 30px;
                border-radius: 50%;
                border: 2px solid white;
                overflow: hidden;
                text-align: center;
                cursor: pointer;
                i {
                    font-size: 15px;
                    color: $main-green-color;
                    line-height: 30px;
                    line-height: 0;
                }
            }

        }
    }
}

.header-right {
    width: 65%;
    overflow: hidden;
    position: relative;

    .image-container {
        width: 100%;
        position: relative;
        overflow: hidden;
        height: 0;
        padding-top: 90%;

        img {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
    }
}</style>