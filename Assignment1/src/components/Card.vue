
<script setup>
    
</script>

<template>
    <div class="card-container">
        <div class="card-header">
            <slot name="header"></slot>
        </div>
        <div class="card-title">
            <slot name="title"></slot>
        </div>
        <div class="card-body">
            <slot name="body"></slot>
        </div>
        <div class="card-footer">
            <slot name="footer"></slot>
        </div>
    </div>
</template>

<style scoped>

.card-container {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  width: 40%;
  margin:auto
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.container {
  padding: 2px 16px;
}

</style>