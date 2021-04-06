<template>
    <div class="row mb-5">
      <div class="col">
        <div class="progress">
            <div class="progress-bar" role="progressbar" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"
              :style="{ width: (QuoteCount / MaxCount) * 100 + '%' }">
              {{ QuoteCount }} / {{ MaxCount }}
            </div>
        </div>

      </div>
    </div>
</template>

<script>
export default {
  props: ['QuoteCount', 'MaxCount']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
