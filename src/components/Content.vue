<template>
    <div class="content-mobile-buttons">
        <div v-on:click="setStage(1)" class="content-mobile-button" :style="isActiveMobile(1)">Resumo</div>
        <div v-on:click="setStage(2)" class="content-mobile-button" :style="isActiveMobile(2)">Estrutura interna</div>
        <div v-on:click="setStage(3)" class="content-mobile-button" :style="isActiveMobile(3)">Geologia da superface</div>
    </div>
    <div class="content-container">
        <div class="content-image-container">
            <img v-show="stage == 1" :src="require('@/assets/'+planet.image1)" alt="mercury" class="content-image-mobile">
            <img v-show="stage == 2" :src="require('@/assets/'+planet.image2)" alt="mercury" class="content-image-mobile">
            <img v-show="stage == 3" :src="require('@/assets/'+planet.image3)" alt="mercury" class="content-image-mobile">
        </div>
        <div class="content-info-container">
            <div class="content-info-value">
                <h1 class="content-info-planet-name">{{ planet.name }}</h1>
                <p v-if="stage == 1" class="content-info-planet-text content-info-planet-overview-height">{{ planet.overview }}</p>
                <p v-else-if="stage == 2" class="content-info-planet-text content-info-planet-overview-height">{{ planet.internalStructure }}</p>
                <p v-else class="content-info-planet-text content-info-planet-overview-height">{{ planet.surfaceGeology }}</p>
                <div class="content-info-source-container">
                    <p class="content-info-planet-text">Fonte: </p>
                    <a :href="planet.link" target="_blank" class="content-info-source-link">Wikipedia</a>
                    <span class="material-icons content-info-source-icon" >open_in_new</span>
                </div>
            </div>
            
            <div class="content-info-buttons">
                <button v-on:click="setStage(1)" :style="isActive(1)" class="content-info-button" >
                    <div class="content-info-button-number">01</div>
                    <div class="content-info-button-text">Resumo</div>
                </button>
                <button v-on:click="setStage(2)" :style="isActive(2)" class="content-info-button" >
                    <div class="content-info-button-number">02</div>
                    <div class="content-info-button-text">Estrutura interna</div>
                </button>
                <button v-on:click="setStage(3)" :style="isActive(3)" class="content-info-button" >
                    <div class="content-info-button-number">03</div>
                    <div class="content-info-button-text">Geologia da superface</div>
                </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'PageContent',
    props: ['planet'],
    data () {
        return { stage: 1 }
    }, 
    methods: {
        setStage (number) { this.stage = number },
        isActive ( number ) { if (this.stage == number) return 'background-color: ' + this.planet.color},
        isActiveMobile ( number ) { if (this.stage == number) return 'opacity: 1; border-bottom: 1vh solid ' + this.planet.color}
    },
    watch: {
        planet () {this.stage = 1}
    }
}
</script>

<style>
    .content-container{
        width: 80vw;
        margin-top: 4vh;
        align-items: flex-start;
        font-size: 1vw;
    }
    .content-image-container{
        width: 65%;
        justify-content: center;
        min-height: 50vh;
    }
    .content-info-planet-overview-height{
        min-height: 19vh;
    }
    .content-mobile-buttons{display: none;}
    .content-info-container{
        flex-direction: column;
        width: 35%;
    }
    .content-info-value{
        flex-direction: column;
        align-items: flex-start;
    }
    .content-info-buttons{
        flex-direction: column;
        width: 100%;
    }
    .content-info-planet-name{
        color: white;
        font-size: 3.5em;
        font-family: 'Antonio';
        margin: 0;
    }
    .content-info-planet-text{
        color: white;
        font-size: 1.2em;
        margin: 1.5vh 0;
    }
    .content-info-source-container{ gap: 0.5vw; }
    .content-info-source-link{
        font-size: 1.25em;
        color: white;
    }
    .content-info-source-icon{
        font-size: 1.5em;
        color: white;
    }
    .content-info-button{
        width: 100%;
        background-color: transparent;
        border: 1px solid white;
        display: flex;
        align-items: center;
        padding: 2vh 0;
        margin-top: 2.5vh;
        cursor: pointer;
    }
    .content-info-button-number{
        margin-left: 2vw;
        font-size: 1.2em;
        color: white;
        opacity: 0.5;
    }
    .content-info-button-text{
        margin-left: 2vw;
        font-size: 1.2em;
        color: white;
        text-transform: uppercase;
        font-weight: 700;
    }
    .content-info-button:hover{ background-color: #838391; }
    @media (max-width: 820px) {
        .content-container {
            flex-direction: column;
            gap: 2vh;
        }
        .content-image-container {
            width: 100%;
            min-height: 0;
        }
        .content-info-container{
            flex-direction: row;
            width: 100%;
            justify-content: space-between;
        }
        .content-info-value{
            width: 40%;
        }
        .content-info-buttons{ width: 45%; }
        .content-info-button{
            margin-top: 0;
            margin-bottom: 2.5vh;
        }
        .content-info-planet-name{ font-size: 6em; }
        .content-info-planet-text{ font-size: 1.8em; }
        .content-info-planet-overview-height{ min-height: 14vh; }
        .content-info-source-link{font-size: 2em; }
        .content-info-source-icon{ font-size: 3em;}
        .content-info-source-container{ gap: 1.5vw; }
    }
    @media (max-width: 430px){
        .content-image-mobile{ transform: scale(0.6); }
        .content-info-buttons{ display: none; }
        .content-info-value{
            width: 100%;
            align-items: center;
        }
        .content-info-planet-name{font-size: 11em;}
        .content-info-planet-text{font-size: 3em;}
        .content-info-source-link{font-size: 4em;}
        .content-info-source-icon{font-size: 5em;}
        .content-mobile-buttons{
            display: flex;
            border-bottom: 0.1vh solid white;
            justify-content: space-evenly;
            width: 100vw;
        }
        .content-mobile-button{
            color: white;
            opacity: 0.5;
            font-weight: 700;
            text-transform: uppercase;
            font-size: 0.6em;
            padding: 2vh 0;
            border-bottom: 1vh solid transparent;
        }
    }
</style>