# souve. studio — calculadora de preço

calculadora de preço de venda para os objetos autorais impressos em 3d da souve studio.
página única em html, css e javascript puro, sem build e sem dependências (só google fonts).

## o que ela calcula

```
custo direto  = (gramas / 1000 × preço do filamento/kg)
              + (horas × consumo kWh/h × preço kWh)
              + (horas × desgaste da máquina/h)
              + embalagem
              + (minutos de acabamento / 60 × mão de obra/h)

custo total   = custo direto × (1 + taxa de falha)
preço final   = custo total × markup (3x, 4x ou 5x)
margem bruta  = preço final − custo total
```

os parâmetros de produção e o markup escolhido ficam salvos no navegador
(`localStorage`, chave `souve-calc-params`). os dados do produto não são salvos.

## usar localmente

abra o `index.html` direto no navegador. não precisa instalar nada.

## publicar no github pages

1. crie um repositório no github chamado `souve-calculadora-preco`
2. faça push do `index.html` (e deste readme) para a branch `main`
   ```
   git init
   git add .
   git commit -m "calculadora de preço souve"
   git branch -M main
   git remote add origin https://github.com/anavrodovalho/souve-calculadora-preco.git
   git push -u origin main
   ```
3. no repositório: **settings → pages → source: deploy from a branch → `main` / `(root)`**
4. em um ou dois minutos a página fica em
   https://anavrodovalho.github.io/souve-calculadora-preco/

> no plano gratuito o github pages exige repositório público, então os parâmetros
> padrão (custos e markups) ficam visíveis para quem abrir o código.
