#PREPARING DATA IN SQL
#mencari jumlah total bags, tons, dan pounds
SELECT  SUM(bags) AS Total_Bags, SUM(metric_tons) AS Total_Tons, SUM(Pounds) AS Total_Pounds
FROM `data-surya-390505.datasuryauhuy.data_coffee`

#mencari 10 data teratas
SELECT *
FROM `data-surya-390505.datasuryauhuy.data_coffee`
ORDER BY Pounds DESC
LIMIT 10

#Total metric tons top 5 negara
SELECT SUM(metric_tons) AS Total_Top_5
FROM (
  SELECT metric_tons
  FROM `data-surya-390505.datasuryauhuy.data_coffee`
  WHERE metric_tons IS NOT NULL
  ORDER BY metric_tons DESC
  LIMIT 5
) subquery

#persen dari 5 negara teratas terhadap seluruh export coffee
SELECT Top_5 / Total AS Ratio
FROM (
  SELECT
    (SELECT SUM(metric_tons) AS Top_5
    FROM (
      SELECT metric_tons
      FROM `data-surya-390505.datasuryauhuy.data_coffee`
      WHERE metric_tons IS NOT NULL
      ORDER BY metric_tons DESC
      LIMIT 5
    )) AS Top_5,
    (SELECT SUM(metric_tons) AS Total
    FROM `data-surya-390505.datasuryauhuy.data_coffee`
    WHERE metric_tons IS NOT NULL) AS Total
)
