<script setup>

</script>

<template>
    <div class="container">
    <div class="row">
        
        <div class="col">
            <h1 class="text-center mt-4">Учёт товаров</h1>
            <form action="">
                <div class="mb-3">
                    <label for="date" class="form-label">Название</label>
                    <input type="text" class="form-control" id="name" >
                </div>
                <div class="mb-3">
                    <label for="date" class="form-label">Дата</label>
                    <input type="date" class="form-control" id="name" >
                </div>
                <div class="mb-3">
                    <label for="date" class="form-label">Количество</label>
                    <input type="number" class="form-control" id="name" >
                </div>
                <div class="mb-3">
                    <label for="date" class="form-label">Цена</label>
                    <input type="number" class="form-control" id="name" >
                </div>
                <div class="text-center mb-3">
                    <button type="button" class="btn btn-dark">Добавить</button>
                </div>
            </form>
        </div>
    </div>
    <div class="card text-center">
  <div class="card-header">
    Featured
  </div>
  <div class="card-body">
    <h5 class="card-title">Redmi 10 c</h5>
    <p class="card-text">20.12.25</p>
    <p class="card-text">150$</p>
    <p class="card-text">x10</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
  <div class="card-footer text-body-secondary">
    2 days ago
  </div>
</div>
    
<div class="row my-4">
    <div class="col">
        <h3 class="text-end">Total summary: $1234</h3>
    </div>
</div>
</div>

</template>

