<script>
import CustomButton from './CustomButton.vue';
export default {
    components: { CustomButton }
}
</script>

<template >
    <div class="helper-start row row-cols-2">
        <h2>
            we help to deliver <br> the business case
        </h2>
        <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati, quos maiores. Optio alias nemo repellat beatae tempore voluptas ullam repellendus consequuntur totam? Necessitatibus quia odit, ab tempora corporis accusantium neque?
        </p>
        <CustomButton :initial-color="'rgb(247, 30, 58)'" :buttonText="'GET STARTED'" />
    </div>
</template>


<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.row {
    @include flex(row, center, center);
    height: 300px;
    color: black;
    padding-left: $margin-left;
    margin-right: $margin-right;
    padding-right: $margin-right;
    background-color: $main-green-color;
    position: relative;
    h2 {
        text-align: center;
        text-transform: uppercase;
    }
    button {
        color: white;
        position: absolute;
        bottom: 0;
        right: 0;
    }
}


    
</style>