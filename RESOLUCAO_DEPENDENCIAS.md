# Resolução do Conflito de Dependências

## Problema Identificado
O erro ocorreu devido a um conflito entre as versões do `date-fns` e `react-day-picker`:

- `date-fns` estava na versão `^4.1.0`
- `react-day-picker` esperava apenas `^2.28.0 || ^3.0.0`

## Solução Aplicada

### 1. Atualização do package.json
- ✅ `date-fns`: `^4.1.0` → `^3.6.0`
- ✅ `react-day-picker`: `^8.10.1` → `^9.4.3`

### 2. Próximos Passos

Execute os seguintes comandos para aplicar as mudanças:

```bash
# Remover node_modules e package-lock.json
rm -rf node_modules package-lock.json

# Instalar dependências novamente
npm install
```

### 3. Verificação
Após a instalação, verifique se não há erros executando:

```bash
npm run dev
```

## Compatibilidade
- O componente `Calendar` em `src/components/ui/calendar.tsx` é compatível com a nova versão
- Não são necessárias mudanças no código existente

## Alternativas (se necessário)
Se ainda houver problemas, você pode usar:

```bash
npm install --legacy-peer-deps
```

Ou forçar a instalação:

```bash
npm install --force
```

Mas é recomendado usar a solução acima primeiro.
