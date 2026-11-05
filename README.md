# Parâmetro D em Espirometria de Vida Real (CPAC)

Repositório com a metodologia e scripts relacionados à extração e análise do **Parâmetro D** a partir de laudos PDF de espirometria do Centro de Pneumologia e Alergia do Ceará (CPAC).

## Conteúdo

- `parametroD_extracao_metodologia.py` — Documentação de alto nível da metodologia de extração das curvas volume–tempo e cálculo do Parâmetro D.

## Metodologia resumida

1. Extração de curvas volume–tempo de PDFs (dois tipos: PDFCreator e Amyuni) com `pdfplumber`.
2. Processamento: segmento expiratório, remoção dos primeiros ~50 mL, reamostragem.
3. Ajuste do modelo biexponencial:

   ```
   V(t) = A * exp(B * t) + C * exp(D * t)
   ```

4. Controle de qualidade (exclusão de extremos e restrição FET ≥ 6 s para VEF1/VEF6).

## Referências principais

- Bhatt et al. Sci Rep. 2018
- Bhatt et al. Ann Am Thorac Soc. 2023

---

Autor: Fernando Luiz Cavalcanti Lundgren
