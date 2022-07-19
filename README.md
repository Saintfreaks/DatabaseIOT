# Tabeldatabarang

<!doctype html>
<html>
    <head>
        <title> Data Barang Museum Lampung</title>
        <style>
        body{
                background-color: aquamarine; 
                Margin-bottom;20px;
            }
        </style>
    </head>
    <body>
        <h1> Data Barang Museum Lampung </h1>
        <button style="background-color : red; margin-bottom: 40px; "><a href="form_tambah.php">Tambah</a></button>
        <table border="5">
            <tr>
                <th>No</th>
                <th>Id_barang</th>
                <th>Date</th>
                <th>Nama_barang</th>
                <th>Deskripsi_barang</th>
                <th>Tempat_barang</th>
                <th>Aksi</th>
                
            </tr>
            <?php
                include"koneksi.php";

                $no= 1;
                $data = mysqli_query($koneksi,"SELECT * FROM `tabel data barang`");
                while  ($hasil= mysqli_fetch_array ($data)) {
                    ?>
                <tr>
                    <td><?php echo $no++; ?></td>
                    <td><?php echo $hasil['Id_barang']; ?></td>
                    <td><?php echo $hasil['Date']; ?></td>
                    <td><?php echo $hasil['Nama_barang']; ?></td>
                    <td><?php echo $hasil['Deskripsi_barang']; ?></td>
                    <td><?php echo $hasil['Tempat_barang']; ?></td>
                    <td>
                       <a href="">ubah </a> 
                       <a href="">hapus </a> 
                    </td>
                </tr>
                <?php
                }
            ?>
        </table>
    </body>
</html>
