# Planeja+ — Planejador Financeiro Pessoal

Ferramenta estática (HTML puro, sem backend) para planejamento financeiro pessoal.

## Funcionalidades
- Dashboard com receita, gastos, sobra mensal e taxa de poupança
- Diagnóstico automático de categorias de gasto acima do ideal
- Cadastro de despesas fixas e variáveis
- Simulador de investimentos (CDB % do CDI vs Poupança) com projeção mês a mês
- Sugestões de alocação de recursos por perfil de risco
- Dados salvos no localStorage do navegador (não há servidor nem banco de dados)

## Deploy na Vercel

### Opção 1 — Vercel CLI
```bash
npm i -g vercel
cd planeja-financas
vercel --prod
```

### Opção 2 — Painel da Vercel
1. Crie um repositório no GitHub e suba esta pasta (index.html + vercel.json).
2. Em vercel.com, clique em "Add New Project" e importe o repositório.
3. Não é preciso configurar build command nem framework — é um site estático puro. Clique em Deploy.

### Opção 3 — Arrastar e soltar
Em vercel.com, você também pode arrastar a pasta diretamente na tela de novo projeto (drag & drop), sem precisar de Git.

## Personalização rápida
- Categorias de gasto e seus % ideais: variável `CATEGORIES` no `<script>` do index.html
- Sugestões de alocação por perfil: variável `ALLOCATIONS`
- Cores e fontes: bloco `:root { ... }` no `<style>`
