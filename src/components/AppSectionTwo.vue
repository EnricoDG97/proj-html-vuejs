<script>
import { store } from '../store';
export default {
    data() {
        return {
            store,

            backgroundImage: "../assets/images/business-people-working-together-on-project-and-5FHSKBL.jpg"
        }
    },
    methods: {
        getImageUrl(imgName) {
            return new URL(imgName, import.meta.url).href;
        },
        changeImage() {
            this.backgroundImage = "../assets/images/hover/customer-hover.png"
        },
        restoreImage() {
            this.backgroundImage = "../assets/images/business-people-working-together-on-project-and-5FHSKBL.jpg"
        }
    }
}
</script>

<template >
    <div class="customer-section">
        <div class="section-left">
            <div class="image-container">
                <img :src="getImageUrl(backgroundImage)" alt="" @mouseover="changeImage" @mouseout="restoreImage">
            </div>
        </div>
        <div class="section-right">
            <div class="description">
                <div class="subtitle d-flex">
                    <span class="green-line"></span>
                    <p>about us</p>
                </div>
                <h2>
                    we make your strategy work
                </h2>
                <p>
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sunt sed, accusamus ex fugiat repudiandae asperiores? Animi illum deleniti doloremque id nobis rerum inventore ipsam, porro soluta tenetur assumenda perferendis qui.
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo facere laudantium animi odio rem aut nisi nobis quibusdam dolor aliquam beatae ipsa, dolorum magnam cupiditate ipsam adipisci voluptas obcaecati. Id?
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis est cum temporibus quia rem porro molestiae pariatur dolorem! Adipisci, accusantium? Porro doloribus nihil itaque eius. Deleniti delectus accusantium at. Assumenda?
                </p>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.customer-section {
    @include flex(row,center,center);
    margin-right: $margin-right;
    .section-right {
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
                    color: white;
                }
            }
    
            h2 {
                font-size: 60px;
                text-transform: uppercase;
                z-index: 1;
            }

            p {
                font-weight: 200;
                color: $main-gray;
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
    
    .section-left {
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
                display: block;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                object-fit: cover;
            }
        }
    }
}

</style>