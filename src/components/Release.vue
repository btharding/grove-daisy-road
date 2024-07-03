<script>
    export default {
        name: 'Release',
        components: {},
        props: {
            releaseLinks: Array,
            releaseName: String,
            trackList: Array,
            trackImgFilename: String
        },
        methods: {
            formatImgUrl: function (filename) {
                return new URL(`../assets/img/${filename}`, import.meta.url).href;
            }
        },
    }
</script>

<template>
    <div class="release-container">
        <div id="albumImg">
            <img :src="formatImgUrl(trackImgFilename)">
        </div>
        <div id="albumDetails">
            <div class="albumLinks">
                <span v-for="link in releaseLinks">{{ link.title }}</span>
            </div>
            <h2>
                {{ releaseName }}
            </h2>
            <div v-for="track in trackList" class="track-listing">
                <span id="track-no">{{ track.no }}</span>
                <span id="track-name">{{ track.name }}</span>
                <span id="track-length">{{ track.length }}</span>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .track-listing {
        display: grid;
        grid-template-columns: 50px 1fr 50px;
        margin: 0px 5px 5px 5px;
    }

    .track-listing span {
        font-size: 20px;
        font-weight: 300;

    }

    #albumDetails {
        padding: 10px;
        text-transform: uppercase;

    }
    .albumLinks {
        width: 100%;
        margin-bottom: 20px;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
    }
    .albumLinks span {
        margin: 0px 5px 0px 5px;
        font-size: 20px;
        font-weight: 400;
        padding: 3px;
        transition: all 0.3s;
    }

    .albumLinks span:hover {
        font-weight: 600;
    }

    #albumDetails h2{
        margin-bottom: 20px;
    }
    .release-container  {
        width: 90%;
        max-width: 1000px;
        border: 1px solid black;
        background-color: white;
        margin: 0px auto 20px auto;
        display: grid;
        text-align: center;
        grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    }

    @media screen and (max-width: 400px) {
        .release-container {
            grid-template-columns: 1fr;
        }
    }


    @media (prefers-reduced-motion: no-preference) {
        #albumImg img {
            animation: rotates linear 8s infinite;
        }
    }

    @keyframes rotates {
        from { transform: rotate(0deg) }
        to { transform: rotate(360deg) }
    }

    #albumImg {
        width: 90%;
        aspect-ratio: 1/1;
        border-radius: 50%;
        overflow: hidden;
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: #60D641;
        margin: 10px;
        place-self: center
    }

    #albumImg img {
        width: 70%;
        object-fit: cover;
        object-position: center;
    }
</style>