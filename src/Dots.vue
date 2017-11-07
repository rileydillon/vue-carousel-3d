<template>
    <div class="carousel-3d-dots">
        <div class="dot" v-for="(slide, i) in total" :index="i" :key="i" :style="`width: ${width}px; height: ${height}px; line-height: ${height}px;`" :class="{ active: current === i }" @click.prevent="parent.goSlide(i)" />
    </div>
</template>

<script>
    export default {
        name: 'dots',
        props: {
            /**
             * Width in pixels of the dot indicators
             */
            width: {
                type: [String, Number],
                default: 10
            },
            /**
             * Height in pixels of the dot indicators
             */
            height: {
                type: [String, Number],
                default: 10
            },
            total: {
                type: Number,
                default: 0
            },
            current: {
                type: Number,
                default: 0
            }
        },
        data () {
            return {
                parent: this.$parent
            }
        },
        mounted: function () {
        }
    }
</script>

<style scoped>
    .carousel-3d-dots {
        position: absolute;
        bottom: 0;
        left: 50%;
        transform: translateX(-50%);
        z-index: 9099;
    }

    .dot {
        display:  inline-block;
        vertical-align: top;
        background:  red;
        margin: 0 8px;
        cursor: pointer;
    }

    .active {
        background: yellow;
    }
</style>
