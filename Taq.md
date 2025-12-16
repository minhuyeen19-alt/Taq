<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Lớp DH26BT</title>
<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #f4f6f8;
}
header {
    background: #1e3a5f;
    color: white;
    padding: 25px;
    text-align: center;
}
nav {
    background: #2c4c73;
    display: flex;
    justify-content: center;
}
nav a {
    color: white;
    padding: 14px 20px;
    text-decoration: none;
}
nav a:hover {
    background: #1e3a5f;
}
section {
    padding: 30px;
}
.card {
    background: white;
    padding: 15px;
    margin: 10px 0;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
button {
    padding: 8px 12px;
    margin: 5px 0;
    cursor: pointer;
}
footer {
    background: #1e3a5f;
    color: white;
    text-align: center;
    padding: 10px;
}
.admin {
    display: none;
    margin-top: 10px;
}
textarea {
    width: 100%;
    height: 80px;
}
</style>
</head>
<body>

<header>
    <h1>LỚP DH26BT</h1>
    <p>Đoàn kết – Năng động – Thành công</p>
    <button onclick="login()">🔐 Đăng nhập Admin</button>
</header>

<nav>
    <a href="#gioithieu">Giới thiệu</a>
    <a href="#thongbao">Thông báo</a>
    <a href="#hoatdong">Hoạt động</a>
</nav>

<section id="gioithieu">
    <h2>📘 Giới thiệu lớp</h2>
    <div class="card" contenteditable="false" id="intro">
        Lớp DH26BT – Khoa/Trường … <br>
        Sĩ số: … sinh viên
    </div>
</section>

<section id="thongbao">
    <h2>📢 Thông báo</h2>
    <div class="card" id="notice">
        Chưa có thông báo mới.
    </div>

    <div class="admin">
        <textarea id="newNotice" placeholder="Nhập thông báo mới..."></textarea>
        <button onclick="addNotice()">➕ Cập nhật thông báo</button>
    </div>
</section>

<section id="hoatdong">
    <h2>🎉 Hoạt động lớp</h2>
    <div class="card" contenteditable="false" id="activity">
        Sinh hoạt lớp, hoạt động ngoại khóa, tình nguyện...
    </div>
</section>

<footer>
    © 2025 – Website lớp DH26BT
</footer>

<script>
const password = "19082007";

function login() {
    const pass = prompt("Nhập mật khẩu admin:");
    if (pass === password) {
        alert("Đăng nhập admin thành công!");
        document.querySelectorAll(".admin").forEach(el => el.style.display = "block");
        document.getElementById("intro").contentEditable = true;
        document.getElementById("activity").contentEditable = true;
        localStorage.setItem("admin", "true");
    } else {
        alert("Sai mật khẩu!");
    }
}

function addNotice() {
    const text = document.getElementById("newNotice").value;
    if (text.trim() !== "") {
        document.getElementById("notice").innerHTML = text;
        document.getElementById("newNotice").value = "";
    }
}

// giữ trạng thái admin
if (localStorage.getItem("admin") === "true") {
    document.querySelectorAll(".admin").forEach(el => el.style.display = "block");
    document.getElementById("intro").contentEditable = true;
    document.getElementById("activity").contentEditable = true;
}
</script>

</body>
</html>
