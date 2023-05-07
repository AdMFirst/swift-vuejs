<template>
    <div>
      <div v-if="store.activeTab === 'tab1'">Content for tab 1</div>
      <div v-if="store.activeTab === 'tab2'">Content for tab 2</div>
    </div>
  </template>
  
<script>
import { store } from './store';

  
export default {
data() {
    return {
        store
    }
}
}
</script>
  