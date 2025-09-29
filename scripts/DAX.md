
## Total Revenue
````
  Total Revenue = SUMX(
    fVendas,
    fVendas[Quantity sold]*RELATED(dProdutos[Preço Unitario])
)

---

````
% Crescimento YoY
````
% Crescimento YoY = 
VAR vFat_ano_anterior = CALCULATE(
    [Total Revenue],
    DATEADD(dCalendario[Dates],-12,MONTH)
    )
VAR vCrescimento = DIVIDE(
    [Total Revenue]-vFat_ano_anterior,
    vFat_ano_anterior)
RETURN
IF(HASONEVALUE(
    dCalendario[Ano])&&vCrescimento<>BLANK(),
    vCrescimento,
    "N/A"
)
