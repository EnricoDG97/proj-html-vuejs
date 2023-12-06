<script>
export default {
    props: {
        initialColor: {
            type: String,
            default: 'rgb(53, 255, 191)'
        },
        buttonText: {
            type: String,
            default: 'Button'
        },
    },
    data() {
        return {
            changeBackgroundColor: this.initialColor,
            isGreen: this.initialColor === 'rgb(53, 255, 191)',
            isHovered: false
        };
    },
    methods: {
        handleMouseEnter() {
            if (!this.isHovered) {
                this.isHovered = true;
                this.changeBackgroundColor = this.isGreen ? 'rgb(247, 30, 58)' : 'rgb(53, 255, 191)';
            }
        },
        handleMouseLeave() {
            this.isHovered = false;
            this.changeBackgroundColor = this.isHovered ? 'rgb(247, 30, 58)' : this.initialColor;
        }
    }
};
</script>

<template>
    <button :style="{ backgroundColor: changeBackgroundColor }" @mouseenter="handleMouseEnter"
        @mouseleave="handleMouseLeave">
        {{ buttonText }}
    </button>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

button {
    border: none;
    padding: 0.5rem 1.5rem;
    width: 150px;
    text-transform: uppercase;
    transition: background-color 0.3s;
}
</style>