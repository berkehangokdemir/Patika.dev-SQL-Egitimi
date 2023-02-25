# [Patika.dev](https://www.patika.dev/tr) - SQL Eğitimi
## Ödev 10
## Sorular

Merhabalar,


Aşağıdaki sorgu senaryolarını **dvdrental** örnek veri tabanı üzerinden gerçekleştiriniz.

1. **city** tablosu ile **country** tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.
2. **customer** tablosu ile **payment** tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.
3. **customer** tablosu ile **rental** tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.

Kolay Gelsin.

## Cevaplar

### Cevap (1)

- **Seçenek 1** - **First Table** : city
```sql
SELECT city.city, country.country FROM city
LEFT JOIN country ON city.country_id = country.country_id;
```
- **Seçenek 2** - **First Table** : country
```sql
SELECT city.city, country.country FROM country
LEFT JOIN city ON city.country_id = country.country_id;
```


### Cevap (2)
- **Seçenek 1** - **Second Table** : payment
```sql
SELECT payment.payment_id, customer.first_name, customer.last_name
FROM customer
RIGHT JOIN payment ON customer.customer_id = payment.customer_id;
```
- **Seçenek 2** - **Second Table** : customer
```sql
SELECT payment.payment_id, customer.first_name, customer.last_name
FROM payment
RIGHT JOIN customer ON customer.customer_id = payment.customer_id;
```

### Cevap (3)
```sql
SELECT rental.rental_id, customer.first_name, customer.last_name
FROM rental
FULL JOIN customer ON rental.customer_id = customer.customer_id;
```
