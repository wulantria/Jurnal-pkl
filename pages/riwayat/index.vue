<template>
  <div class="riwayat-container">
    <h2>Riwayat Pengisian Catatan Jurnal PKL</h2>
    <table border="1">
      <thead>
        <tr>
          <th>No</th>
          <th>Hari/Tanggal</th>
          <th>Uraian Kegiatan</th>
          <th>Verifikasi Guru</th>
          <th>Catatan Instruktur</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(entry, index) in riwayat" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ entry.Tanggal }}</td>
          <td>{{ entry.Uraian_Kegiatan }}</td>
          <td>{{ entry.Verifikasi_Guru }}</td>
          <td>{{ entry.Catatan_Instruktur }}</td>
        </tr>
      </tbody>
    </table>
    <button @click="printTable" class="print-button">Print</button>
  </div>
</template>

<script setup>
const pb = usePocketBaseClient();

const riwayat = await pb.collection('riwayat').getFullList()

</script>

<style scoped>
.riwayat-container {
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
  max-width: 1000px;
  margin: 20px auto;
}

h2 {
  margin-bottom: 20px;
}

.detail-container {
  margin-bottom: 20px;
  background: #fff;
  padding: 10px;
  border-radius: 5px;
  box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.1);
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 30px;
}

th, td {
  padding: 12px;
  text-align: left;
  border: 1px solid #ddd;
}

.print-button {
  margin-top: 20px;
  padding: 10px 15px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.print-button:hover {
  background-color: #0056b3;
}
</style>
