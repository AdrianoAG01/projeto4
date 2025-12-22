# Coleção Dorameira Premium - Build Estática

## 📁 Estrutura de Arquivos

```
public/
├── index.html           # Página principal (HTML)
├── favicon.png          # Ícone do site
├── .htaccess            # Configuração para servidores Apache
├── assets/
│   ├── index-*.css      # Estilos compilados
│   └── index-*.js       # JavaScript compilado
└── README.md            # Este arquivo
```

## 🚀 Como Usar no GitHub Pages

### Passo 1: Upload dos Arquivos
Faça upload de todos os arquivos da pasta `public/` para a subpasta do seu repositório:

```
seu-repo/
└── novaoferta2/
    ├── index.html
    ├── favicon.png
    ├── .htaccess
    ├── assets/
    │   ├── index-*.css
    │   └── index-*.js
    └── README.md
```

### Passo 2: Configuração no GitHub Pages
No repositório do GitHub:
1. Vá para **Settings** > **Pages**
2. Selecione a branch que contém a pasta `public/`
3. Defina a pasta raiz como a subpasta (ex: `/novaoferta2`)
4. Clique em **Save**

### Passo 3: Acesse
Acesse: `https://seu-usuario.github.io/seu-repo/novaoferta2`

## ⚙️ Detalhes Técnicos

- **Framework**: React + Vite
- **CSS**: Tailwind CSS (incluído no bundle)
- **JavaScript**: Bundle único compilado e minificado
- **Responsivo**: Funciona em desktop, tablet e mobile
- **Sem dependências externas**: Tudo está incluído nos arquivos

## 🔧 Configuração Alternativa (Se não usar GitHub Pages)

Se você estiver usando seu próprio servidor:

### Apache
- O arquivo `.htaccess` já está configurado
- Certifique-se de que `mod_rewrite` está ativado

### Nginx
Adicione isto à configuração do seu site:
```nginx
location /novaoferta2 {
    try_files $uri $uri/ /novaoferta2/index.html;
}
```

### Node.js / Express
```javascript
app.use('/novaoferta2', express.static('public'));
app.get('/novaoferta2/*', (req, res) => {
  res.sendFile(path.join(__dirname, 'public/index.html'));
});
```

## 📝 Notas Importantes

✅ Os caminhos estão configurados como **relativos** para funcionar em subpastas
✅ Todos os estilos e scripts estão **inlined** no bundle
✅ A aplicação é totalmente **estática** - não precisa de servidor Node.js
✅ Funciona offline após o primeiro carregamento (com service workers do navegador)

## 🐛 Troubleshooting

**Problema**: CSS/JS não está carregando
- **Solução**: Verifique se o caminho da subpasta está correto no seu servidor

**Problema**: Rotas da aplicação não funcionam
- **Solução**: Certifique-se de que o servidor está redirecionando requisições não encontradas para `index.html`

**Problema**: Imagens não carregam
- **Solução**: Verifique se os arquivos em `assets/` foram copiados corretamente

---

**Gerado em**: 22 de dezembro de 2025
