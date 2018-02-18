CREATE TABLE departemen (
idDepartemen INTEGER NOT NULL PRIMARY KEY,
namaDepartemen TEXT NOT NULL);

INSERT INTO departemen VALUES (1,'Dep. MDSI');
INSERT INTO departemen VALUES (2,'Dep. PPTI');
INSERT INTO departemen VALUES (3,'Dep. MSK');
INSERT INTO departemen VALUES (4,'Dep. DIKLAT');
INSERT INTO departemen VALUES (5,'Dep. PAM');

CREATE TABLE karyawan (
nik INTEGER NOT NULL PRIMARY KEY,
idDepartemen INTEGER NOT NULL,
namaDepan TEXT NOT NULL,
namaBelakang TEXT NOT NULL,
jenisKelamin TEXT NOT NULL,
email TEXT NOT NULL,
phoneNumber TEXT NOT NULL,
jabatan TEXT NOT NULL,
FOREIGN KEY(idDepartemen) REFERENCES departemen(idDepartemen));

INSERT INTO karyawan VALUES (05606,1,'Eki','Fakhrureza','L','ekifakhrureza@gmail.com','087874957002','SAP ABAP');
INSERT INTO karyawan VALUES (05777,1,'Agung','Prabowo','L','agungp@gmail.com','08234242422','SAP BASIS');
INSERT INTO karyawan VALUES (05888,3,'Ahmad','Yusuf','L','yusuf@gmail.com','0856023232','Network Engineer');
INSERT INTO karyawan VALUES (05444,2,'Putra','Janitra','L','putra@gmail.com','08133399888','Web Programmer');
INSERT INTO karyawan VALUES (05119,4,'Fitri','Ramadhani','P','fitri@gmail.com','0813377447','Ahli Madya Diklat');


CREATE TABLE proyek (
idProyek INTEGER NOT NULL PRIMARY KEY,
nama TEXT NOT NULL,
nilai TEXT NOT NULL,
dueDate TEXT NOT NULL,
status TEXT NOT NULL,
keterangan TEXT);

INSERT INTO proyek VALUES (1,'EIS','200000000','2018-06-10','ON PROGRESS','Semangat');
INSERT INTO proyek VALUES (2,'HRIS','100000000','2017-12-12','DONE','Selamat');
INSERT INTO proyek VALUES (3,'Cuti Online Mobile App','150000000','2018-10-15','ON PROGRESS','Caiyo');
INSERT INTO proyek VALUES (4,'Koperasi Apps','125000000','2018-07-06','ON PROGRESS','Ganbatte');
INSERT INTO proyek VALUES (5,'SPPD Mobile Apps','225000000','2018-12-09','ON PROGRESS','Fokus');

CREATE TABLE proyekKaryawan(
idProyekKaryawan INTEGER NOT NULL PRIMARY KEY,
nik INTEGER NOT NULL,
idProyek INTEGER NOT NULL,
FOREIGN KEY(nik) REFERENCES karyawan(nik),
FOREIGN KEY(idProyek) REFERENCES proyek(idProyek));

INSERT INTO proyekKaryawan VALUES(1,05606,1);
INSERT INTO proyekKaryawan VALUES(2,05606,2);
INSERT INTO proyekKaryawan VALUES(3,05777,2);
INSERT INTO proyekKaryawan VALUES(4,05444,3);
INSERT INTO proyekKaryawan VALUES(5,05888,4);
