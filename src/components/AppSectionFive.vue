<script>
export default {
    data() {
        return {
            testimonials: [
                {
                    text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Incidunt quidem ullam, quaerat numquam corporis voluptatibus, autem sint itaque laborum omnis quasi quia tempora dolores magni impedit obcaecati dolor exercitationem voluptates!",
                    name: "Vera Duncan",
                    company: "Amazon Inc."
                },
                {
                    text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Incidunt quidem ullam, quaerat numquam corporis voluptatibus, autem sint itaque laborum omnis quasi quia tempora dolores magni impedit obcaecati dolor exercitationem voluptates!",
                    name: "Duncan Vera",
                    company: "Google Inc."
                },
                {
                    text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Incidunt quidem ullam, quaerat numquam corporis voluptatibus, autem sint itaque laborum omnis quasi quia tempora dolores magni impedit obcaecati dolor exercitationem voluptates!",
                    name: "Dunra Vencan",
                    company: "Facebook Inc."
                },
            ]
        }
    }
}
</script>

<template >
    <div class="testimonials">
        <div class="subtitle d-flex">
            <p>testimonial</p>
            <span class="green-line"></span>
        </div>
        <div>
            <h3>what's the customer say <br> about our work</h3>
        </div>
    </div>
    <div class="testimonials-container">
        <ul class="testimonials-showcase row row-cols-3 g-5">
            <li v-for="(testimonial, index) in testimonials" :key="index">
                <p> {{ testimonial.text }} </p>
                <div class="autor">
                    <h3> {{ testimonial.name }} </h3>
                    <p> {{ testimonial.company }} </p>
                </div>
            </li>
        </ul>
    </div>
</template>


<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.testimonials {
    padding: 40px 0;
    margin-right: $margin-right;

    div {
        h3 {
            text-transform: uppercase;
            text-align: end;
            padding-bottom: 40px
        }
    }

    .subtitle {
        @include flex(row, center, center);
        text-align: center;
        position: relative;

        p {
            text-transform: uppercase;
            margin-left: 50px;
            color: white;
            font-weight: 200;
        }

        .green-line {
            position: absolute;
            top: 25%;
            right: 0;
            height: 4px;
            width: 40px;
            background-color: $main-green-color;
            vertical-align: bottom;
        }

    }
}

.testimonials-container {
    background-color: white;
    height: 300px;
    margin-left: $margin-left;
    ul.testimonials-showcase {
        color: black;
        list-style-type: none;
        padding: 40px;
        margin-right: $margin-right;
        li {
            margin: 0;
            p {
                font-weight: 200;
                color: $main-gray;
                font-size: small;
            }
    
            .autor {
                p {
                    font-weight: 200;
                    color: $main-gray;
                    font-size: small;
                }
            }
        }
    }
}

</style>