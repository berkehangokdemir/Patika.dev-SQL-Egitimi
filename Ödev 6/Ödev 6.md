# [Patika.dev](https://www.patika.dev/tr) - SQL Eğitimi
## Ödev 6
## Sorular

Merhabalar,

Aşağıdaki sorgu senaryolarını **dvdrental** örnek veri tabanı üzerinden gerçekleştiriniz.

1. **film** tablosunda bulunan **rental_rate** sütunundaki değerlerin ortalaması nedir?
2. **film** tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?
3. **film** tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?
4. **film** tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

Kolay Gelsin.

## Cevaplar

### Cevap (1)

```sql
SELECT ROUND(AVG(rental_rate), 2) FROM film;
```
- **Cevap** : **film** tablosunda bulunan **rental_rate** sütunundaki değerlerin ortalaması "**2.98**" çıkmaktadır.

### Cevap (2)

```sql
SELECT COUNT(title) FROM film
WHERE title LIKE 'C%';
```
- **Cevap** : **film** tablosunda bulunan filmlerden "**92**" tanesi 'C' karakteri ile başlamaktadır.

### Cevap (3)

```sql
SELECT MAX (length) FROM film
WHERE rental_rate = 0.99;
```
- **Cevap** : **film** tablosunda bulunan filmlerden rental_rate değeri 0.99'a eşit olan en uzun(length) film "**184**" dakikadır.

### Cevap (4)

```sql
SELECT COUNT (DISTINCT (replacement_cost)) FROM film
WHERE length > 150;
```
- **Cevap** : **film** tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait "**21**" adet farklı replacement_cost değeri vardır.