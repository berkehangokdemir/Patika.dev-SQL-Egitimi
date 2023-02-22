# [Patika.dev](https://www.patika.dev/tr) - SQL Eğitimi
## Ödev 8
## Sorular

Merhabalar,

1. **test** veritabanınızda **employee** isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.
2. Oluşturduğumuz **employee** tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.
3. Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
4. Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.

Kolay Gelsin.

## Cevaplar

### Cevap (1)

- **İlk Aşama** : pgAdmin4 çalıştır --> Servers --> PostgreSQL 15 --> Databases --> Create --> Database --> Database ismi (test) --> Save
- **İkinci Aşama** : **test** veritabanı oluşturuldu.
- **Üçüncü Aşama** : **test** veritabanının query tool'unu açarak işlem girmeye başlayabiliriz.

```sql
CREATE TABLE employee (
	id INTEGER,
 	name VARCHAR(50),
 	birthday DATE,
 	email VARCHAR(100)
);
```

### Cevap (2)
- **İlk aşama** : 'Mockaroo' servisi üzerinden veri oluşturma:
![Mockaroo](https://images2.imgbox.com/fd/e4/EPbEbiLH_o.jpg)
- **İkinci aşama** : Oluşturulan veriyi kopyalayıp ekleme, Örnek kod:
```sql
INSERT INTO employee (id, name, birthday, email)
VALUES (15, 'Orin Field', '2022-04-19', 'ofield0@newyorker.com');
```

### Cevap (3)
- **Update 1** -- *id'ye göre*
```sql
UPDATE employee
SET name = 'Quentin Tarantino',
	birthday = '1963-03-27',
	email = 'quentin@tarantino.com'
WHERE id = 3
RETURNING *;
```
- **Update 2** -- *id'ye göre*
```sql
UPDATE employee
SET name = 'Mark Cuban',
	birthday = '1958-07-31',
	email = 'mark@cuban.com'
WHERE id = 11
RETURNING *;
```
- **Update 3** -- *name'e göre*
```sql
UPDATE employee
SET name = 'Christian Bale',
	birthday = '1974-01-30',
	email = 'christian@bale.com'
WHERE name = 'Demott Rossoni'
RETURNING *;
```
- **Update 4** -- *email'e göre*
```sql
UPDATE employee
SET name = 'Christopher Nolan',
	birthday = '1970-07-30',
	email = 'christopher@nolan.com'
WHERE email = 'smenhenitt3@amazon.co.uk'
RETURNING *;
```
- **Update 5** -- *birthday'e göre*
```sql
UPDATE employee
SET name = 'Luka Doncic',
	birthday = '1999-02-28',
	email = 'luka@doncic.com'
WHERE birthday = '2022-05-20'
RETURNING *;
```

### Cevap (4)
- **Delete 1** -- *id'ye göre*
```sql
DELETE FROM employee
WHERE id = 78;
```
- **Delete 2** -- *name'e göre*
```sql
DELETE FROM employee
WHERE name = 'Tanner Van Hove';
```
- **Delete 3** -- *birthday'e göre*
```sql
DELETE FROM employee
WHERE birthday = '2023-01-06';
```
- **Delete 4** -- *email'e göre*
```sql
DELETE FROM employee
WHERE email = 'bnewlove9@nbcnews.com';
```
- **Delete 5** -- *id'ye göre*
```sql
DELETE FROM employee
WHERE id = 5;
```