# 🔐 AUTENTICAÇÃO GITHUB - Guia Rápido

## ⚠️ **PROBLEMA:**
```
Permission denied to cortinasbresser
Error 403
```

Você precisa autenticar o Git com sua conta GitHub.

---

## ✅ **SOLUÇÃO MAIS FÁCIL: GitHub Desktop**

### **1. Baixar GitHub Desktop:**
- Acesse: https://desktop.github.com
- Baixe e instale

### **2. Fazer Login:**
- Abra GitHub Desktop
- File → Options → Accounts
- Sign in to GitHub.com
- Faça login com sua conta

### **3. Adicionar Repositório:**
- File → Add local repository
- Escolha: `e:\CB\www\cortinasbresser`
- Clique em "Add repository"

### **4. Push:**
- Clique em "Push origin" (botão azul no topo)
- Pronto! ✅

---

## ✅ **SOLUÇÃO ALTERNATIVA: Personal Access Token**

### **1. Criar Token no GitHub:**

1. Acesse: https://github.com/settings/tokens
2. Clique em "Generate new token" → "Generate new token (classic)"
3. Dê um nome: `cortinasbresser-deploy`
4. Marque: `repo` (todas as opções)
5. Clique em "Generate token"
6. **COPIE O TOKEN** (você não verá novamente!)

### **2. Usar Token no Git:**

```powershell
# No PowerShell, execute:
git push -u origin main
```

Quando pedir credenciais:
- **Username:** workriar
- **Password:** [COLE O TOKEN AQUI]

---

## ✅ **SOLUÇÃO ALTERNATIVA 2: SSH**

### **1. Gerar Chave SSH:**

```powershell
ssh-keygen -t ed25519 -C "seu@email.com"
```

Pressione Enter 3 vezes (aceitar padrões)

### **2. Copiar Chave Pública:**

```powershell
cat ~/.ssh/id_ed25519.pub | clip
```

### **3. Adicionar no GitHub:**

1. Acesse: https://github.com/settings/keys
2. Clique em "New SSH key"
3. Cole a chave
4. Clique em "Add SSH key"

### **4. Mudar Remote para SSH:**

```powershell
git remote set-url origin git@github.com:workriar/cortinasbresser.git
git push -u origin main
```

---

## 🎯 **RECOMENDAÇÃO:**

**Use GitHub Desktop - É o mais fácil!**

1. Baixe: https://desktop.github.com
2. Instale
3. Faça login
4. Adicione o repositório
5. Push com 1 clique

---

## 📝 **DEPOIS DO PUSH:**

Quando o push funcionar, você verá:

```
Enumerating objects: 100, done.
Counting objects: 100% (100/100), done.
Writing objects: 100% (100/100), 5.00 MiB | 2.00 MiB/s, done.
Total 100 (delta 0), reused 0 (delta 0)
To https://github.com/workriar/cortinasbresser.git
 * [new branch]      main -> main
```

**Aí você pode fazer deploy no Netlify!** ✅

---

## 🚀 **PRÓXIMOS PASSOS:**

1. **Autenticar Git:**
   - GitHub Desktop (recomendado)
   - Ou Personal Access Token
   - Ou SSH

2. **Push:**
   ```powershell
   git push -u origin main
   ```

3. **Deploy no Netlify:**
   - https://app.netlify.com
   - Import do GitHub
   - Deploy!

---

**Escolha uma das soluções acima e faça o push!** 🚀
