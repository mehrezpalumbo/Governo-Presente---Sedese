# SEDESE — Painel Gov. Presente 3

Painel interativo de entregas da SEDESE para o Governo Presente 3.  
Os dados são lidos diretamente da planilha no Google Sheets a cada acesso.

---

## Como publicar (passo a passo)

### 1. Criar a API Key do Google

1. Acesse [console.cloud.google.com](https://console.cloud.google.com)
2. Crie um projeto novo (ou use um existente) → clique em **"Selecionar projeto" > "Novo projeto"**
3. No menu lateral, vá em **APIs e Serviços > Biblioteca**
4. Pesquise **"Google Sheets API"** e clique em **Ativar**
5. Vá em **APIs e Serviços > Credenciais**
6. Clique em **"+ Criar credenciais" > "Chave de API"**
7. Copie a chave gerada (começa com `AIza...`)
8. **Opcional mas recomendado:** clique em "Editar chave" e em "Restrições de API", restrinja à Google Sheets API. Em "Restrições de aplicativo", coloque o domínio do seu GitHub Pages (ex: `seuusuario.github.io`)

### 2. Inserir a API Key no arquivo index.html

Abra o arquivo `index.html` e localize a linha:

```js
const API_KEY = 'COLE_SUA_API_KEY_AQUI';
```

Substitua pelo valor real:

```js
const API_KEY = 'AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX';
```

### 3. Publicar no GitHub Pages

1. Acesse [github.com](https://github.com) e crie um **novo repositório público**  
   Sugestão de nome: `painel-gov-presente`

2. Faça upload dos arquivos:
   - `index.html`
   - `README.md`

   Você pode arrastar os arquivos diretamente pela interface web do GitHub.

3. Vá em **Settings > Pages**

4. Em **"Branch"**, selecione `main` e pasta `/ (root)`

5. Clique em **Save**

6. Aguarde ~1 minuto. O painel estará disponível em:  
   `https://seuusuario.github.io/painel-gov-presente`

---

## Como atualizar os dados

Basta editar a planilha no Google Sheets normalmente.  
Na próxima vez que alguém abrir o painel (ou clicar em **Atualizar**), os dados novos aparecerão automaticamente.

Não é necessário alterar nenhum arquivo do painel.

---

## Planilha conectada

- **ID da planilha:** `1yZsTc6VtPImD8OuxhGwe7O_OE6SbMa2depVsd_tm21k`
- **Aba utilizada:** `Entregas Propostas Governo Pres`
- **Link:** https://docs.google.com/spreadsheets/d/1yZsTc6VtPImD8OuxhGwe7O_OE6SbMa2depVsd_tm21k

A planilha deve estar com permissão **"Qualquer pessoa com o link pode ver"**.

---

## Funcionalidades do painel

- Filtros combinados: macrorregião, cidade sede, projeto, órgão, origem do recurso
- Busca livre por texto
- Pills de status rápido (Viável, Visita, A definir, Não viável)
- Métricas dinâmicas: total de entregas, municípios, pessoas estimadas, investimento
- Gráficos de barras por macrorregião e por projeto
- Tabela paginada com ordenação por coluna
- Tooltip com texto completo em campos truncados
- Botão "Atualizar" para buscar os dados mais recentes sem recarregar a página
