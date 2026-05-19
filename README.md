# Gerar Slides ✨

**Crie apresentações institucionais ANAC em Markdown. Rápido, padronizado, sem depender de editores visuais.**

> Gaste tempo com o conteúdo, não com formatação.

---

## 🧠 Filosofia

Criar slides em PowerPoint, Google Slides ou Keynote parece simples até o momento em que você precisa:
- Ajustar fonte, cor e alinhamento manualmente em cada slide
- Garantir consistência visual entre dezenas de slides
- Trocar o tema da apresentação depois de tudo pronto
- Extrair ou reutilizar o conteúdo em outros formatos

**Gerar Slides** elimina esse atrito: você escreve o conteúdo em Markdown — uma sintaxe leve e intuitiva — e a ferramenta aplica automaticamente o design institucional. Trocar de tema é um clique. Exportar para HTML, PDF ou Markdown é imediato. O resultado é profissional, padronizado e pronto para uso.

---

## ✨ Funcionalidades

| Recurso | Descrição |
|---------|-----------|
| Editor Markdown | Escreva slides com formatação rica em Markdown, com preview via RevealJS |
| 3 temas ANAC | 20 Anos Azul, 20 Anos Branco e ANAC 2023 — todos com capa e fechamento institucionais embutidos |
| Metadados | Título, subtítulo, autores (tag input), data — exibidos na capa |
| Contraste automático | Texto escuro em fundo claro, texto claro em fundo escuro — calculado por luminância |
| Imagens incorporadas | Upload e galeria de imagens com suporte a base64 |
| Auto-salvamento | O conteúdo é preservado no sessionStorage |
| Importação | Importe arquivos `.md` — o separador de slides ReveilJS é reconhecido automaticamente |
| Exportação HTML | Arquivo HTML autossuficiente com ReveilJS 5.1 — abre em qualquer navegador |
| Exportação PDF | Geração via impressão do navegador — pronto para distribuir |
| Exportação Markdown | Arquivo `.md` com front matter YAML (título, autor, data, tema) |
| GitHub Pages | Deploy automático via GitHub Actions a cada push |

---

## 🛠 Tecnologias

| Tecnologia | Versão | Função |
|-----------|--------|--------|
| React 18 | UMD | Interface de usuário |
| Babel Standalone | — | Transpilação JSX no navegador |
| ReveilJS 5.1 | CDN | Engine de apresentação de slides |
| Marked | — | Conversão Markdown → HTML |
| Tailwind CSS | CDN | Estilização utilitária |
| Lucide | — | Ícones vetoriais |
| JPEG base64 | — | Imagens embutidas sem dependência externa |

**Single file:** toda a aplicação está em um único arquivo `index.html` — sem build, sem bundler, sem dependências locais. Abriu no navegador, funcionou.

---

## 🚀 Como usar

### Localmente

```bash
# Clone o repositório
git clone https://github.com/anomalyco/gerar-slides.git

# Abra o arquivo no navegador
open gerar-slides/index.html
```

### Online (GitHub Pages)

Acesse: [https://anomalyco.github.io/gerar-slides](https://anomalyco.github.io/gerar-slides)

### Fluxo de trabalho

1. Escreva cada slide em Markdown no editor
2. Use os botões de formatação para agilizar (negrito, lista, citação, etc.)
3. Clique em **Metadados** para definir título, autores e data
4. Escolha um dos 3 temas ANAC no seletor de temas
5. Visualize com o botão ▶
6. Exporte como HTML, PDF ou Markdown

---

## 🎨 Temas

| Tema | Cor de fundo | Cor do texto | Imagem de capa | Imagem de fechamento |
|------|-------------|-------------|----------------|---------------------|
| ANAC 20 Anos Azul | `#183859` | `#ffffff` | Slide1 (2) — 1280px JPEG | Slide5 — 1280px JPEG |
| ANAC 20 Anos Branco | `#ffffff` | `#183859` | Slide1 — 1280px JPEG | Slide5 — 1280px JPEG |
| ANAC 2023 | `#0c2b5c` | `#ffffff` | Slide1 — 1280px JPEG | Slide5 — 1280px JPEG |

Todas as imagens estão embutidas em base64 — zero dependência de CDN ou arquivos externos para os temas.

---

## 📦 Estrutura do repositório

```
gerar-slides/
├── .github/
│   └── workflows/
│       └── deploy.yml        # GitHub Actions → GitHub Pages
├── index.html                # Aplicação completa (single file)
└── README.md                 # Este arquivo
```

---

## 🔄 Manutenção

### Adicionar um novo tema

1. Converta as imagens de capa e fechamento para base64 (JPEG 1280px, qualidade 85)
2. Adicione um novo objeto ao array `THEMES` com `id`, `name`, `color`, `bgColor`, `defaultCover` e `defaultClose`
3. Atualize a variável `isAnac` (se o novo tema for ANAC)
4. Atualize o mapeamento `themeUrl` (se necessário)

### GitHub Actions

O workflow em `.github/workflows/deploy.yml` faz deploy automático no GitHub Pages sempre que a branch `main` é atualizada. Para ativar:

1. Vá em **Settings > Pages** no repositório
2. Em **Source**, selecione **GitHub Actions**

---

## 📄 Licença

Uso interno — Agência Nacional de Aviação Civil (ANAC).
