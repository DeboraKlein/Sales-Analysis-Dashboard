## DAX Formulas Page 2

### Best Product
````
Best Product = 
CALCULATE(
    MAX(dProdutos[Name Product]),
    TOPN(1,ALL(dProdutos[Name Product]),[Sold Quantity])
)

````
### Sales Best Products
````
 sales Best Products = [Qt Best Products]/[Sold Quantity]

````
### Best Store
````
Best Store = 
CALCULATE(
    MAX(dLojas[Nome da Loja]),
    TOPN(1,ALL(dLojas[Nome da Loja]),[Sold Quantity])
)

````
### % sales Best Store
````
% sales Best Store = [Qt Best Store]/[Sold Quantity]

````
### % growth MoM
````
% growth MoM = DIVIDE([Total Revenue]-[Faturamento Mês Anterior],[Faturamento Mês Anterior],"Sem Histórico")

````
### Choose Analysis 2
````
Choose Analysis 2 = {
    ("Total Revenue", NAMEOF('Medidas'[Total Revenue]), 0),
    ("Qt Sold", NAMEOF('Medidas'[Sold Quantity]), 1)
}

````
### Choose analysis
````
Choose analysis = {
    ("Total Revenue", NAMEOF('Medidas'[Total Revenue]), 0),
    ("Qt Sold", NAMEOF('Medidas'[Sold Quantity]), 1)
}
