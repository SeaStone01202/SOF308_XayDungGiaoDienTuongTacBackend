<script setup>
    import 'bootstrap/dist/css/bootstrap.css';
    import 'bootstrap/dist/js/bootstrap.bundle';


    import Header from '../components/header.vue';
    import Footer from '../components/footer.vue';

    // Hàm xem trước ảnh đại diện
    function previewImage(event) {
            const reader = new FileReader();
            reader.onload = function() {
                const output = document.getElementById('profilePreview');
                output.src = reader.result;
            };
            reader.readAsDataURL(event.target.files[0]);
        }
</script>

<template>
    <div>
        <Header></Header>

        <main class="content-background d-flex justify-content-center align-items-center">
        <div class="container">
            <div class="row justify-content-center">
                <div class="col-md-8 col-lg-6">
                    <div class="card shadow-lg">
                        <div class="card-body p-5">
                            <h3 class="text-center mb-4">Chỉnh Sửa Thông Tin</h3>
                            <form enctype="multipart/form-data">
                                <!-- Hình ảnh đại diện -->
                                <div class="text-center mb-4">
                                    <img src="https://via.placeholder.com/150" alt="Profile Image" class="profile-img mb-3" id="profilePreview">
                                    <input type="file" class="form-control" id="profileImage" accept="image/*" onchange="previewImage(event)">
                                </div>
                                <!-- Fullname -->
                                <div class="mb-3">
                                    <label for="fullname" class="form-label">Họ và Tên:</label>
                                    <input type="text" class="form-control" id="fullname" value="Nguyễn Văn A" required>
                                </div>
                                <!-- Email -->
                                <div class="mb-3">
                                    <label for="email" class="form-label">Email:</label>
                                    <input type="email" class="form-control" id="email" value="email@example.com" required>
                                </div>
                                <!-- Password -->
                                <div class="mb-3">
                                    <label for="password" class="form-label">Mật khẩu:</label>
                                    <input type="password" class="form-control" id="password" placeholder="Nhập mật khẩu mới" required>
                                </div>
                                <!-- Nút cập nhật -->
                                <button type="submit" class="btn btn-primary w-100">Cập Nhật</button>
                            </form>
                            <hr class="my-4">
                            <p class="text-center"><a href="profile.html" class="text-decoration-none">Quay lại trang cá nhân</a></p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <Footer></Footer>
    </div>
</template>