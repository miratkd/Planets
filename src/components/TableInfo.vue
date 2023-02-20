<template>
    <div class="content-table-container">
        <div class="content-table-square">
            <p class="content-table-square-title">Tempo de rotação</p>
            <p class="content-table-square-value">{{ planet.rotationTime }}</p>
        </div>
        <div class="content-table-square">
            <p class="content-table-square-title">Tempo de volta</p>
            <p class="content-table-square-value">{{ planet.revolutionTime }}</p>
        </div>
        <div class="content-table-square">
            <p class="content-table-square-title">Raio</p>
            <p class="content-table-square-value">{{ planet.radius }}</p>
        </div>
        <div class="content-table-square">
            <p class="content-table-square-title">Temperatura media</p>
            <p class="content-table-square-value">{{ planet.averageTemp }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "TableInfo",
        props: ['planet']
    }
</script>

<style>
    .content-table-container{
        gap: 4vw;
        margin-top: 7vh;
        font-size: 1vw;
    }
    .content-table-square{
        border: 1px solid white;
        padding: 2vh 1.5vw;
        min-width: 14vw;
        flex-direction: column;
        align-items: flex-start;
        gap: 2vh;
    }
    .content-table-square-title{
        font-weight: 700;
        font-size: 1.2em;
        color: white;
        opacity: 0.5;
        margin: 0;
        text-transform: uppercase;
    }
    .content-table-square-value{
        font-weight: 400;
        font-size: 2.4em;
        color: white;
        margin: 0;
        letter-spacing: -1px;
        font-family: 'Antonio';
    }
    @media (max-width: 820px) {
        .content-table-square-title{font-size: 1.25em;}
        .content-table-square-value{font-size: 3em;}
    }
    @media (max-width: 430px) {
        .content-table-container{ 
            margin-top: 2vh; 
            padding-bottom: 5vh;
            flex-direction: column;
            width: 80%;
        }
        .content-table-square{ 
            width: 100%; 
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
        }
        .content-table-square-title{font-size: 3em}
        .content-table-square-value{font-size: 5em;}
    }
</style>