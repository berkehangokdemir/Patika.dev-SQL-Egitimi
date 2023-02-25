# [Patika.dev](https://www.patika.dev/tr) - SQL Eğitimi
## Ödev 11
## Sorular

Merhabalar,

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1. **actor** ve **customer** tablolarında bulunan **first_name** sütunları için tüm verileri sıralayalım.
2. **actor** ve **customer** tablolarında bulunan **first_name** sütunları için kesişen verileri sıralayalım.
3. **actor** ve **customer** tablolarında bulunan **first_name** sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.
4. İlk 3 sorguyu tekrar eden veriler için de yapalım.

Kolay Gelsin.

## Cevaplar

### Cevap (1)

```sql
(SELECT first_name FROM actor)
UNION
(SELECT first_name FROM customer);
```

### Cevap (2)

```sql
(SELECT first_name FROM actor)
INTERSECT
(SELECT first_name FROM customer);
```

### Cevap (3)

```sql
(SELECT first_name FROM actor)
EXCEPT
(SELECT first_name FROM customer);
```

### Cevap (4)
----
- **1.Sorgu** *(Tekrar eden veriler ile birlikte)*
```sql
(SELECT first_name FROM actor)
UNION ALL
(SELECT first_name FROM customer);
```

----
- **2.Sorgu** *(Tekrar eden veriler ile birlikte)*
```sql
(SELECT first_name FROM actor)
INTERSECT ALL
(SELECT first_name FROM customer);
```
- **INTERSECT ALL** bize **INTERSECT** ile aynı sonucu verecektir çünkü iki tablo içerisinde bulunan **kesişen** verileri bizlere getirecektir.

----
- **3.Sorgu** *(Tekrar eden veriler ile birlikte)*
```sql
(SELECT first_name FROM actor)
EXCEPT ALL
(SELECT first_name FROM customer);
```
- **EXCEPT ALL** bize ilk tabloda tekrar eden verilerle birlikte daha fazla satır sunacaktır.
----