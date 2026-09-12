[README (2).md](https://github.com/user-attachments/files/32147514/README.2.md)
# Planeja+ — Planejador Financeiro Pessoal

Ferramenta estática (HTML puro, sem backend) para planejamento financeiro pessoal.

## Estrutura de arquivos
```
planeja-financas/
  index.html      <- a ferramenta inteira (HTML + CSS + JS)
  libs/           <- Chart.js e jsPDF empacotados localmente (sem depender de CDN externo)
    chart.umd.js
    jspdf.umd.min.js
    jspdf.plugin.autotable.min.js
  vercel.json
  README.md
```
Mantenha a pasta `libs/` sempre junto do `index.html` — os caminhos são relativos (`./libs/...`).

## Funcionalidades
- **Como usar**: primeiro módulo do menu, com passo a passo de como usar a ferramenta
- **Dashboard**: receita, gastos, sobra mensal, taxa de poupança e diagnóstico automático por categoria
- **Despesas**: cadastro de gastos fixos/variáveis, um por vez (Enter também adiciona)
- **Investimentos**: fluxo por objetivo (reserva, viagem, carro, casa, estudos, patrimônio ou um objetivo com nome próprio) — a pessoa só informa quanto tem, quanto guarda por mês e opcionalmente uma meta de valor; o app calcula sozinho quando ela chega lá, investindo vs. deixando parado. Taxas técnicas ficam escondidas atrás de "Ajustar taxas manualmente (opcional)"
- **Sugestões**: reserva de emergência ideal e alocação de recursos por perfil de risco
- **Exportação**:
  - **Planilha (.csv)**: abre no Excel/Google Sheets, com resumo, despesas, diagnóstico, simulação e alocação
  - **PDF profissional**: relatório com capa, gráficos (custos por categoria, projeção do objetivo, alocação sugerida), tabelas e rodapé com paginação — tudo gerado no navegador da pessoa, sem enviar dados a nenhum servidor
- Dados salvos no localStorage do navegador (não há servidor nem banco de dados)

## Deploy na Vercel

### Opção 1 — Vercel CLI
```bash
npm i -g vercel
cd planeja-financas
vercel --prod
```

### Opção 2 — Painel da Vercel
1. Suba esta pasta inteira (index.html + libs/ + vercel.json) para um repositório no GitHub.
2. Em vercel.com, "Add New Project" e importe o repositório.
3. Não precisa configurar build nem framework — é site estático puro. Clique em Deploy.

### Opção 3 — Arrastar e soltar
Em vercel.com, arraste a pasta inteira (com a subpasta `libs/`) na tela de novo projeto.

## Personalização rápida
- Objetivos de investimento (ícone, nome, taxa e prazo padrão): variável `OBJECTIVES` no `<script>`
- Categorias de gasto e seus % ideais: variável `CATEGORIES`
- Sugestões de alocação por perfil: variável `ALLOCATIONS`
- Cores e fontes: bloco `:root { ... }` no `<style>`
