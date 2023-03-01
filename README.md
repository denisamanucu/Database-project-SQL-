# Database-project-SQL-3. CREATE TABLE CU RESTRICTIILE DE INTEGRITATE AFERENTE
CREATE TABLE client
(id_client NUMBER(2) CONSTRAINT PKey_client PRIMARY KEY,
nume VARCHAR2(30) NOT NULL,
prenume VARCHAR2(30) NOT NULL,
cnp VARCHAR2(13) NOT NULL,
adresa VARCHAR2(50) NOT NULL,
telefon VARCHAR(10));
CREATE TABLE angajat
(id_angajat NUMBER(3) CONSTRAINT PKey_angajat PRIMARY KEY,
nume VARCHAR2(50) NOT NULL,
prenume VARCHAR2(50) NOT NULL,
cnp VARCHAR2(13) NOT NULL,
salariu NUMBER(4) NOT NULL,
data_ang DATE NOT NULL,
functie VARCHAR2(50));
CREATE TABLE camera
(id_camera NUMBER(2) CONSTRAINT PKey_camera PRIMARY KEY,
etaj NUMBER(2) NOT NULL,
tip_camera VARCHAR2(10) NOT NULL,
pret_noapte NUMBER(4) NOT NULL);
CREATE TABLE factura
(id_factura NUMBER(4) CONSTRAINT PKey_factura PRIMARY KEY,
valoare NUMBER(7) NOT NULL,
id_client NUMBER(2) NOT NULL,
CONSTRAINT FKey_client_factura FOREIGN KEY (id_client) REFERENCES client(id_client),
id_angajat NUMBER(3) NOT NULL,
CONSTRAINT FKey_angajat_factura FOREIGN KEY (id_angajat) REFERENCES angajat(id_angajat),
data_factura DATE NOT NULL);
CREATE TABLE perioada_inchiriere
(id_perioada NUMBER(3) CONSTRAINT PKey_perioada_inchiriere PRIMARY KEY,
data_inceperii DATE NOT NULL,
nr_nopti NUMBER(2) NOT NULL,
id_client NUMBER(2),
CONSTRAINT FKey_client_perioada FOREIGN KEY (id_client) REFERENCES client(id_client),
id_camera NUMBER(2),
CONSTRAINT FKey_camera_perioada FOREIGN KEY (id_camera) REFERENCES camera(id_camera));
4. Actualizarea structurii tabelelor si modificarea 
restrictiilor de integritate 
 Adaugarea unei coloane noi in tabela client (coloana adresa de email)
 Modificarea tipului de data a coloanei etaj
 Adaugarea unei restrictii in tabela angajat
 Dezactivarea restrictiei adaugate anterior
 Stergerea restrictiei adaugate anterior
 Stergere coloana adresa_de_email din tabela client
 Modificarea numelui tabelei client in vizitator
5.Adăugarea (min 10, max 15) de înregistrări în fiecare tabelă 
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('555','Patrascu','Radu','500070207591','2300',TO_DATE('15-05-2020','dd-mm-yyyy'),'Receptionist');
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('899','Mares','Andreea','699052407591','3700',TO_DATE('15-11-2018','dd-mm-yyyy'),'Bucatar');
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('333','Remetea','Narcisa','670022003495','3000',TO_DATE('01-03-2019', 'dd-mm-yyyy'),'Camerista');
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('442','Bojoga','Mihai','599052407591','3200',TO_DATE('15-11-2018', 'dd-mm-yyyy'),'Ajutor de 
bucatar_1');
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('443','Popescu','Andrei','598752407591','3200',TO_DATE('16-11-2019', 'dd-mm-yyyy'),'Ajutor de 
bucatar_2');
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('444','Busuioc','Mihai','58765407591','3200',TO_DATE('15-11-2018', 'dd-mm-yyyy'),'Ajutor de 
bucatar_3');
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('445','Oprea','Paul','599059807591','3200',TO_DATE('15-11-2017', 'dd-mm-yyyy'),'Ajutor de bucatar_4');
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('222','Alexandru','Catalina','599562407591','3000',TO_DATE('15-11-2013', 'dd-mm-yyyy'),'Femeie de 
serviciu');
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('556','Chirila','Daniel','599052788591','2300',TO_DATE('15-09-2018', 'dd-mm-yyyy'),'Receptionist_2');
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('777','Ursu','Roxana','598952407591','3500',TO_DATE('15-10-2018', 'dd-mm-yyyy'),'Contabil');
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('999','Apostol','Ana','599059808991','3200',TO_DATE('15-11-2017', 'dd-mm-yyyy'),'Marketing PR');
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie) VALUES 
('998','Mihnea','Mirela','599058907591','3200',TO_DATE('15-12-2018', 'dd-mm-yyyy'),'Marketing 
PR_2');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('82','Ionescu','Andrei','592052407291','Str.Malinului 5','0764456852');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('35','Popa','Ioana','698052412091','Str.Trandafirilor 32','0764478963');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('17','Diacon','Denis','5978941582367','Str.Miorita 118','0757841547');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('18','Popescu','Catalin','5898741582367','Bd Timisoara 79','0759901547');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('19','Florea','Robert','5998941589867','SBd Timisoara 80','075789997');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('20','Bogdan','Ciprian','50008941762367','Str Romancierilor 2A','0757841547');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('21','Pasicinic','Stefan','5008944532367','Aleea Campul cu Flori 118','0778965447');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('22','Grigorescu','ALexandru','5078941582367','Str Valea Oltului 78','0757849864');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('23','Ioan','Denis','5965756482367','Str.Fabrica de zahar 75','0757841888');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('25','Stoica','Horatiu','5098941587655','Aleea Dealul Macinului 118','0757834547');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('24','Petre','Denisa','5078741580098','Aleea Dealul Maccrisului 118','0757841987');
INSERT INTO client(id_client,nume,prenume,cnp,adresa,telefon) VALUES 
('26','Obregia','Geanina','50754415000','Str Sperantei','0765441547');
INSERT INTO camera(id_camera,etaj,tip_camera,pret_noapte) VALUES (01,0,'Double',350);
insert into camera(id_camera,etaj,tip_camera,pret_noapte) VALUES(02,0,'Single',280);
insert into camera(id_camera,etaj,tip_camera,pret_noapte) VALUES(03,0,'Double',350);
insert into camera(id_camera,etaj,tip_camera,pret_noapte) VALUES(04,1,'Double',350);
insert into camera(id_camera,etaj,tip_camera,pret_noapte) VALUES(05,1,'Single',280);
insert into camera(id_camera,etaj,tip_camera,pret_noapte) VALUES(06,1,'Double',350);
insert into camera(id_camera,etaj,tip_camera,pret_noapte) VALUES(07,2,'Triple',450);
insert into camera(id_camera,etaj,tip_camera,pret_noapte) VALUES(08,2,'Single',280);
insert into camera(id_camera,etaj,tip_camera,pret_noapte) VALUES(09,1,'Premium',550);
insert into camera(id_camera,etaj,tip_camera,pret_noapte) VALUES(10,2,'Single',280);
insert into camera(id_camera,etaj,tip_camera,pret_noapte) VALUES(11,0,'Premium',550);
insert into camera(id_camera,etaj,tip_camera,pret_noapte) VALUES(12,2,'Premium',550);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(564,TO_DATE('30.12.2023','dd.mm.yyyy'),5,35,01);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(789,TO_DATE('27.12.2023','dd.mm.yyyy'),2,17,05);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(566,TO_DATE('10.12.2023','dd.mm.yyyy'),14,82,02);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(987,TO_DATE('17.03.2023','dd.mm.yyyy'),2,18,03);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(000,TO_DATE('27.11.2023','dd.mm.yyyy'),7,19,04);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(569,TO_DATE('27.05.2023','dd.mm.yyyy'),9,20,06);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(749,TO_DATE('12.08.2023','dd.mm.yyyy'),10,21,07);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(729,TO_DATE('19.09.2023','dd.mm.yyyy'),2,22,08);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(719,TO_DATE('26.09.2023','dd.mm.yyyy'),6,23,09);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(799,TO_DATE('4.11.2023','dd.mm.yyyy'),12,24,10);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(389,TO_DATE('7.02.2023','dd.mm.yyyy'),2,25,11);
INSERT INTO perioada_inchiriere(id_perioada,data_inceperii,nr_nopti,id_client,id_camera) VALUES 
(399,TO_DATE('7.07.2023','dd.mm.yyyy'),5,26,12);
insert into factura(id_factura, valoare, id_client, data_factura) values ('000', '1750', 35, 
TO_DATE('5.01.2023','dd.mm.yyyy'));
insert into factura(id_factura, valoare, id_client, data_factura) values ('001', '560', 17, 
TO_DATE('27.12.2023','dd.mm.yyyy'));
insert into factura(id_factura, valoare, id_client, data_factura) values ('002', '3920', 82, 
TO_DATE('10.12.2023','dd.mm.yyyy'));
insert into factura(id_factura, valoare, id_client, data_factura) values ('003', '700', 18, 
TO_DATE('17.03.2023','dd.mm.yyyy'));
insert into factura(id_factura, valoare, id_client, data_factura) values ('004', '2450', 19, 
TO_DATE('27.11.2023','dd.mm.yyyy'));
insert into factura(id_factura, valoare, id_client, data_factura) values ('005', '3150', 20, 
TO_DATE('27.05.2023','dd.mm.yyyy'));
insert into factura(id_factura, valoare, id_client, data_factura) values ('006', '560', 22, 
TO_DATE('19.09.2023','dd.mm.yyyy'));
insert into factura(id_factura, valoare, id_client, data_factura) values ('007', '3360', 24, 
TO_DATE('4.11.2023','dd.mm.yyyy'));
insert into factura(id_factura, valoare, id_client, data_factura) values ('008', '4500', 21, 
TO_DATE('12.08.2023','dd.mm.yyyy'));
insert into factura(id_factura, valoare, id_client, data_factura) values ('009', '3300', 23, 
TO_DATE('5.01.2023','dd.mm.yyyy'));
insert into factura(id_factura, valoare, id_client, data_factura) values ('010', '1100', 25, 
TO_DATE('7.02.2023','dd.mm.yyyy'));
insert into factura(id_factura, valoare, id_client, data_factura) values ('011', '2750', 26, 
TO_DATE('7.07.2023','dd.mm.yyyy'));
1. Actualizarea inregistrarilor 
 Adaugarea a 200 de lei pentru angajatii cu salariul sub 3000
UPDATE angajat
SET salariu=salariu+200
WHERE salariu<3000;
SELECT * FROM angajat;
 Sa se modifice data facturii cu suma totala mai mica decat 800.

 Sa se actualizeze salariul daca angajatul are cnp-ul ‘500070207591’
 Sa se actualizeze pretul pe noapte al camerelor ‘single’ la 300
2. Stergerea si recuperarea unei tabele
8. Exemple de interogări variate (min 20) – inclunzând şi operatorii UNION, 
INTERSECT, MINUS, expresiile DECODE şi CASE, cereri imbricate, diverse 
funcţii single-row, functii de grup, structuri ierarhice, jonctiuni. 
1. Sa se selecteze id_angajat, prenume si functie al acelora al caror 
prenume incepe cu M
SELECT id_angajat,prenume, functie FROM angajat WHERE prenume LIKE '%M%';
2. Sa se selecteze angajatii care au salariul intre 2300 si 3100 de lei si a 
caror functie continue litera ‘r’
SELECT id_angajat, nume,prenume, salariu, functie FROM angajat WHERE salariu BETWEEN 2300 
AND 3100 AND functie LIKE '%r%';
3. Sa se selecteze clientii a caror adresa e corespondenta cu o strada
SELECT id_client,prenume,telefon FROM client WHERE adresa LIKE '%Str%';
4. Setare de perioada inchiriere in functie de id client
MERGE INTO perioada_inchiriere USING client 
ON (perioada_inchiriere.id_client = client.id_client)
WHEN MATCHED THEN 
UPDATE SET perioada_inchiriere.id_perioada=client.id_client
WHEN NOT MATCHED THEN
INSERT (id_client) VALUES (client.id_client);
COMMIT;
5. Selectare angajati cu salarii mai mici decat 4000 de lei care nu au 
functia de bucatari si ordonare descrescatoare dupa salariu
SELECT id_angajat,nume,prenume,salariu
FROM angajat
WHERE salariu < ANY
(SELECT salariu FROM angajat WHERE salariu <4000) 
AND functie <> 'Bucatar'
ORDER BY salariu DESC;
6. Selectare angajati care au salariul mai mare de 3000 si functia lor 
incepe cu litera ‘R’, ordonare crescatoare dupa salariu
SELECT id_angajat,functie, salariu
FROM angajat
WHERE salariu < ALL
(SELECT salariu FROM angajat WHERE salariu >=3000) 
AND functie like '%R%'
ORDER BY salariu ASC;
7. Selectare camere al corar tip incep cu litera ‘D’
SELECT camera.*, pi.* 
FROM camera, perioada_inchiriere pi
WHERE camera.id_camera=pi.id_camera
AND INITCAP(camera.tip_camera) LIKE '%D%';
3. Selectare informatii despre camerele si perioada inchirierii
SELECT c.id_camera, c.tip_camera,c.pret_noapte, pi.nr_nopti
FROM camera c, perioada_inchiriere pi
WHERE c.id_camera = pi.id_camera (+);
4. Selectare camere de tip ‘Double’
SELECT id_camera,etaj,tip_camera,pret_noapte FROM camera WHERE tip_camera='Double';
5. Selectare angajat cu salariu minim
SELECT*FROM angajat WHERE salariu=(SELECT MIN(salariu) FROM angajat);
6. Selectare nume si salariu angajat care are functia de bucatar
SELECT nume, prenume, salariu FROM angajat WHERE UPPER(functie)='BUCATAR';
12.Afisare tip de camera si pretul acestora
SELECT 'Camera ' || UPPER(tip_camera) || ' are pretul de ' || pret_noapte || ' lei/noapte.'
FROM camera;
13.Selectare data curenta
SELECT SYSDATE data_curenta FROM DUAL;
14.Adaugare comision pe venit
ALTER TABLE angajat
ADD comision NUMBER(2);
SELECT nume, salariu*12 + salariu*12*NVL(comision,0) venit_anual
FROM angajat;
15. Calcul total angajati
SELECT COUNT(id_angajat) total_angajati
FROM angajat
WHERE salariu>0; 
16.Calcul pret in functie de perioada si tipul de camera
SELECT c.id_camera, SUM(pi.nr_nopti * c.pret_noapte) total_perioada
FROM camera c, perioada_inchiriere pi
where pi.id_camera=c.id_camera
GROUP BY c.id_camera
ORDER BY total_perioada ASC;
17.Salariu minim si salariu maxim
SELECT MIN(salariu), MAX(salariu) FROM angajat;
18. Inserare manager
INSERT INTO angajat(id_angajat,nume,prenume,cnp,salariu,data_ang,functie,id_manager) VALUES 
(999,'Movila','Marius','579254861591','4000',TO_DATE('01-09-2019','dd-mm-yyyy'),'Manager',0);
UPDATE angajat
SET id_manager=999
WHERE id_manager IS NULL;
19. Selectare angajati care au salariul intre 2500 si 4500 fara cei care au 
salariul intre 2800 si 3000
SELECT * FROM angajat WHERE salariu BETWEEN 2500 AND 4500
MINUS 
SELECT *FROM angajat WHERE salariu IN(2800,3300);
20. Sa se afiseze angajatii care au id-ul 2,4,6 sau 8
select * from angajat
where id_angajat in(2,4,6,8);
21.Selectare manager
select id_angajat, nume, id_manager, functie from angajat 
connect by prior id_angajat=id_manager
start with nume='Movila'
order by functie;
 Gestiunea altor obiecte ale bazei de date: vederi, indecsi, sinonime, 
secvente.
 View
CREATE OR REPLACE VIEW v_angajat
AS SELECT*FROM angajat
WHERE salariu>1000;
 Index
SELECT *FROM client WHERE nume='Popa';
CREATE INDEX idx_prenume ON client(nume);
SELECT*FROM client WHERE nume='Popa';
 Secventa
CREATE SEQUENCE seq_camera
START WITH 01 INCREMENT BY 1
MAXVALUE 8 NOCYCLE;
INSERT INTO camera VALUES(seq_camera.NEXTVAL, 2,'Single',280);
SELECT seq_camera.CURRVAL FROM DUAL;
 Sinonim
create synonym angajat1 for angajat
