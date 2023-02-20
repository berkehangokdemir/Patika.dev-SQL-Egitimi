# [Patika.dev](https://www.patika.dev/tr) - SQL Eğitimi
## Ödev 4
## Sorular

Merhabalar,

Aşağıdaki sorgu senaryolarını **dvdrental** örnek veri tabanı üzerinden gerçekleştiriniz.

1. **film** tablosunda bulunan **replacement_cost** sütununda bulunan birbirinden farklı değerleri sıralayınız.
2. **film** tablosunda bulunan **replacement_cost** sütununda birbirinden farklı kaç tane veri vardır?
3. **film** tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?
4. **country** tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?
5. **city** tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?

Kolay Gelsin.

## Cevaplar

### Cevap (1)

```sql
SELECT DISTINCT replacement_cost FROM film;
```

### Cevap (2)

```sql
SELECT COUNT (DISTINCT replacement_cost) FROM film;
```
- **Cevap** : **film** tablosunda **replacement_cost** sütununda birbirinden farklı **21** adet veri vardır.

### Cevap (3)

```sql
SELECT COUNT (title) FROM film
WHERE title LIKE 'T%'
AND rating = 'G';
```
- **Cevap** : **film** tablosunda bulunan film isimlerinde (title) **9** tanesi 'T' karakteri ile başlar ve aynı zamanda 'G' rating'ine sahiptir.

### Cevap (4)

```sql
SELECT COUNT (country) FROM country
WHERE country LIKE '_____';
```
- **Cevap** : **country** tablosunda bulunan ülke isimlerinden **13** tanesi 5 karakterden oluşmaktadır.

### Cevap (5)

```sql
SELECT COUNT (city) FROM city
WHERE city ILIKE '%r';
```
- **Cevap** : **city** tablosundaki şehir isimlerinin **33** tanesi 'R' veya 'r' karakteri ile bitmektedir.
