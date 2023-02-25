# [Patika.dev](https://www.patika.dev/tr) - SQL Eğitimi
## Ödev 12
## Sorular

Merhabalar,

Aşağıdaki sorgu senaryolarını **dvdrental** örnek veri tabanı üzerinden gerçekleştiriniz.

1. **film** tablosunda film uzunluğu **length** sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?
2. **film** tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?
3. **film** tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.
4. **payment** tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.

Kolay Gelsin.

## Cevaplar

### Cevap (1)

```sql
SELECT COUNT(length) FROM film
WHERE length >
(
	SELECT AVG(length) FROM film
);
```
- **film** tablosunda, uzunluğu ortalama film uzunluğundan fazla **489** film vardır.

### Cevap (2)

```sql
SELECT COUNT(rental_rate) FROM film
WHERE rental_rate =
(
	SELECT MAX(rental_rate) FROM film
);
```
- **film** tablosunda en yüksek rental_rate değerine sahip **336** film vardır.

### Cevap (3)

```sql
SELECT title, rental_rate, replacement_cost FROM film
WHERE rental_rate =
(
	SELECT MIN(rental_rate) FROM film
)
AND replacement_cost =
(
	SELECT MIN(replacement_cost) FROM film
);
```

### Cevap (4)

```sql
SELECT payment.customer_id,
CONCAT(customer.first_name, ' ', customer.last_name) AS customer,
COUNT(payment.customer_id) AS purchase_count FROM customer
INNER JOIN payment ON customer.customer_id = payment.customer_id
GROUP BY payment.customer_id, customer
ORDER BY purchase_count DESC;
```