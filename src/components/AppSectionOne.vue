<script>
export default {
    data() {
        return {
            list: [
                {
                    class: "fa-chart-line",
                    title: "statistical consulting",
                    text: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Cumque sequi, molestiae praesentium hic a aut laboriosam suscipit minima omnis harum aspernatur molestias repellendus? Sed commodi laborum nostrum saepe recusandae voluptas!"
                },
                {
                    class: "fa-bullhorn",
                    title: "digital consulting",
                    text: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Cumque sequi, molestiae praesentium hic a aut laboriosam suscipit minima omnis harum aspernatur molestias repellendus? Sed commodi laborum nostrum saepe recusandae voluptas!"
                },
                {
                    class: "fa-folder-open",
                    title: "banking consulting",
                    text: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Cumque sequi, molestiae praesentium hic a aut laboriosam suscipit minima omnis harum aspernatur molestias repellendus? Sed commodi laborum nostrum saepe recusandae voluptas!"
                },
                {
                    class: "fa-crosshairs",
                    title: "enterprise consulting",
                    text: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Cumque sequi, molestiae praesentium hic a aut laboriosam suscipit minima omnis harum aspernatur molestias repellendus? Sed commodi laborum nostrum saepe recusandae voluptas!"
                },
            ]
        }
    }
}
</script>

<template >
    <div class="header">
        <h2>our consultants can help you</h2>
        <span class="green-line"></span>
    </div>
    <ul class="row row-cols-2 g-5">
        <li v-for="(item, index) in list" :key="index">
            <div class="icon-container">
                <i class="fa-solid" :class="item.class"></i>
            </div>
            <div>
                <h3> {{ item.title }}</h3>
                <p> {{ item.text }}</p>
            </div>
        </li>
    </ul>
</template>


<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

* {
    color: black;
}

.header {
    @include flex(row, center, center);
    gap: 20px;
    padding-top: 150px;

    // position: relative;
    h2 {
        text-transform: uppercase;
        font-size: 40px;
        min-width: 50%;
        text-align: end;
    }

    .green-line {
        // position: absolute;
        // top: 50%;
        // left: 50%;
        height: 4px;
        width: 100%;
        background-color: $main-green-color;
        vertical-align: bottom;
    }
}

ul.row {
    list-style-type: none;
    margin-left: $margin-left;
    margin-right: $margin-right;
    margin-top: 20px;
    padding-bottom: 150px;

    li {
        @include flex(row, center, start);
        position: relative;
        div {
            h3 {
                text-transform: uppercase;
            }
        }
        .icon-container {
            position: absolute;
            top: 5px;
            left: -20px;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            background-color: red;
            overflow: hidden;
            text-align: center;
            cursor: pointer;
            i.fa-solid {
                font-size: 15px;
                color: white;
                line-height: 0;
                margin-top: 15px;
            }
        }

        div {
            display: inline-block;
            vertical-align: middle;
        }
    }
}</style>