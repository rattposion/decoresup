# Solução para Erro 404 - Roteamento

## Problema Identificado
Quando você atualiza as páginas ou acessa URLs diretamente, recebe erro 404 porque o servidor não sabe como lidar com as rotas do React Router.

## Soluções Implementadas

### 1. ✅ Arquivo vercel.json (para Vercel)
Criado arquivo `vercel.json` que redireciona todas as rotas para `index.html`

### 2. ✅ Arquivo _redirects (para Netlify)
Criado arquivo `public/_redirects` para servidores Netlify

### 3. ✅ Arquivo .htaccess (para Apache)
Criado arquivo `public/.htaccess` para servidores Apache

### 4. ✅ HashRouter (Alternativa)
Mudei de `BrowserRouter` para `HashRouter` no `App.tsx`

## Próximos Passos

### Para Vercel:
O arquivo `vercel.json` já está configurado. Faça o deploy normalmente.

### Para Netlify:
O arquivo `_redirects` já está configurado. Faça o deploy normalmente.

### Para Apache:
O arquivo `.htaccess` já está configurado. Faça o upload dos arquivos.

### Para desenvolvimento local:
```bash
npm run dev
```

## Diferença entre BrowserRouter e HashRouter

### BrowserRouter (anterior):
- URLs limpas: `/funcionarios`, `/equipamentos`
- Requer configuração do servidor
- Melhor para SEO

### HashRouter (atual):
- URLs com hash: `/#/funcionarios`, `/#/equipamentos`
- Funciona sem configuração do servidor
- Menos SEO-friendly

## Se quiser voltar para BrowserRouter:

1. Reverta as mudanças no `App.tsx`:
   ```tsx
   import { BrowserRouter, Routes, Route } from "react-router-dom";
   // ...
   <BrowserRouter>
   ```

2. Mantenha os arquivos de configuração do servidor:
   - `vercel.json`
   - `public/_redirects`
   - `public/.htaccess`

## Teste
Após o deploy, teste acessando diretamente:
- `https://seu-dominio.com/funcionarios`
- `https://seu-dominio.com/equipamentos`
- `https://seu-dominio.com/inventario`

Deve funcionar sem erro 404!
