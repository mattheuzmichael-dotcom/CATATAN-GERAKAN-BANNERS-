<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CATATAN GERAKAN BANNERS</title>

<style>
body {
  font-family: Arial, sans-serif;
  background: #0f0f0f;
  color: white;
  margin: 0;
  padding: 20px;
}

h1 {
  text-align: center;
  margin-bottom: 25px;
  font-size: 20px;
  letter-spacing: 1px;
}

.container {
  max-width: 500px;
  margin: auto;
}

input, textarea {
  width: 100%;
  padding: 14px;
  margin-bottom: 10px;
  border-radius: 12px;
  border: 1px solid #222;
  background: #1a1a1a;
  color: white;
  font-size: 14px;
  outline: none;
}

input:focus, textarea:focus {
  border-color: #00ff88;
}

button {
  width: 100%;
  padding: 14px;
  border-radius: 12px;
  border: none;
  background: #00ff88;
  font-weight: bold;
  cursor: pointer;
  margin-bottom: 20px;
}

.note {
  background: #1a1a1a;
  padding: 15px;
  border-radius: 14px;
  margin-bottom: 12px;
}

.note h3 {
  margin: 0 0 5px 0;
  font-size: 16px;
}

.note p {
  margin: 0 0 10px 0;
  font-size: 14px;
  color: #ccc;
}

.delete-btn {
  background: #ff3b3b;
  padding: 6px 10px;
  font-size: 12px;
  border-radius: 8px;
  width: auto;
}
</style>
</head>

<body>

<div class="container">
  <h1>CATATAN GERAKAN BANNERS</h1>

  <input type="text" id="judul" placeholder="JUDUL">
  <textarea id="isi" rows="3" placeholder="NAMA GERAKAN"></textarea>
  <button onclick="tambahCatatan()">TAMBAH</button>

  <div id="daftarCatatan"></div>
</div>

<script>
let notes = JSON.parse(localStorage.getItem("notes")) || [];

function tampilkanCatatan() {
  const container = document.getElementById("daftarCatatan");
  container.innerHTML = "";

  notes.slice().reverse().forEach((note, index) => {
    const div = document.createElement("div");
    div.className = "note";
    div.innerHTML = `
      <h3>${note.judul}</h3>
      <p>${note.isi}</p>
      <button class="delete-btn" onclick="hapusCatatan(${notes.length - 1 - index})">Hapus</button>
    `;
    container.appendChild(div);
  });
}

function tambahCatatan() {
  const judul = document.getElementById("judul").value.trim();
  const isi = document.getElementById("isi").value.trim();

  if (!judul || !isi) return;

  notes.push({ judul, isi });
  localStorage.setItem("notes", JSON.stringify(notes));

  document.getElementById("judul").value = "";
  document.getElementById("isi").value = "";

  tampilkanCatatan();
}

function hapusCatatan(index) {
  notes.splice(index, 1);
  localStorage.setItem("notes", JSON.stringify(notes));
  tampilkanCatatan();
}

tampilkanCatatan();
</script>

</body>
</html>
