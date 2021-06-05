<template>
<div class="card-box-container">
        <b-jumbotron>
            <template slot="lead">
                {{ currentCard.question }}
           
            </template>
            <hr class="my-4"/>
            <p>
                tekst her
            </p>
            <b-button variant="primary" href="a"> En knap</b-button>
        </b-jumbotron>
</div>
</template>
<script>
export default {
    props: {
        currentCard: Object
    }
}
</script>