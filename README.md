# 🔗 Link na Bio - Premium Dark Mode

![Preview do Projeto](https://img.shields.io/badge/Status-Conclu%C3%ADdo-brightgreen)
![License](https://img.shields.io/badge/License-MIT-blue)

Uma página de "Link na Bio" moderna, minimalista e de alta performance, desenvolvida com foco em UI/UX para profissionais que buscam uma presença digital premium. O projeto apresenta um design _Dark Mode_ com efeitos de vidro (_glassmorphism_) e animações fluidas.

---

## ✨ Demonstração

Este projeto foi construído para ser visualmente impactante e funcional. Ele inclui:

- **Fundo Animado:** Gradientes sutis que se movem suavemente.
- **Glows Volumétricos:** Luzes de fundo (Cyan e Purple) que dão profundidade ao layout.
- **Avatar Dinâmico:** Foto de perfil com borda em gradiente giratório.
- **Cards Interativos:** Efeitos de hover com elevação e brilho personalizado por categoria.
- **Design Responsivo:** Otimizado para dispositivos móveis (Instagram, TikTok, Twitter).

---

## 🚀 Tecnologias Utilizadas

O projeto utiliza tecnologias web puras para garantir velocidade de carregamento instantânea:

- [HTML5](https://developer.mozilla.org/pt-BR/docs/Web/HTML) - Estrutura semântica.
- [CSS3](https://developer.mozilla.org/pt-BR/docs/Web/CSS) - Estilização avançada, animações e variáveis.
- [Google Fonts](https://fonts.google.com/specimen/Inter) - Fonte Inter para legibilidade moderna.
- [Lucide/HeroIcons](https://heroicons.com/) - Ícones em SVG para máxima nitidez.

---

## 🛠️ Como Personalizar

Para usar este projeto com suas próprias informações:

1. **Alterar a Foto de Perfil:**
   Substitua o arquivo em `./imagem/eudois.png` ou altere o `src` da tag `<img>` no `index.html`.

2. **Editar os Links:**
   No `index.html`, localize a seção `<section class="cards-section">` e atualize os atributos `href` e os textos dos títulos e descrições.

3. **Cores de Destaque:**
   As cores principais (Cyan e Purple) podem ser ajustadas diretamente no arquivo `style.css` nas classes `.glow-cyan`, `.glow-purple` e nos modificadores de card `.card--cyan` / `.card--purple`.

---

## 📦 Instalação e Uso

Não é necessário instalar dependências. Basta clonar o repositório e abrir o arquivo `index.html` no seu navegador:

```bash
# Clone este repositório
git clone https://github.com/seu-usuario/nome-do-repositorio.git

# Navegue até a pasta
cd nome-do-repositorio

# Abra o index.html (exemplo no VS Code)
code index.html
```

---

## 🐛 Problemas Enfrentados e Soluções

### 1. Animação do avatar sumindo no scroll (mobile)
**Problema:** Ao rolar a página no celular, a animação giratória em volta da foto de perfil sumia ou cobria a imagem.

**Causa:** Conflito de `z-index` entre as camadas `.avatar-ring`, `.avatar-mask` e `.avatar-img`, combinado com o `translateZ(0)` definido diretamente no elemento sendo sobrescrito pelo `@keyframes` que animava apenas o `rotate`.

**Solução:** Definição explícita de `z-index` em cascata (`ring: 0`, `mask: 1`, `img: 2`) e inclusão do `translateZ(0)` dentro do próprio `@keyframes` para não ser perdido durante a animação.

---

### 2. Animação do anel não visível no mobile
**Problema:** O efeito de borda giratória com `linear-gradient` e `filter: blur` não era renderizado corretamente em browsers mobile.

**Causa:** Browsers mobile têm suporte limitado a `filter: blur` em elementos com `transform` animado.

**Solução:** Substituição do `linear-gradient` + `blur` por `conic-gradient` sem blur, que tem compatibilidade nativa com mobile e produz o mesmo efeito visual de arco colorido girando.

---

### 3. Barra de scroll horizontal indesejada
**Problema:** Uma pequena barra de rolagem horizontal aparecia na página.

**Causa:** Elementos com `position: fixed` e dimensões maiores que a viewport (`.bg-image` com `height: 160%` e os glows posicionados fora da tela) causavam overflow horizontal.

**Solução:** Adição de `overflow-x: hidden` tanto no `html` quanto no `body`.

---

### 4. CSS inline misturado ao HTML
**Problema:** Todo o CSS estava embutido via classes utilitárias do Tailwind diretamente nas tags HTML, dificultando manutenção.

**Solução:** Migração completa para um arquivo `style.css` externo com classes semânticas, removendo a dependência do Tailwind CDN.

---

### 5. Imagens dos cards não carregavam
**Problema:** Os cards exibiam apenas placeholders cinzas sem imagem real.

**Causa:** As URLs do `placehold.co` dependem de serviço externo e não representam conteúdo visual relevante.

**Solução:** Substituição por imagens reais e temáticas do Unsplash via URL direta, sem necessidade de download local.

---

## 👤 Autor

**Marcos Oliveira**  
_Especialista em Automação de Processos_

- LinkedIn: Seu Perfil
- GitHub: @DedicatedDevExpert

---

Desenhado com ❤️ para uma experiência premium.
