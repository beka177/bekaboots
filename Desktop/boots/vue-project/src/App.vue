<script setup>
        import { ref, computed } from "vue";        
    let products = ref([
        {
            id: 1,
            name: 'redmi',
            date: '20.11.2023',
            count: 20,
            price: 10,
        },
        {
            id: 2,
            name: 'nokia',
            date: '20.11.2013',
            count: 200,
            price: 190,
        },
/*         {
            id: 3,
            name: 'google',
            date: '20.10.2013',
            count: 2300,
            price: 90,
        },
        {
            id: 4,
            name: 'momo',
            date: '10.11.2013',
            count: 203,
            price: 1970,
        },         */
])
let name = ref('lol');
let date = ref('');
let count = ref(1);
let price = ref(0);

let addProduct = () => {
    if (name.value && date.value && count.value && price.value) {
        products.value.push(
            {
            id: Date.now(),
            name: name.value,
            date: (new Date(date.value)).toLocaleDateString(),
            count: count.value,
                price: price.value,
        },   
        )
    }
}

let removeProduct = (id) => {
    products.value = products.value.filter((product) => product.id != id);
}


let totalSum = computed(() => {
    return products.value.reduce((sum, product) => sum + (product.price * product.count), 0)
})
</script>

<template>
    <div class="container">
    <div class="row">
        
        <div class="col">
            <h1 class="text-center mt-4">Учёт товаров</h1>
            <form action="">
                <div class="mb-3">
                    <label for="date" class="form-label">Название</label>
                    <input type="text"  class="form-control" :class="{'is-invalid' : !name}" id="name" v-model="name"> 
                    <div class="invalid-feedback">
                     имя напиши лол
                     </div>
                </div>
                <div class="mb-3">
                    <label for="date" class="form-label">Дата</label>
                    <input type="date" class="form-control" :class="{'is-invalid' : !name}" id="name" v-model="date" >
                    <div class="invalid-feedback">
                    а когда...
                      </div>
                </div>
                <div class="mb-3">
                    <label for="date" class="form-label">Количество</label>
                    <input type="number" class="form-control" :class="{'is-invalid' : !count}" id="name" v-model="count">
                    <div class="invalid-feedback">
                        напиши число лол
                    </div>    
                </div>
                <div class="mb-3">
                    <label for="date" class="form-label">Цена</label>
                    <input type="number" class="form-control" :class="{'is-invalid' : !name}" id="name" v-model="price">
                    <div class="invalid-feedback">
                    скоко!?!??!?!
                    </div>
                </div>
                <div class="text-center mb-3">
                    <button @click="addProduct" type="button" class="btn btn-dark">Добавить</button>
                </div>

            </form>
        </div>
    </div>
    <div class="row">
        <div class="col" v-for="i in products" :keys="i.id" >
            <div class="card text-center">
  <div class="card-header">
    Featured
  </div>
  <div class="card-body">
    <h5 class="card-title">{{i.name}}</h5>
    <p class="card-text">date:{{i.date}}</p>
    <p class="card-text">${{i.price}}</p>
    <p class="card-text">x{{i.count}}</p>

    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
  <div class="text-center mb-3">  
                    <button @click="removeProduct(i.id)" type="button" class="btn btn-light">delete</button>
    </div>
  <div class="card-footer text-body-secondary">
    2 days ago
  </div>
</div>

        </div>
    </div>
    
<div class="row my-4">
    <div class="col">
        <h3 class="text-end">Total summary: ${{ totalSum }}</h3>
    </div>
</div>
</div>

</template>

