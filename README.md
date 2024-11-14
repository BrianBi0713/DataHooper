SELECT 
p1.Tm,
ROUND(avg(p1.`FG%`),2) as AVG_FG_23_24,
ROUND(avg(p2.`FG%`),2) as AVG_FG_22_23,
ROUND(avg(p1.`FG%`) - avg(p2.`FG%`),2) as FG_percent_change
FROM NBA_Regular_Stats_2023_2024.NBA_Regular_2324 p1
JOIN
NBA_Regular_Stats_22_23.NBA_Regular_2223 p2 
ON 
p1.Tm = p2.Tm
GROUP BY p1.Tm
ORDER BY FG_percent_change DESC;
