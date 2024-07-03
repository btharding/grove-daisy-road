<script>
    export default {
        name: 'Event',
        components: {},
        props: {
            date: String,
            city: String,
            venue: String
        },
    }
</script>

<template>
    <div class="event-container">
        <span id="date">{{ date }}</span>
        <span id="city">{{ city }}</span>
        <span id="venue">{{ venue }}</span>
        <span id="tickets">Get Tickets</span>
    </div>
</template>

<style scoped>
    @media screen and (max-width: 650px) {
        .event-container {
            grid-template-columns: 1fr !important;
        }
    }
    .event-container {
        width: 90%;
        max-width: 1000px;
        border: 1px solid black;
        background-color: white;
        margin: 0px auto 10px auto;
        display: grid;
        grid-template-columns: 1fr 3fr 3fr 1fr;
        place-items: center;
    }

    .event-container span {
        font-size: 30px;
        font-weight: 400;
        text-align: center;
        padding: 10px;
    }

    #tickets {
        font-size: 20px;
        font-weight: 500;
        color: #f00;
        transition: all 0.3s;
    }

    #tickets:hover {
        color: #900;
        font-weight: 700;
    }
</style>