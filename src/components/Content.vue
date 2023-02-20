<template>
    <div class="content-container">
        <div class="content-image-container">
            <img v-if="stage == 1" :src="require('@/assets/'+planet.image1)" alt="mercury">
            <img v-else-if="stage == 2" :src="require('@/assets/'+planet.image2)" alt="mercury">
            <img v-else :src="require('@/assets/'+planet.image3)" alt="mercury">
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
        return {
            stage: 1
        }
    }, 
    methods: {
        setStage (number) { this.stage = number },
        isActive ( number ) { if (this.stage == number) return 'background-color: ' + this.planet.color}
    }
}
</script>

<style>
    .content-container{
        width: 80vw;
        margin-top: 5vh;
        align-items: flex-start;
        font-size: 1vw;
    }
    .content-image-container{
        width: 65%;
        justify-content: center;
        min-height: 50vh;
    }
    .content-info-planet-overview-height{
        min-height: 17vh;
    }
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
</style>