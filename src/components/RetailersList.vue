<template>

    <div class="retailers-list">

        <div class="">
            <ul class="list-group list-group-flush" v-for="(retailer,index) in retailers" :key="retailer.id" >
                <div class="retailer-total"
                @mouseover="mouseOver(index)"
                @mouseleave="mouseLeave(index)"
                >
                    <li 
                    class="list-group-item" 
                    
                    > 
                    <b class="forceemph"> {{ retailer.storeName }} </b>  <b class="oranged">{{ retailer.storeType }}</b>
                    </li>
                    <div class="retailer-detail">
                        <div class="card">
                            <img class="card-img-top" :src="retailer.pictures" alt="">
                            <div class="card-body">
                                <h5 class="card-title">{{ retailer.storeName }}</h5>
                                <p class="card-text">{{ retailer.storeDescription }}</p>
                                <router-link :to="{name: 'Retailer', params: {id: retailer.id, retailer: retailer}}">
                                    <a href="#" class="btn btn-primary">Plus d'informations</a>
                                </router-link>
                            </div> 
                        </div>
                    </div>
                </div>
                
            </ul>
        </div>
    </div>
    
</template>

<script>
export default {
    name: 'RetailersList',
    props: ['retailers'],
    data() {
        return {
          
        }
    },
    methods: {
        mouseOver(index) {
            var t = document.querySelectorAll(".retailer-detail")
            t[index].style.display = "block"
        },
        mouseLeave(index) {
            var ta = document.querySelectorAll(".retailer-detail")
            ta[index].style.display = "none"
        },
    }
}
</script>

<style scoped>

.retailers-list {
    overflow-y : scroll;
    height: 95vh;
    width: 100%;
}

.retailer-detail {
    display: none;
}

.card-body{
    background-color: white;
}
.card-body:hover{
    background-color: white;
}
ul:hover {
    background-color: white!important;
}
.btn-primary:hover {
    background-color: black;
    color: white;
}
.btn-primary {
    color: #fff;
    background-color:#FFA008;
    border-color:#FFA008;
    border-radius: 0px;
    border: none;
}
.forceemph{
    font-weight: 700;
    font-size: 30px;
}
.oranged {
    color: #FFA008;
}
.list-group-item {
    position: relative;
    display: block;
    padding: 0.75rem 1.25rem;
    background-color: #fff;
    border: none;
}
</style>