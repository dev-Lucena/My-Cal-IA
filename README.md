# MYCAL'

MYCAL' é uma landing page de um app de nutrição com IA que estima calorias e macros a partir de uma foto da refeição — tirada na hora pela câmera ou enviada por upload.

## ✅ O que está incluso

- Página inicial moderna e responsiva (mobile, tablet e desktop)
- Seção de benefícios e fluxo de uso
- Modal de cadastro/login com captura de foto (câmera ao vivo ou upload de imagem)
- Análise nutricional real feita por IA (Puter.js), a partir da foto enviada
- Histórico local salvo no navegador (localStorage)
- Compressão inteligente da imagem antes do envio à IA (evita timeouts e rejeições em fotos grandes)
- Parsing robusto da resposta da IA (suporta conteúdo multi-partes e texto explicativo)
- Resultado nutricional exibido em um painel visual com calorias e macros

## 📁 Estrutura do projeto

- `index.html` — página principal do site (HTML, CSS e JS em um único arquivo)
- `assets/` — imagens e vídeos usados pela landing page (`hero-poster.jpg`, `hero-demo.mp4`)
- `vercel.json` — configurações de hospedagem para a Vercel (cache e cabeçalhos)
- `LICENSE` — licença MIT
- `.gitignore` — arquivos ignorados pelo Git

## ▶️ Como visualizar localmente

Abra o arquivo `index.html` diretamente no navegador ou sirva a pasta localmente com:

```bash
python -m http.server 8000
```

Depois acesse:

```text
http://localhost:8000/
```

> A captura de câmera (`getUserMedia`) exige contexto seguro: funciona em `localhost` durante o desenvolvimento e exige **HTTPS** em produção (o Vercel já entrega HTTPS por padrão).

## 🤖 Como funciona a análise de IA

A foto do prato (tirada pela câmera ou enviada por upload) é convertida em base64 no navegador e enviada para `puter.ai.chat`, que retorna uma estimativa de calorias, proteínas, carboidratos, gorduras, fibras, açúcar e um índice de confiança. Não é necessária nenhuma chave de API: o Puter.js roda inteiramente no cliente.

## 🚀 Publicar no GitHub

1. Crie um repositório novo no GitHub.
2. Na pasta do projeto:
   ```bash
   git init
   git add .
   git commit -m "MYCAL': landing page com análise nutricional por IA"
   git branch -M main
   git remote add origin https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git
   git push -u origin main
   ```

## ▲ Publicar na Vercel

1. Acesse [vercel.com](https://vercel.com) e faça login com sua conta GitHub.
2. Clique em **Add New… → Project** e selecione o repositório recém-criado.
3. Como é um site estático, a Vercel detecta automaticamente — não é necessário configurar build command nem output directory.
4. Clique em **Deploy** e aguarde a publicação.

## 🧪 Observações

- O histórico de refeições e o login de demonstração ficam salvos apenas no `localStorage` do navegador (funcionam por dispositivo/navegador, sem backend).
- Tamanho máximo de imagem aceito: 8MB.
- Compatível com os principais navegadores modernos (Chrome, Safari, Firefox, Edge).
