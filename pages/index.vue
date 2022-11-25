<template>
    <div>
        <SearchPanel :data="restros"/>
        <Filters />
        <List :data="restros" />
        <HorizontalRule />
    </div>
</template>

<script setup>
const { data: restros } = await useFetch('http://127.0.0.1:5500/restro', { mode: 'no-cors'});
</script>
