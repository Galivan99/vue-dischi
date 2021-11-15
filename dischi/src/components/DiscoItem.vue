<template>
    <div class="container">
        <img :src="item.poster" :alt="item.img">
        <h4>{{item.title.toUpperCase()}}</h4>
        <h5>{{item.author}}</h5>
        <h5>{{item.year}}</h5>
    </div>

</template>

<script>
export default {
    name: 'discoItem',
    props: ['item']
}
</script>

<style scoped lang="scss">

    .container {
        width: 100%;
        height: 100%;
        cursor: pointer;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;



        img {
            width: 150px;
            height: 150px;
            margin-top: 10px;
        }

        h4 {
            color: white;
            text-align: center;
            word-break: break-word;
        }
        h5 {
            color: #64797F;
            text-align: center;
        }
        
    }
</style>