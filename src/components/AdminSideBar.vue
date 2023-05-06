<template>
    <div class="d-flex flex-column flex-shrink-0 p-3 bg-light" style="width: 180px; min-height: 90vh;">
            <ul class="nav nav-pills flex-column mb-auto">
            <li class="nav-item">
                <a href="/dashboard" class="nav-link active" aria-current="page">
                    Home
                </a>
            </li>
            <li>
                <a href="#" class="nav-link link-dark">
                Dashboard
                </a>
            </li>
            <li>
                <a href="#" class="nav-link link-dark">
                Orders
                </a>
            </li>
            <li>
                <a href="#" class="nav-link link-dark">
                Products
                </a>
            </li>
            <li>
                <a href="#" class="nav-link link-dark">
                Customers
                </a>
            </li>
            <li>
                <a href="#" class="nav-link link-dark">
                Products
                </a>
            </li>
            <li>
                <a href="#" class="nav-link link-dark">
                Customers
                </a>
            </li>
            <li>
                <a href="#" class="nav-link link-dark">
                Products
                </a>
            </li>
            <li>
                <a href="#" class="nav-link link-dark">
                Customers
                </a>
            </li>
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
export default {
    name: 'AdminSidebar',
    methods: {
        logout: function() {
            sessionStorage.clear()
        }
    }
}
</script>