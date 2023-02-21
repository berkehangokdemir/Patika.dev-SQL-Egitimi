# [Patika.dev](https://www.patika.dev/tr) - SQL Eğitimi
## Ödev 5
## Sorular

Merhabalar,

Aşağıdaki sorgu senaryolarını **dvdrental** örnek veri tabanı üzerinden gerçekleştiriniz.

1. **film** tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.
2. **film** tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.
3. **customer** tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

Kolay Gelsin.

## Cevaplar

### Cevap (1)

```sql
SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5;
```

### Cevap (2)

```sql
SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length
LIMIT 5
OFFSET 5;
```

### Cevap (3)

```sql
SELECT last_name FROM customer
WHERE store_id = 1
ORDER BY last_name DESC
LIMIT 4;
```
