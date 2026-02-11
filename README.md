# 🏴 CATATAN GERAKAN BANNERS

Web sederhana untuk mencatat dan menyimpan daftar gerakan BANNERS secara online.

## 🚀 Live Website
🔗 https://mattheuzmichael-dotcom.github.io/CATATAN-GERAKAN-BANNERS/

---

## ✨ Fitur

- ✅ Tambah catatan
- ✅ Simpan otomatis (localStorage)
- ✅ Hapus catatan
- ✅ Tampilan dark mode
- ✅ Mobile friendly
- ✅ Catatan terbaru tampil paling atas

---

## 🛠 Teknologi

- HTML
- CSS
- JavaScript
- GitHub Pages (untuk hosting)

---

## 📱 Tampilan

Web ini didesain khusus mobile-first agar nyaman digunakan di Android maupun iPhone.

---

## 📌 Cara Pakai

1. Isi bagian **JUDUL**
2. Isi bagian **NAMA GERAKAN**
3. Tekan tombol **TAMBAH**
4. Catatan akan otomatis tersimpan

---

## 👨‍💻 Developer

Dibuat oleh:  
**Michael Gaztone**

---

🔥 Project ini dibuat sebagai latihan belajar coding & pengembangan web.
  document.getElementById("judul").value = "";
  document.getElementById("isi").value = "";

  render();
}

function hapus(index) {
  data.splice(index, 1);
  localStorage.setItem("banners", JSON.stringify(data));
  render();
}

render();
</script>

</body>
</html>    div.innerHTML = `
      <h3>${item.judul}</h3>
      <p>${item.isi}</p>
      <button onclick="hapus(${data.length - 1 - index})">Hapus</button>
    `;
    list.appendChild(div);
  });
}

function tambahCatatan() {
  const judul = document.getElementById("judul").value.trim();
  const isi = document.getElementById("isi").value.trim();

  if (!judul || !isi) return;

  data.push({ judul, isi });
  localStorage.setItem("banners", JSON.stringify(data));

  document.getElementById("judul").value = "";
  document.getElementById("isi").value = "";

  render();
}

function hapus(index) {
  data.splice(index, 1);
  localStorage.setItem("banners", JSON.stringify(data));
  render();
}

render();
</script>

</body>
</html>
