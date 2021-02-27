<template>
    <div id="app">
        <div class="container">
                <button class="collapse" @click="change">
                    <img :class="{'down':isActive,'up':!isActive}" src="./assets/course-down.png" alt="">
                </button>
            <collapse>
                <div class="container" v-show="isActive">
                    <h2>王海坤是傻逼</h2>
                </div>
            </collapse>
        </div>
    </div>
</template>
<style>
    img {
        width: 50px;
        height: 50px;
    }

    .down {
        transition: 0.2s;
        transform-origin: center;
        transform: rotateZ(180deg);
    }

    .up {
        transition: 0.2s;
        transform-origin: center;
        transform: rotateZ(0deg);
    }

    .collapse {
        box-sizing: border-box;
        position: relative;
        display: flex;
        justify-content: center;
        margin-left: 50%;
        background: #bde4fb;
        width: 50px;
        height: 50px;
        border: none;
        outline: none;

    }

    .collapse::before {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        border-left: 50px solid transparent;
        border-bottom: 50px solid #bde4fb;
        transform: translate(-100%);
    }
</style>
<script>
    import collapse from "./collapse";

    export default {
        name: "App",
        components: {
            collapse
        },
        data() {
            return {
                isActive: false
            };
        },
        methods: {
            change() {
                this.isActive = !this.isActive;
                this.$refs.icon.style.transform = "rotate(180deg)";
            }
        }
    };
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
