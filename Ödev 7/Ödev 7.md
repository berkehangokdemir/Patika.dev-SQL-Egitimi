# [Patika.dev](https://www.patika.dev/tr) - SQL Eğitimi
## Ödev 7
## Sorular

Merhabalar,

Aşağıdaki sorgu senaryolarını **dvdrental** örnek veri tabanı üzerinden gerçekleştiriniz.

1. **film** tablosunda bulunan filmleri **rating** değerlerine göre gruplayınız.
2. **film** tablosunda bulunan filmleri **replacement_cost** sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.
3. **customer** tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir? 
4. **city** tablosunda bulunan şehir verilerini **country_id** sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.

Kolay Gelsin.

## Cevaplar

### Cevap (1)

```sql
SELECT rating FROM film
GROUP BY rating;
```

### Cevap (2)

```sql
SELECT replacement_cost, COUNT(*) FROM film
GROUP BY replacement_cost
HAVING COUNT(*) > 50;
```

### Cevap (3)

```sql
SELECT store_id, COUNT(*) FROM customer
GROUP BY store_id;
```
- **Cevap** : **customer** tablosunda bulunan **store_id (1)**'e karşılık gelen müşteri sayısı "**326**", **store_id (2)**'e karşılık gelen müşteri sayısı "**273**" olarak çıkmaktadır.

### Cevap (4)

```sql
SELECT country_id, COUNT(*) FROM city
GROUP BY country_id
ORDER BY COUNT(*) DESC
LIMIT 1;
```
- **Cevap** : **city** tablosunda bulunan şehir verilerini **country_id** sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id "**44**" çıkmakta ve bu country_id'nin şehir sayısı "**60**" çıkmaktadır.