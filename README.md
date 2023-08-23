# PEMBELAJARAN_SQL_BISNIS
BASIC SQL

# KUNCI JAWABAN QUERY
1. SELECT
  id,
  email
FROM
  `project-tilda-396813.ecommerce.customer`
WHERE
  gender= 'Female'
  AND city='Depok'
2.SELECT
  customer_id,
  SUM(total) AS total_Pembelanjaan
FROM
  `project-tilda-396813.ecommerce.Transaction`
GROUP BY
  1
ORDER BY 
  2 DESC
LIMIT
  10
   3. SELECT 
id AS product_id 
 FROM `project-tilda-396813.ecommerce.Product` 
 WHERE price< 10000
4. SELECT
  product_id,
  SUM(quantity) AS total_terjual
FROM
  `project-tilda-396813.ecommerce.Transaction`
GROUP BY
  1
ORDER BY
  2 DESC
LIMIT
  5. SELECT
  DATE_TRUNC(created_at,MONTH),
  COUNT(DISTINCT id) AS count_transaction,
  SUM(total) AS total_pendapatan,
  SUM(quantity) AS total_terjual
FROM
  `project-tilda-396813.ecommerce.Transaction`
GROUP BY
  1
ORDER BY
  1 ASC
6. SELECT
  DATE_TRUNC(created_at,MONTH),
  COUNT(DISTINCT id) AS count_transaction,
  SUM(total) AS total_pendapatan,
  SUM(quantity) AS total_terjual
FROM
  `project-tilda-396813.ecommerce.Transaction`
GROUP BY
  1
ORDER BY
  1 ASC
   7. SELECT
 type,
 COUNT(DISTINCT customer_id) AS jumlah_customer
FROM
 `project-tilda-396813.ecommerce.Transaction` AS a
LEFT JOIN
 `project-tilda-396813.ecommerce.Store`  AS b
ON
 a.store_id=b.id
GROUP BY
 1
HAVING
 SUM(total)>200000
ORDER BY
 2 DESC
