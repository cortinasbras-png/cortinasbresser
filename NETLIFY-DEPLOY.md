# 🚀 DEPLOY NO NETLIFY - Guia Completo

## 📋 **INFORMAÇÕES DO PROJETO:**

- **Repositório GitHub:** https://github.com/workriar/cortinasbresser.git
- **Framework:** Next.js 14.2.33
- **Tipo:** Exportação Estática
- **Deploy:** Netlify

---

## ✅ **PASSO A PASSO - DEPLOY NO NETLIFY:**

### **1. Acessar Netlify**
- Acesse: https://app.netlify.com
- Clique em **"Sign up"** ou **"Log in"**
- Escolha **"GitHub"** para login

### **2. Conectar GitHub**
- Autorize o Netlify a acessar seu GitHub
- Permita acesso ao repositório `cortinasbresser`

### **3. Criar Novo Site**
- Na dashboard, clique em **"Add new site"**
- Selecione **"Import an existing project"**
- Escolha **"Deploy with GitHub"**

### **4. Selecionar Repositório**
- Procure por **"cortinasbresser"**
- Clique no repositório

### **5. Configurar Build**

#### **Configure as seguintes opções:**

**Branch to deploy:**
```
main
```

**Build command:**
```
npm run build
```

**Publish directory:**
```
out
```

**Base directory:**
```
(deixe vazio)
```

#### **Environment variables:**
```
# Nenhuma necessária por enquanto
```

### **6. Deploy**
- Clique em **"Deploy site"**
- Aguarde 2-5 minutos
- ✅ **Pronto! Seu site está no ar!**

---

## 🌐 **APÓS O DEPLOY:**

### **URL Gerada:**
O Netlify vai gerar uma URL automática:
```
https://random-name-123456.netlify.app
```

### **Mudar Nome do Site:**
1. Vá em **"Site settings"**
2. Clique em **"Change site name"**
3. Digite: `cortinasbresser`
4. Nova URL: `https://cortinasbresser.netlify.app`

### **Testar o Site:**
1. ✅ Hero Carousel (5 slides)
2. ✅ Botão "Solicitar Orçamento"
3. ✅ Formulário
4. ✅ Seção de Localização
5. ✅ Responsividade (mobile/desktop)

---

## 🔧 **CONFIGURAR DOMÍNIO PERSONALIZADO:**

### **Passo 1: Adicionar Domínio**
1. Vá em **"Domain settings"**
2. Clique em **"Add custom domain"**
3. Digite: `cortinasbresser.com.br`
4. Clique em **"Verify"**

### **Passo 2: Configurar DNS**

O Netlify vai mostrar as configurações DNS:

#### **Opção A: Netlify DNS (Recomendado)**
```
Nameservers:
dns1.p01.nsone.net
dns2.p01.nsone.net
dns3.p01.nsone.net
dns4.p01.nsone.net
```

#### **Opção B: CNAME**
```
Type: CNAME
Name: www
Value: cortinasbresser.netlify.app
```

#### **Opção C: A Record**
```
Type: A
Name: @
Value: 75.2.60.5
```

### **Passo 3: HTTPS**
- Netlify ativa HTTPS automaticamente
- Aguarde 1-2 minutos após DNS configurado
- Certificado SSL grátis via Let's Encrypt

---

## 🔄 **ATUALIZAÇÕES AUTOMÁTICAS:**

### **Como funciona:**
1. Você faz alterações no código
2. Faz commit e push para GitHub:
   ```bash
   git add .
   git commit -m "atualização"
   git push origin main
   ```
3. **Netlify detecta automaticamente**
4. **Faz build e deploy automático**
5. **Site atualizado em 2-3 minutos!**

### **Deploy Previews:**
- Pull Requests geram preview automático
- Teste antes de fazer merge
- URL única para cada PR

---

## 📊 **RECURSOS DO NETLIFY:**

### **✅ Incluído Grátis:**
- HTTPS automático (SSL)
- CDN global
- Deploy automático
- Deploy previews
- Form handling (formulários)
- 100GB bandwidth/mês
- 300 build minutes/mês
- Domínio personalizado

### **🎯 Performance:**
- Edge Network global
- Cache automático
- Compressão automática
- Image optimization
- Prerendering

---

## 📝 **ARQUIVO NETLIFY.TOML (Opcional):**

Crie um arquivo `netlify.toml` na raiz do projeto:

```toml
[build]
  command = "npm run build"
  publish = "out"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200

[[headers]]
  for = "/*"
  [headers.values]
    X-Frame-Options = "DENY"
    X-XSS-Protection = "1; mode=block"
    X-Content-Type-Options = "nosniff"
    Referrer-Policy = "strict-origin-when-cross-origin"

[[headers]]
  for = "/assets/*"
  [headers.values]
    Cache-Control = "public, max-age=31536000, immutable"
```

---

## 🔍 **MONITORAMENTO:**

### **Dashboard Netlify:**
- **Deploys:** Histórico de deploys
- **Analytics:** Visitantes (pago)
- **Logs:** Build logs e erros
- **Functions:** Serverless functions

### **Netlify Analytics (Pago):**
- Visitantes únicos
- Pageviews
- Top pages
- Referrers
- Sem cookies ou tracking

---

## 🆘 **TROUBLESHOOTING:**

### **Problema: Build falha**
**Solução:**
1. Verifique os logs no Netlify
2. Teste localmente: `npm run build`
3. Verifique `next.config.mjs`

### **Problema: 404 em páginas**
**Solução:**
1. Adicione `netlify.toml` com redirects
2. Verifique `output: 'export'` no config

### **Problema: Imagens não carregam**
**Solução:**
1. Verifique `images.unoptimized: true`
2. Confirme que imagens estão em `public/`

### **Problema: Domínio não funciona**
**Solução:**
1. Aguarde propagação DNS (até 48h)
2. Verifique configurações DNS
3. Use Netlify DNS para facilitar

---

## 📝 **CHECKLIST PÓS-DEPLOY:**

### **Funcionalidades:**
- [ ] Hero Carousel funcionando
- [ ] 5 slides aparecendo
- [ ] Botão "Solicitar Orçamento" funciona
- [ ] Formulário envia para WhatsApp
- [ ] Mapa do Google Maps carrega
- [ ] Cards de localização aparecem
- [ ] Responsivo em mobile
- [ ] Responsivo em tablet
- [ ] Responsivo em desktop

### **Performance:**
- [ ] Lighthouse Score > 90
- [ ] FCP < 1.8s
- [ ] LCP < 2.5s
- [ ] CLS < 0.1

### **SEO:**
- [ ] Meta tags corretas
- [ ] Open Graph funcionando
- [ ] Structured data presente

---

## 🎯 **PRÓXIMOS PASSOS:**

### **1. Fazer Deploy:**
1. Acesse https://app.netlify.com
2. Login com GitHub
3. Import projeto `cortinasbresser`
4. Configure build
5. Deploy!

### **2. Testar:**
1. Acesse a URL gerada
2. Teste todas as funcionalidades
3. Verifique em mobile

### **3. Configurar Domínio:**
1. Adicione `cortinasbresser.com.br`
2. Configure DNS
3. Aguarde propagação
4. HTTPS ativa automaticamente

### **4. Monitorar:**
1. Verifique Deploys
2. Monitore Build logs
3. Acompanhe Performance

---

## 🎉 **VANTAGENS DO NETLIFY:**

### **✅ Por que Netlify:**
1. **Build automático** - Sem erro de symlink
2. **Deploy em 2 minutos** - Super rápido
3. **HTTPS grátis** - SSL automático
4. **CDN global** - 100+ localizações
5. **Deploy previews** - Teste PRs
6. **Form handling** - Formulários nativos
7. **Edge Functions** - Serverless
8. **Fácil de usar** - Interface intuitiva

### **💰 Custo:**
- **Grátis** para projetos pessoais
- **Sem limite** de sites
- **100GB** bandwidth/mês grátis
- **300 minutos** build/mês grátis

---

## 📊 **NETLIFY vs VERCEL:**

| Recurso | Netlify | Vercel |
|---------|---------|--------|
| **Build automático** | ✅ Sim | ✅ Sim |
| **HTTPS grátis** | ✅ Sim | ✅ Sim |
| **CDN global** | ✅ Sim | ✅ Sim |
| **Deploy previews** | ✅ Sim | ✅ Sim |
| **Form handling** | ✅ Sim | ❌ Não |
| **Edge Functions** | ✅ Sim | ✅ Sim |
| **Analytics** | 💰 Pago | 🆓 Grátis |
| **Bandwidth** | 100GB | 100GB |

---

## 📞 **SUPORTE:**

### **Documentação:**
- Netlify Docs: https://docs.netlify.com
- Next.js on Netlify: https://docs.netlify.com/frameworks/next-js

### **Comunidade:**
- Netlify Community: https://answers.netlify.com
- Discord: https://discord.gg/netlify

---

## ✅ **RESUMO RÁPIDO:**

```bash
# 1. Acesse
https://app.netlify.com

# 2. Login com GitHub

# 3. Import
https://github.com/workriar/cortinasbresser.git

# 4. Configure
Build: npm run build
Publish: out

# 5. Deploy
Clique em "Deploy site"

# 6. Aguarde 2-3 minutos

# 7. Pronto! ✅
```

---

## 🎊 **CONCLUSÃO:**

**Deploy no Netlify é excelente!**

✅ Rápido e fácil  
✅ Grátis  
✅ HTTPS automático  
✅ CDN global  
✅ Deploy automático  
✅ Form handling nativo  
✅ Deploy previews  

**Seu site estará no ar em menos de 5 minutos!** 🚀

---

**Criado em:** 2025-11-22  
**Repositório:** https://github.com/workriar/cortinasbresser.git  
**Status:** ✅ PRONTO PARA DEPLOY NO NETLIFY
