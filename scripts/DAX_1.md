## DAX Formulas Page 1
### Total Revenue
````
  Total Revenue = SUMX(
    fVendas,
    fVendas[Quantity sold]*RELATED(dProdutos[Preço Unitario])
)

````
### % Crescimento YoY
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

````
### Total Profit
````
Total Profit = SUMX(
    fVendas,
    (fVendas[Quantity sold]*RELATED(dProdutos[Preço Unitario]))*0.9-
    fVendas[Quantity sold]*RELATED(dProdutos[Custo Unitario])
)

````
### % Crescimento Lucro YoY
````

% Crescimento Lucro YoY = 
VAR vLucro_ano_anterior = CALCULATE(
    [Total Profit],
    DATEADD(dCalendario[Dates],-12,MONTH)
    )
VAR vCrescimento = DIVIDE(
    [Total Profit]-vLucro_ano_anterior,
    vLucro_ano_anterior)
    RETURN
IF(HASONEVALUE(
    dCalendario[Ano])&&vCrescimento<>BLANK(),
    vCrescimento,
    "N/A"
)

````
### Sold Quantity
````
Sold Quantity = SUM(fVendas[Quantity sold])

````
### % Crescimento Vendas YoY
````
% Crescimento Vendas YoY = 
VAR vVendas_Ano_Anterior = CALCULATE(
    [Sold Quantity],
    DATEADD(dCalendario[Dates],-12,MONTH)
    )
VAR vCrescimento = DIVIDE(
    [Sold Quantity]-vVendas_Ano_Anterior,
    vVendas_Ano_Anterior)
    RETURN
IF(HASONEVALUE(
    dCalendario[Ano])&&vCrescimento<>BLANK(),
    vCrescimento,
    "N/A"
)

````
### % Margem de Lucro
````
% Margem de Lucro = [Total Profit]/[Total Revenue]

````
### Total Revenue
````
Total Revenue = SUMX(
    fVendas,
    fVendas[Quantity sold]*RELATED(dProdutos[Preço Unitario])
)

````
### Revenue LY
````
Revenue LY = 
VAR vRevenue_LY = 
    CALCULATE([Total Revenue],
    DATEADD(
    dCalendario[Dates],
    -1,YEAR
    ))
RETURN
    IF(HASONEVALUE(
    dCalendario[Ano]),
    vRevenue_LY
    )
