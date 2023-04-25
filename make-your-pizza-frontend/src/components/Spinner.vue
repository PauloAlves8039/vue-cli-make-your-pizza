<template>
    <div class="spinner-body" v-if="loading">
        <div class="spinner-grow text-success spinner-boder" role="status">
            <span class="visually-hidden">Loading...</span>
        </div>
    </div>
</template>
<script>
export default {
    name: "Spinner",
    data() {
    return {
      loading: true
    }
  },
  async mounted() {
    await new Promise((resolve) => setTimeout(resolve, 2000));
    this.loading = false;
  },
}
</script>
<style scoped>
.spinner-body {
    display: flex;
    justify-content: center;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    align-items: center;
    transition: all 0.2s;
    opacity : 0.7;
    z-index: 9999;
    background-color: var(--var-system-color-black);
}

.spinner-boder {
    width: 5rem;
    height: 5rem;
    background-color: var(--var-system-color-success);
}
</style>