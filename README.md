<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CATATAN GERAKAN BANNERS</title>

<style>
body {
    font-family: Arial, sans-serif;
    background: #121212;
    color: #ffffff;
    margin: 0;
    padding: 15px;
}

h1 {
    text-align: center;
    margin-bottom: 20px;
    letter-spacing: 1px;
}

.container {
    max-width: 600px;
    margin: auto;
}

input, textarea {
    width: 100%;
    padding: 14px;
    margin: 8px 0;
    border-radius: 12px;
    border: 1px solid #333;
    background: #1e1e1e;
    color: white;
    font-size: 14px;
    outline: none;
}

input:focus, textarea:focus {
    border: 1px solid #00c3ff;
}

button {
    width: 100%;
    padding: 14px;
    border: none;
    border-radius: 12px;
    background: linear-gradient(45deg, #00c3ff, #007bff);
    color: white;
    font-weight: bold;
    cursor: pointer;
    margin-top: 5px;
    transition: 0.3s;
}

button:active {
    transform: scale(0.98);
}

.note {
    background: #1e1e1e;
    padding: 15px;
    margin-top: 15px;
    border-radius: 15px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.4);
    animation: fadeIn 0.3s ease-in-out;
}

.note h3 {
    margin: 0 0 6px 0;
    color: #00c3ff;
}

.note p {
    margin: 0;
    color: #ccc;
}

@keyframes fadeIn {
    from {opacity: 0; transform: translateY(10px);}
    to {opacity: 1; transform: translateY(0);}
}
</style>
</head>

<body>

<div class="container">
<h1>CATATAN GERAKAN BANNERS</h1>

<input type="text" id="judul" placeholder="JUDUL">
<textarea id="isi" rows="4" placeholder="NAMA GERAKAN"></textarea>
<button onclick="tambahCatatan()">Tambah Catatan</button>

<div id="daftarCatatan"></div>
</div>

<script>
function tambahCatatan() {
    const judul = document.getElementById("judul").value.trim();
    const isi = document.getElementById("isi").value.trim();

    if (!judul || !isi) {
        alert("Harap isi semua kolom!");
        return;
    }

    const tanggal = new Date().toLocaleString("id-ID");

    const note = document.createElement("div");
    note.className = "note";

    note.innerHTML = `
        <h3>${judul}</h3>
        <small style="color:#777;">${tanggal}</small>
        <p>${isi}</p>
    `;

    document.getElementById("daftarCatatan").prepend(note);

    document.getElementById("judul").value = "";
    document.getElementById("isi").value = "";
}
</script>

</body>
</html>
