# 🚨 Adoption Day — Reports

```sql
SELECT d.name, d.breed, d.fee, d.campus AS written_campus
FROM dogs d LEFT JOIN shelters s ON d.campus = s.campus
WHERE s.campus IS NULL
```
{: .query source="dogs,shelters" #invisible }

[Invisible dogs](#)
{: .datagrid source="invisible" #lost_dogs height="200" title="🚨 Invisible to every family — adoption income: $0" }

```sql
SELECT s.campus, COUNT(d.name) AS visible_dogs, SUM(d.fee) AS adoption_income
FROM shelters s LEFT JOIN dogs d ON d.campus = s.campus
GROUP BY s.campus
```
{: .query source="dogs,shelters" #by_campus }

[Adoption income by campus](#)
{: .chart #chart source="by_campus" type="bar" x="campus" y="adoption_income" height="240" }

```sql
SELECT status, SUM(fee) AS income FROM (
  SELECT CASE WHEN s.campus IS NULL THEN 'At risk' ELSE 'Funded' END AS status,
         d.fee AS fee
  FROM dogs d LEFT JOIN shelters s ON d.campus = s.campus
) x GROUP BY status
```
{: .query source="dogs,shelters" #income_split }

[The missing money](#)
{: .chart #money_pie source="income_split" type="pie" x="status" y="income" height="240" }
