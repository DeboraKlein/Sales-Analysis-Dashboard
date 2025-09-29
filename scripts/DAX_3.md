## DAX Formulas Page 3

### Lost revenue
````
  Lost revenue = SUMX(
    'fDevoluções',
    'fDevoluções'[Returns quantity]*RELATED(dProdutos[Preço Unitario]
    ))

````
### % Lost revenue
````
% lost revenue = [Lost revenue]/[Total Revenue]

````
### % Returns
````
% Returns = [Total Returns]/[Sold Quantity]


