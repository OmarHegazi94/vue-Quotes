<template>
    <div class="col-sm-6 col-md-4 col-lg-3 my-3">
        <div class="card">
            <div class="card-body">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {};
</script>

<style>
    .card {
        cursor: pointer;
    }

    .card:hover {
        background-color: #ffe2e2;
    }
</style>
