<script>
export default {
    data() {
        return {
            carouselImages: [
                "../assets/images/DRY-1-790x592.jpg",
                "../assets/images/221bf0b7-8134-43bb-936a-5acbe42db64a-790x592.jpg",
                "../assets/images/z1el4c4p-790x592.jpg"
            ]
        }
    },
    methods: {
        getImageUrl(imgName) {
            return new URL(imgName, import.meta.url).href;
        },
    }
}
</script>

<template >
    <div class="carousel-section">
        <div class="subtitle d-flex">
            <span class="green-line"></span>
            <p>project</p>
        </div>
        <div class="title">
            <h2>
                our experts consultants <br> help clients
            </h2>
            <div class="arrows">
                <i class="fa-solid fa-square-caret-left"></i>
                <i class="fa-solid fa-square-caret-right"></i>
            </div>
        </div>
        <ul class="carousel row row-cols-3 g-4">
            <li v-for="(image, index) in carouselImages" :key="index">
                <img :src="getImageUrl(image)" alt="">
            </li>
        </ul>
    </div>
</template>


<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.carousel-section {
    margin-left: $margin-left;
    margin-right: $margin-right;
    padding: 40px;
    .title {
        @include flex(row,space-between,center);
        h2 {
            text-transform: uppercase;
        }
        .arrows {
            @include flex(row,space-between,center);
            gap: 8px;
            color: $main-gray;
            cursor: pointer;
        }
    }
    ul.carousel {
        padding: 40px 0;
        list-style-type: none;
        li {
            overflow: hidden;
            img {
                object-fit: contain;
                max-width: 100%;
                &:hover {
                    opacity: 0.5;
                    transition: opacity 0.3s ease;
                }
            }
        }
    }
}

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
</style>