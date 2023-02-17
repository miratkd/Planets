<template>
    <div role="heading" class="Header-container">
        <div class="Header-title">THE PLANETS</div>
        <div class="Header-menu">
            <button class="Header-menu-button">mercury</button>
            <button class="Header-menu-button">venus</button>
            <button class="Header-menu-button">earth</button>
            <button class="Header-menu-button">mars</button>
            <button class="Header-menu-button">jupiter</button>
            <button class="Header-menu-button">saturn</button>
            <button class="Header-menu-button">uranus</button>
            <button class="Header-menu-button">neptune</button>
        </div>
    </div>
</template>

<script>
export default {
    name: "HeaderComponent"
}
</script>

<style>
    .Header-container{
        padding: 3vh 3vw;
        border-bottom: 1px solid white;
        width: 100vw;
        font-size: 1vw;
        justify-content: space-between;
    }
    .Header-title{
        font-family: 'Antonio';
        font-size: 1.9em;
        color: white;
        letter-spacing: -1.05px;
    }
    .Header-menu{ gap: 2vw; }
    .Header-menu-button{
        background-color: transparent;
        color: white;
        font-size: 1.4em;
        border: none;
        cursor: pointer;
    }
    @media (max-width: 820px){
        .Header-container{
            font-size: 2vw;
            flex-direction: column;
            gap: 3vh;
        }

    }
</style>