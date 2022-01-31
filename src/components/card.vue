<template>
    <div>
            <div>                   
                <img :src="immagine" alt="">
                <h3>{{titolo}}</h3>
                <h5>{{autore}}</h5>
                <h5>{{anno}}</h5>
                    
            </div>
    </div>
</template>

<script>
export default {
    props: {
        immagine: String,
        titolo: String,
        autore: String,
        anno: String,
    }
}

</script>

<style lang="scss">
</style>
