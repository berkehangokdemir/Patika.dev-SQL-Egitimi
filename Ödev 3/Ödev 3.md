# [Patika.dev](https://www.patika.dev/tr) - SQL Eğitimi
## Ödev 3
## Sorular

Merhabalar,

Aşağıdaki sorgu senaryolarını **dvdrental** örnek veri tabanı üzerinden gerçekleştiriniz.

1. **country** tablosunda bulunan **country** sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.
2. **country** tablosunda bulunan **country** sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.
3. **film** tablosunda bulunan **title** sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.
4. **film** tablosunda bulunan tüm sütunlardaki verilerden **title** 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

Kolay Gelsin.

## Cevaplar

### Cevap (1)

```sql
SELECT country FROM country
WHERE country LIKE 'A%a';
```

### Cevap (2)

```sql
SELECT country FROM country
WHERE country LIKE '%_____n';
```

### Cevap (3)

```sql
SELECT title FROM film
WHERE title ILIKE '%t%t%t%t%';
```

### Cevap (4)

```sql
SELECT * FROM film
WHERE title LIKE 'C%'
AND length > 90
AND rental_rate = 2.99;
```
