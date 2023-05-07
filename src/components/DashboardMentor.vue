<template>
    <div class="overflow-auto">
        <div v-if="store.activeTab === 'tab1'" class="container flex-grow">
            <div class="row">
                <div class="col">
                    <h1>yes and no</h1>
                    <img src="../assets/background_3.png"/>
                </div>
            </div>
        </div>
        <div v-if="store.activeTab === 'tab2'">
            Content for tab 2
        </div>
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

<style>
.maxContainer {
    max-width: 70vw;
}
</style>
  