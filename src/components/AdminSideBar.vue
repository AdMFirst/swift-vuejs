<template>
    <div class="d-flex flex-column flex-shrink-0 p-3 bg-light" style="width: 180px; min-height: 90vh;">
            <ul class="nav nav-pills flex-column mb-auto">
                <li :class="{ 'active': store.activeTab === 'tab1' }" @click="store.activeTab = 'tab1'" class="nav-link link-dark">Tab 1</li>
                <li :class="{ 'active': store.activeTab === 'tab2' }" @click="store.activeTab = 'tab2'" class="nav-link link-dark">Tab 2</li>
                <li :class="{ 'active': store.activeTab === 'tab3' }" @click="store.activeTab = 'tab3'" class="nav-link link-dark">Tab 3</li>

            </ul>
            <hr>
            <div class="dropdown">
            <a href="#" class="d-flex align-items-center text-decoration-none dropdown-toggle link-dark text-truncate" id="dropdownUser1" data-bs-toggle="dropdown" aria-expanded="false">
                <img src="https://github.com/mdo.png" alt="" width="32" height="32" class="rounded-circle me-2">
                <strong>Abecede </strong>
            </a>
            <ul class="dropdown-menu dropdown-menu-light text-small shadow " aria-labelledby="dropdownUser1">
                <li><a class="dropdown-item" href="#">New project...</a></li>
                <li><a class="dropdown-item" href="#">Settings</a></li>
                <li><a class="dropdown-item" href="#">Profile</a></li>
                <li><hr class="dropdown-divider"></li>
                <li><a class="dropdown-item" href="/" @click="logout">Sign out</a></li>
            </ul>
            </div>
        </div>
</template>

<script>
import { store } from './store';


export default {
    name: 'AdminSidebar',
    data () {
        return {
            store
        }
    },
    methods: {
        logout: function() {
            sessionStorage.clear()
        }
    }
}
</script>