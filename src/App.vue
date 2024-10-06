<template>
    <Scene @onSceneLoad="onSceneLoad" />
    <div ref="loading" class="loading-screen">
        <div class="loader">
    <div class="ring"></div>
    <div class="dot"></div>
</div>

        <p>Loading...</p>
    </div>
</template>

<script>
    import Scene from "./components/Scene.vue";
    export default {
        components: {
            Scene,
        },
        methods: {
            onSceneLoad() {
                this.$refs.loading.style.display = "none";
            }
        }
    }
</script>

<style scoped lang="scss">
    .loading-screen {
        position: absolute;
        top: 0;
        left: 0;
        z-index: 2;
        width: 100%;
        height: 100%;
        background-color: var(--dark);
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 16px;
        font-weight: bold;
        .loader {
    position: relative;
    width: 80px;
    height: 80px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 auto;
}

.ring {
    width: 80px;
    height: 80px;
    border: 8px solid rgba(255, 255, 255, 0.3);
    border-top: 8px solid #9c2ae8;
    border-radius: 50%;
    animation: spin 2s linear infinite;
}

.dot {
    position: absolute;
    width: 15px;
    height: 15px;
    background-color: #9c2ae8;
    border-radius: 50%;
    animation: pulse 1s ease-in-out infinite;
}

/* Ring spinning animation */
@keyframes spin {
    0% {
        transform: rotate(0deg);
    }
    100% {
        transform: rotate(360deg);
    }
}


    }
</style>
