<script>
import AppSectionOne from './AppSectionOne.vue';
import AppSectionTwo from './AppSectionTwo.vue';
import AppSectionThree from './AppSectionThree.vue';
import AppSectionFour from './AppSectionFour.vue';
import AppSectionFive from './AppSectionFive.vue';
import AppSectionSix from './AppSectionSix.vue';

export default {
    components: { AppSectionOne, AppSectionTwo, AppSectionThree, AppSectionFour, AppSectionFive, AppSectionSix },
    data() {
        return {

        }
    },
}
</script>
<template>
    <div>
        <div class="bg-sec-one">
            <AppSectionOne />
        </div>
        <AppSectionTwo />
        <AppSectionThree />
        <AppSectionFour />
        <AppSectionFive />
        <AppSectionSix />
    </div>
</template>
<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

    * {
        color: white;
    }

    .bg-sec-one {
        background-color: white;
    }
</style>