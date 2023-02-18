<template>
    <div role="heading" class="Header-container">
        <div class="Header-title">THE PLANETS</div>
        <div class="Header-menu desktop">
            <button class="Header-menu-button">mercury</button>
            <button class="Header-menu-button">venus</button>
            <button class="Header-menu-button">earth</button>
            <button class="Header-menu-button">mars</button>
            <button class="Header-menu-button">jupiter</button>
            <button class="Header-menu-button">saturn</button>
            <button class="Header-menu-button">uranus</button>
            <button class="Header-menu-button">neptune</button>
        </div>
        <span v-on:click="openMobileMenu()" class="material-icons Header-mobile-menu mobile">menu</span>
    </div>
    <div v-if="showMobileMenu" class="Header-mobile-menu-container mobile">
        <div class="Header-mobile-menu-row">
            <div class="Header-mobile-planet-icon mercury-color"></div>
            <p class="Header-mobile-planet-name">Mercúrio</p>
            <span class="material-icons Header-mobile-planet-open-icon">arrow_forward_ios</span>
        </div>
        <div class="Header-mobile-menu-row">
            <div class="Header-mobile-planet-icon venus-color"></div>
            <p class="Header-mobile-planet-name">Vênus</p>
            <span class="material-icons Header-mobile-planet-open-icon">arrow_forward_ios</span>
        </div>
        <div class="Header-mobile-menu-row">
            <div class="Header-mobile-planet-icon earth-color"></div>
            <p class="Header-mobile-planet-name">Terra</p>
            <span class="material-icons Header-mobile-planet-open-icon">arrow_forward_ios</span>
        </div>
        <div class="Header-mobile-menu-row">
            <div class="Header-mobile-planet-icon mars-color"></div>
            <p class="Header-mobile-planet-name">Marte</p>
            <span class="material-icons Header-mobile-planet-open-icon">arrow_forward_ios</span>
        </div>
        <div class="Header-mobile-menu-row">
            <div class="Header-mobile-planet-icon jupiter-color"></div>
            <p class="Header-mobile-planet-name">Júpiter</p>
            <span class="material-icons Header-mobile-planet-open-icon">arrow_forward_ios</span>
        </div>
        <div class="Header-mobile-menu-row">
            <div class="Header-mobile-planet-icon saturn-color"></div>
            <p class="Header-mobile-planet-name">Saturno</p>
            <span class="material-icons Header-mobile-planet-open-icon">arrow_forward_ios</span>
        </div>
        <div class="Header-mobile-menu-row">
            <div class="Header-mobile-planet-icon uranus-color"></div>
            <p class="Header-mobile-planet-name">Urano</p>
            <span class="material-icons Header-mobile-planet-open-icon">arrow_forward_ios</span>
        </div>
        <div class="Header-mobile-menu-row">
            <div class="Header-mobile-planet-icon neptune-color"></div>
            <p class="Header-mobile-planet-name">Netuno</p>
            <span class="material-icons Header-mobile-planet-open-icon">arrow_forward_ios</span>
        </div>
    </div>
</template>

<script>
export default {
    name: "HeaderComponent",
    data () {
        return {
            showMobileMenu: false
        }
    },
    methods: {
        openMobileMenu() { this.showMobileMenu = !this.showMobileMenu }
    }
}
</script>

<style>
.Header-container {
    padding: 0 3vw;
    height: 10vh;
    border-bottom: 0.1vh solid white;
    width: 100vw;
    font-size: 1vw;
    justify-content: space-between;
}
.Header-title {
    font-family: 'Antonio';
    font-size: 1.9em;
    color: white;
    letter-spacing: -1.05px;
}

.Header-menu {
    gap: 2vw;
}

.Header-menu-button {
    background-color: transparent;
    color: white;
    font-size: 1.4em;
    border: none;
    cursor: pointer;
}
.mobile{display: none;}

@media (max-width: 820px) {
    .Header-container {
        font-size: 2vw;
        flex-direction: column;
        gap: 3vh;
    }
}

@media (max-width: 430px) {
    .mobile{display: flex;}
    .Header-container {
        font-size: 3vw;
        flex-direction: row;
        gap: none;
    }

    .desktop {
        display: none;
    }

    .Header-mobile-menu {
        color: white;
        font-size: 2.2em;
        display: flex;
    }
    .mercury-color{background: #DEF4FC;}
    .venus-color{background: #F7CC7F;}
    .earth-color{background: #545BFE;}
    .mars-color{background: #FF6A45;}
    .jupiter-color{background: #ECAD7A;}
    .saturn-color{background: #FCCB6B;}
    .uranus-color{background: #65F0D5;}
    .neptune-color{background: #497EFA;}
    .Header-mobile-menu-container {
        background-color: #070724;
        position: absolute;
        top: 10.1vh;
        height: 86vh;
        width: 100vw;
        padding-top: 3vh;
        flex-direction: column;
        align-items: stretch;
    }
    .Header-mobile-menu-row{
        padding: 1vh 0;
        border-bottom: 0.1vh solid white;
    }
    .Header-mobile-planet-icon{
        width: 5.6vw;
        height: 5.6vw;
        border-radius: 50%;
        margin: 0 6vw;
    }
    .Header-mobile-planet-name{
        font-weight: 700;
        font-size: 1.1em;
        color: #FFFFFF;
        text-transform: uppercase;
        flex: 1;
    }
    .Header-mobile-planet-open-icon{
        color: white;
        font-size: 1em;
        margin-right: 6vw;
    }
}
</style>