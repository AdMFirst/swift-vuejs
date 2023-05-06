<template>
    <div class="container-fluid">
        <div class="row d-flex justify-content-center align-items-center m-4">
            <div class="col-12 col-md-8 col-lg-6 col-xl-5 ">
                <div class="card bg-primary text-white" style="border-radius: 1rem;">
                    <div class="card-body p-4 text-center d-flex flex-column justify-content-around" style="min-height: 80vh;">

                        
                        <h5 class="text-white-50">Masukan Email atau ID Karyawan beserta password anda!</h5>

                        <div class="form-outline form-white">
                            <input type="text" id="typeEmailX" class="form-control form-control-lg" />
                            <label class="form-label" for="typeEmailX">Email/ID Karyawan</label>
                        </div>

                        <div class="form-outline form-white">
                            <input type="password" id="typePasswordX" class="form-control form-control-lg" />
                            <label class="form-label" for="typePasswordX">Password</label>
                        </div>

                        <button class="btn btn-outline-light btn-lg px-5" type="submit">Login</button>
                        <div class="row">
                            <div class="col-md-5 p-0">
                                <a href="#" class="text-white">Belum punya akun?</a>
                            </div>
                            <div class="col-md-2">
                                <p>•</p>
                            </div>
                            <div class="col-md-5 p-0">
                                <a href="#" class="text-white">Lupa password?</a>
                            </div>
                        </div>
                    

                    </div>
                </div>
            </div>
        </div>
    </div>

</template>