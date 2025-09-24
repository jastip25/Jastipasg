<!DOCTYPE html>  <html lang="id">  
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>Formulir Pesanan Jasa Titip</title>  
  <style>  
    body {  
      font-family: Arial, sans-serif;  
      background-color: #f4f4f4;  
      display: flex;  
      justify-content: center;  
      align-items: center;  
      height: 100vh;  
      margin: 0;  
    }  
    .container {  
      background-color: #fff;  
      padding: 30px;  
      border-radius: 8px;  
      box-shadow: 0 0 10px rgba(0,0,0,0.1);  
      width: 100%;  
      max-width: 500px;  
    }  
    h2 {  
      text-align: center;  
      margin-bottom: 20px;  
      color: #333;  
    }  
    label {  
      display: block;  
      margin-bottom: 8px;  
      font-weight: bold;  
      color: #555;  
    }  
    input, textarea, select {  
      width: 100%;  
      padding: 10px;  
      margin-bottom: 15px;  
      border: 1px solid #ccc;  
      border-radius: 4px;  
      box-sizing: border-box;  
    }  
    button {  
      width: 100%;  
      padding: 12px;  
      background-color: #007bff;  
      color: white;  
      border: none;  
      border-radius: 4px;  
      cursor: pointer;  
      font-size: 16px;  
    }  
    button:hover {  
      background-color: #0056b3;  
    }  
    @media (max-width: 600px) {  
      .container {  
        padding: 20px;  
      }  
      h2 {  
        font-size: 20px;  
      }  
    }  
  </style>  
</head>  
<body>  <div class="container">  
  <h2>Formulir Pesanan</h2>  
  <form id="orderForm">  
    <label for="nama">Nama Lengkap:</label>  
    <input type="text" id="nama" name="nama" required>  <label for="whatsapp">Nomor WhatsApp:</label>  
<input type="tel" id="whatsapp" name="whatsapp" pattern="[0-9]{10,15}" placeholder="Contoh: 08123456789" required>  

<label for="email">Email:</label>  
<input type="email" id="email" name="email">  

<label for="alamat">Alamat Pengiriman:</label>  
<textarea id="alamat" name="alamat" rows="3" required></textarea>  

<label for="barang">Nama Barang yang Dipesan:</label>  
<input type="text" id="barang" name="barang" required>  

<label for="catatan">Catatan Tambahan:</label>  
<textarea id="catatan" name="catatan" rows="3"></textarea>  

<label for="metode">Kirim Pesanan via:</label>  
<select id="metode" name="metode" required>  
  <option value="">-- Pilih Metode --</option>  
  <option value="wa">WhatsApp</option>  
  <option value="email">Email</option>  
</select>  

<button type="submit">Kirim Pesanan</button>

  </form>  
</div>  <script>  
  document.getElementById("orderForm").addEventListener("submit", function(e) {  
    e.preventDefault();  
    const nama = document.getElementById("nama").value;  
    const whatsapp = document.getElementById("whatsapp").value;  
    const email = document.getElementById("email").value;  
    const alamat = document.getElementById("alamat").value;  
    const barang = document.getElementById("barang").value;  
    const catatan = document.getElementById("catatan").value;  
    const metode = document.getElementById("metode").value;  
  
    const message = `Halo, saya ingin memesan:\n\n` +  
                    `👤 Nama: ${nama}\n` +  
                    `📱 WhatsApp: ${whatsapp}\n` +  
                    `✉️ Email: ${email}\n` +  
                    `📍 Alamat: ${alamat}\n` +  
                    `📦 Barang: ${barang}\n` +  
                    `📝 Catatan: ${catatan}`;  
  
    if (metode === "wa") {  
      // Nomor WhatsApp admin (ubah sesuai nomor kamu)  
      const adminNumber = "6281273222144";   
      const url = `https://wa.me/${adminNumber}?text=${encodeURIComponent(message)}`;  
      window.open(url, "_blank");  
    }   
    else if (metode === "email") {  
      // Email tujuan (ubah sesuai email kamu)  
      const emailTujuan = "adiexsotis@gmail.com";   
      const subject = "Pesanan Baru Jasa Titip";  
      const body = message.replace(/\n/g, "%0D%0A");  
      const mailtoUrl = `mailto:${emailTujuan}?subject=${encodeURIComponent(subject)}&body=${body}`;  
      window.location.href = mailtoUrl;  
    }   
    else {  
      alert("Silakan pilih metode pengiriman.");  
    }  
  });  
</script>  </body>  
</html>
