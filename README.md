# PROJECT-FILE-MANAGEMENT-SERVER
MEMANEJEMEN FILE DIREKTORI 3 DEPARTEMEN
### 1. Membuat Struktur Direktori
***Buat folder untuk 3 departemen (Marketing, Engineering, HR) dengan
subfolder Documents dan Archives di masing-masing***
```
mkdir -p Marketing/Documents Marketing/Archives
mkdir -p Engineering/Documents Engineering/Archives
mkdir -p HR/Documents HR/Archives
```
### 2. Pindahkan dan salin file
***Pindahkan file yang salah tempat ke direktori yang benar***
```
mv proposal.pdf Marketing/Documents/
mv data.txt Marketing/Documents/

mv proposal.pdf Engineering/Documents/
mv data.txt Engineering/Documents/

mv proposal.pdf HR/Documents/
mv data.txt HR/Documents/
```
***buat backup di
folder Archives***
```
cp proposal.pdf Marketing/Archives/
cp data.txt Marketing/Archives/

cp proposal.pdf Engineering/Archives/
cp data.txt Engineering/Archives/

cp proposal.pdf HR/Archives/
cp data.txt HR/Archives/
```
### 3. Atur permission 
***Set permission yang tepat agar hanya departemen terkait yang bisa mengakses folder mereka***
tambah user departemen terkait terlrbih dahulu jika belum punya contoh:
```
sudo adduser admin-marketing
sudo adduser admin-enginer
sudo adduser admin-hr
```
```
sudo chown -R admin-marketing Marketing/
sudo chown -R admin-enginer Engineering/
sudo chown -R admin-hr Hr/
```
```
sudo chmod -R 700 Marketing/
sudo chmod -R 700 Engineering/
sudo chmod -R 700 HR/
```
### 4. Cari dan filter
***Temukan semua file PDF yang dibuat minggu lalu dan buat daftar
lengkapnya***
```
find -type f -name "*.pdf" -mtime -7 > daftarlengkap-pdf.txt
```
