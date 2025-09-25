<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Formulir Konsumen Jastip ASG</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
    }
    .container {
      background: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      width: 100%;
      max-width: 480px;
    }
    h2 {
      text-align: center;
      margin-bottom: 20px;
      color: #333;
    }
    label {
      font-weight: bold;
      display: block;
      margin-top: 10px;
    }
    input, textarea, select {
      width: 100%;
      padding: 10px;
      margin-top: 6px;
      border: 1px solid #ccc;
      border-radius: 6px;
      box-sizing: border-box;
    }
    button {
      margin-top: 16px;
      width: 100%;
      padding: 12px;
      background: #007bff;
      color: white;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      font-size: 16px;
    }
    button:hover {
      background: #0056b3;
    }
    .terms {
      margin-top: 20px;
      font-size: 14px;
      color: #333;
    }
    .terms h3 {
      margin-bottom: 10px;
    }
    .terms ol {
      padding-left: 18px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Formulir Konsumen Jastip ASG</h2>
    <form id="orderForm">
      <label>Nama Lengkap:</label>
      <input type="text" id="nama" required>

      <label>Nomor WhatsApp:</label>
      <input type="text" id="whatsapp" placeholder="628xxxxxxxxxx" required>

      <label>Alamat Rumah:</label>
      <textarea id="alamat" rows="3" required></textarea>

      <label>E-commerce yang digunakan:</label>
      <textarea id="ecomers" rows="2"></textarea>

      <label>Pertanyaan Tambahan:</label>
      <select id="pertanyaan" required>
        <option value="">-- Pilih --</option>
        <option value="Apakah bisa COD?">Apakah bisa COD?</option>
        <option value="Berapa lama estimasi pengiriman?">Berapa lama estimasi pengiriman?</option>
        <option value="Apakah ada batas jumlah barang?">Apakah ada batas jumlah barang?</option>
      </select>

      <div class="terms">
        <h3>Syarat & Ketentuan</h3>
        <ol>
          <li>Barang tidak dapat diretur atau ditolak dengan alasan apapun.</li>
          <li>Ketidaksesuaian barang adalah tanggung jawab pembeli dan penjual. Kami hanya sebagai penyedia layanan (jastip).</li>
          <li>Biaya jasa per paket normal Rp10.000. Barang besar/kargo: Rp15.000–Rp500.000 tergantung ukuran/berat.</li>
          <li>Dilarang menyebarkan alamat kami tanpa izin.</li>
          <li>Barang COD wajib dibayar lunas. Tidak menerima cicilan, tempo, atau hutang.</li>
          <li>Kami tidak bertanggung jawab atas kerusakan/hilangnya barang selama pengiriman.</li>
        </ol>
        <label>
          <input type="checkbox" id="setuju" required>
          Saya sudah membaca dan menyetujui syarat & ketentuan
        </label>
      </div>

      <button type="submit">Kirim Pesanan</button>
    </form>
  </div>

  <script>
    document.getElementById("orderForm").addEventListener("submit", function(e){
      e.preventDefault();

      const nama = document.getElementById("nama").value;
      const whatsapp = document.getElementById("whatsapp").value;
      const alamat = document.getElementById("alamat").value;
      const ecomers = document.getElementById("ecomers").value;
      const pertanyaan = document.getElementById("pertanyaan").value;

      const message =
        `Halo, saya ingin bergabung di Jastip ASG:%0A` +
        `👤 Nama: ${nama}%0A` +
        `📱 WhatsApp: ${whatsapp}%0A` +
        `🏠 Alamat Rumah: ${alamat}%0A` +
        `🛒 E-commerce: ${ecomers}%0A` +
        `❓ Pertanyaan: ${pertanyaan}`;

      const adminNumber = "6281273222144"; // Ganti dengan nomor admin kamu
      const url = `https://wa.me/${adminNumber}?text=${message}`;
      window.open(url, "_blank");
    });
  </script>
</body>
</html>
