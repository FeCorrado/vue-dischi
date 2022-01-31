 <template>
    <div class="big">
        <div class="boxbb">
            <Card
            v-for="(disco, index) in dischi" 
            :key="index" class="card"
            :immagine="disco.poster"
            :titolo="disco.title"
            :autore="disco.author"
            :anno="disco.year"
            />
        </div>
    </div>
</template>

<script>
import Card from './Card.vue'
export default {
    components: {
        Card,
    },
    props: {
        dischi: Array
    }
}

</script>

<style lang="scss">
@import '../style/main.scss'
</style>