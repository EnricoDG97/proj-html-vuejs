<script>
import CustomButton from './CustomButton.vue';
import { store } from "../store.js";

export default {
    components: { CustomButton },
    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <div class="get-started">
        <h2>let's talk about work</h2>
        <p>A wonderful serenity has taken possession Far far away, behind the word mountains</p>
        <button>GET STARTED</button>
    </div>

    <div class="footer">
        <div class="upper-footer">
            <div class="logo">
                <img src="../assets/images/logotype-2-150x25.png" alt="logo">
            </div>
            <ul class="links">
                <li v-for="(link, index) in store.links" :key="index">
                    <a href="">
                        {{ link }}
                    </a>
                </li>
            </ul>
            <div class="socials">
                <i class="fa-brands fa-instagram"></i>
                <i class="fa-brands fa-linkedin-in"></i>
                <i class="fa-brands fa-facebook-f"></i>
                <i class="fa-brands fa-twitter"></i>
            </div>
        </div>
        <hr>
        <div class="bottom-footer">
            <div class="terms">
                <a href="">Terms of use</a>
                <a href="">Privacy Enviromental Policy</a>
            </div>
            <div class="copyright">
                Copyright <i class="fa-regular fa-copyright"></i> 2020 Phlox Consulting All Rights Reserved.
            </div>
            <div class="up">
                <i class="fa-solid fa-arrow-up"></i>
            </div>
            <div class="chat">
                <i class="fa-regular fa-comment"></i>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.get-started {
    background-image: url(../assets/images/business-people-working-together-on-project-and-B3MZ4TX.jpg);
    text-align: center;
    color: white;
    height: 400px;
    @include flex(column, center, center);

    h2 {
        text-transform: uppercase;
        font-size: 50px;
    }

    p {
        font-weight: 100;
    }

    button {
        border: none;
        padding: 0.5rem 1.5rem;
        width: 150px;
        text-transform: uppercase;
        color: white;
        background-color: $main-bg-color;
    }
}

.footer {
    color: white;

    .upper-footer {
        height: 200px;
        margin-left: $margin-left;
        margin-right: $margin-right;

        @include flex(row, space-between, center);

        ul {
            list-style-type: none;
            @include flex(row, space-around, center);
            gap: 20px;

            li {
                text-transform: uppercase;

                a {
                    text-decoration: none;
                    color: rgb(121, 120, 136);
                    cursor: pointer;
                    padding: 4px;
                }
            }
        }

        .socials {
            @include flex(row, space-around, center);
            gap: 8px;

            i {
                padding: .5rem;
                cursor: pointer;
            }
        }
    }

    hr {
        margin-left: $margin-left;
        margin-right: $margin-right;
        background-color: rgb(121, 120, 136);
        height: 1px;
    }

    .bottom-footer {
        color: rgb(121, 120, 136);
        height: 150px;
        margin-left: $margin-left;
        margin-right: $margin-right;
        @include flex(row, space-between, center);
        position: relative;

        .terms {
            @include flex(column, center, start);

            a {
                text-decoration: none;
                color: inherit;
            }
        }

        .up {
            position: absolute;
            bottom: 30px;
            right: -55px;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            border: 2px solid white;
            overflow: hidden;
            text-align: center;
            cursor: pointer;
            i {
                font-size: 15px;
                color: white;
                line-height: 0;
            }
        }
        .chat {
            position: absolute;
            right: -120px;
            bottom: 20px;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: rgb(82, 124, 235);
            overflow: hidden;
            text-align: center;
            cursor: pointer;
            i {
                padding-top: 25px;
                font-size: 25px;
                line-height: 0;
                color: white;
            }
        }
    }
}</style>