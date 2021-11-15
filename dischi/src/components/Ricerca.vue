<template>
    <form>
        <select @click.prevent="$emit('effettuaRicerca', section)"  v-model="section" name="genere" id="genere">
            <option value="tutto">All</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
    </form>
</template>

<script>
export default {
    name: 'Ricerca',
    data () {
        return {
            section: 'tutto',
        }
    },
}
</script>

<style scoped lang="scss">
select {
    width:220px;
    height: 30px;
    border-radius: 15px;

}
</style>