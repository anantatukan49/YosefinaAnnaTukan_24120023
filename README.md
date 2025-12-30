
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Data Nilai Mahasiswa</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #e6e6e6;
        }

        /* HEADER ATAS */
        .header {
            background: #e0e0e0;
            padding: 15px 30px;
            font-size: 14px;
        }

        .header b {
            display: block;
        }

        /* JUDUL */
        .judul {
            padding: 30px;
        }

        .judul h1 {
            margin: 0;
            font-size: 36px;
            color: #666;
            font-weight: normal;
        }

        .judul p {
            margin-top: 15px;
            font-size: 14px;
        }

        /* CONTAINER UTAMA */
        .container {
            display: flex;
            gap: 30px;
            padding: 0 30px 40px 30px;
        }

        /* BOX */
        .box {
            background: #e4ecd2;
            width: 50%;
            padding: 20px;
            border: 1px solid #999;
        }

        .box h3 {
            text-align: center;
            margin: 0;
            padding-bottom: 10px;
            border-bottom: 1px solid #aaa;
        }

        /* FORM */
        label {
            display: inline-block;
            width: 130px;
            margin: 10px 0;
        }

        input {
            width: 220px;
            padding: 5px;
        }

        .btn {
            margin-top: 15px;
        }

        button {
            padding: 5px 15px;
            margin-right: 5px;
        }

        .note {
            margin-top: 15px;
            font-size: 12px;
        }

        /* OUTPUT */
        .output p {
            margin: 12px 0;
        }
    </style>
</head>

<body>

    <!-- HEADER -->
    <div class="header">
        <b>Nama : Yosefina Anna Maria Tukan</b>
        <b>NPM : 24120023</b>
    </div>

    <!-- JUDUL -->
    <div class="judul">
        <p>
            <b>Nama :</b> Yosefina Anna Maria Tukan <br>
            <b>NPM :</b> 24120023
        </p>
    </div>

    <!-- KONTEN -->
    <div class="container">

        <!-- INPUT -->
        <div class="box">
            <h3>DATA NILAI MAHASISWA</h3>

            <label>Masukan NIM</label>
            <input type="text" id="nim"><br>

            <label>Nama Mahasiswa</label>
            <input type="text" id="nama"><br>

            <label>Nilai UTS</label>
            <input type="number" id="uts"><br>

            <label>Nilai UAS</label>
            <input type="number" id="uas"><br>

            <label>Nilai Tugas</label>
            <input type="number" id="tugas"><br>

            <div class="btn">
                <button onclick="proses()">Proses</button>
                <button onclick="batal()">Batal</button>
            </div>

            <div class="note">
                UTS 30% | UAS 40% | TUGAS 30% <br>
                85–100 = A | 70–84 = B | 60–69 = C | 40–59 = D | &lt;40 = E
            </div>
        </div>

        <!-- OUTPUT -->
        <div class="box output">
            <h3>DATA NILAI MAHASISWA</h3>

            <p><b>NIM :</b> <span id="o_nim"></span></p>
            <p><b>Nama Mahasiswa :</b> <span id="o_nama"></span></p>
            <p><b>Nilai UTS :</b> <span id="o_uts"></span></p>
            <p><b>Nilai UAS :</b> <span id="o_uas"></span></p>
            <p><b>Nilai Tugas :</b> <span id="o_tugas"></span></p>
            <p><b>Index :</b> <span id="o_index"></span></p>
        </div>

    </div>

    <!-- SCRIPT -->
    <script>
        function proses() {
            let nim = document.getElementById("nim").value;
            let nama = document.getElementById("nama").value;
            let uts = parseFloat(document.getElementById("uts").value);
            let uas = parseFloat(document.getElementById("uas").value);
            let tugas = parseFloat(document.getElementById("tugas").value);

            let nilaiAkhir = (uts * 0.3) + (uas * 0.4) + (tugas * 0.3);
            let index = "";

            if (nilaiAkhir >= 85) index = "A";
            else if (nilaiAkhir >= 70) index = "B";
            else if (nilaiAkhir >= 60) index = "C";
            else if (nilaiAkhir >= 40) index = "D";
            else index = "E";

            document.getElementById("o_nim").innerText = nim;
            document.getElementById("o_nama").innerText = nama;
            document.getElementById("o_uts").innerText = uts;
            document.getElementById("o_uas").innerText = uas;
            document.getElementById("o_tugas").innerText = tugas;
            document.getElementById("o_index").innerText = index;
        }

        function batal() {
            document.querySelectorAll("input").forEach(i => i.value = "");
            document.querySelectorAll("span").forEach(s => s.innerText = "");
        }
    </script>

</body>
</html>
