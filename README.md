[README.md](https://github.com/user-attachments/files/27544784/README.md)
# 💈 Leo Studio Barber — README

## Descrição do Projeto
Site institucional da **Leo Studio Barber**, uma barbearia fictícia localizada na Vila Madalena, São Paulo. Desenvolvido como parte do trabalho da disciplina **Padrões Web para No Code e Low Code** da UniFECAF.

---

## 🛠 Ferramentas Utilizadas

| Ferramenta | Função |
|---|---|
| **Webflow** | Ferramenta no-code principal para construção do site |
| **Google Forms** | Formulário de agendamento (integrado via HTML Embed) |
| **Google Maps** | Mapa de localização (integrado via HTML Embed) |
| **HTML5 / CSS3 / JS** | Customizações de código manual inseridas no Webflow |
| **Google Fonts** | Tipografia (Playfair Display + DM Sans) |
| **Unsplash** | Imagens com licença livre |

---

## 📄 Estrutura do Site

```
leo-studio-barber/
├── index.html          → Site completo (HTML de referência)
├── relatorio.docx      → Relatório teórico (Parte 1)
└── README.md           → Este arquivo
```

### Seções do Site

1. **Hero** — Apresentação com nome, slogan e CTA de agendamento
2. **Serviços** — 6 serviços com preços e descrições
3. **Sobre** — História da barbearia e estatísticas
4. **Galeria** — Portfólio fotográfico (5 imagens)
5. **Agendamento** — Formulário via Google Forms embed
6. **Contato** — Endereço, horários, WhatsApp e mapa

---

## ▶️ Como Usar no Webflow

### Passo 1 — Criar conta
Acesse [webflow.com](https://webflow.com) e crie uma conta gratuita.

### Passo 2 — Criar novo projeto
- Clique em **New Project**
- Selecione **Blank Site**
- Nomeie como "Leo Studio Barber"

### Passo 3 — Construir as seções
Para cada seção, use o painel esquerdo do Webflow:
- **Add Element** (ícone +) → arraste componentes como `Section`, `Container`, `Heading`, `Text`, `Button`, `Image`
- Configure cores, fontes e espaçamentos no painel direito

### Passo 4 — Inserir código customizado

**CSS Global** → Settings > Custom Code > `<head>`:
```css
:root {
  --black: #0a0a0a;
  --white: #f5f0eb;
  --red: #c0001a;
  --gold: #c9a84c;
}

.service-card {
  border-top: 3px solid transparent;
  transition: border-color 0.25s;
}
.service-card:hover {
  border-color: var(--gold);
}

.reveal {
  opacity: 0;
  transform: translateY(28px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}
```

**JavaScript** → Settings > Custom Code > Before `</body>`:
```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('visible');
      observer.unobserve(e.target);
    }
  });
}, { threshold: 0.12 });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
```

### Passo 5 — Integrar Google Forms
1. Acesse [forms.google.com](https://forms.google.com) e crie seu formulário
2. Clique em **Enviar** > ícone **<>** (Incorporar)
3. Copie o código `<iframe>`
4. No Webflow, adicione um elemento **HTML Embed** na seção de agendamento
5. Cole o código do iframe

### Passo 6 — Integrar Google Maps
1. Acesse [maps.google.com](https://maps.google.com)
2. Busque o endereço da barbearia
3. Clique em **Compartilhar** > **Incorporar mapa**
4. Copie o código `<iframe>`
5. No Webflow, adicione um **HTML Embed** na seção de contato e cole o código

### Passo 7 — Responsividade
No Webflow, use os breakpoints no topo do editor:
- 🖥 Desktop (padrão)
- 💻 Tablet (≤991px)
- 📱 Mobile Landscape (≤767px)
- 📱 Mobile Portrait (≤479px)

Ajuste layout, tamanhos de fonte e visibilidade de elementos para cada breakpoint.

### Passo 8 — Publicar
- Clique em **Publish** (botão azul no canto superior direito)
- Escolha o subdomínio gratuito: `leostudiobarber.webflow.io`
- Clique em **Publish to webflow.io**

---

## ♿ Acessibilidade Implementada

- `lang="pt-BR"` na tag `<html>`
- `aria-label` em todos os botões, links e regiões
- Atributo `alt` descritivo em todas as imagens
- Hierarquia de headings: h1 → h2 → h3
- Contraste mínimo 4.5:1 (texto sobre fundo)
- `loading="lazy"` nas imagens da galeria
- `role` semântico: `navigation`, `list`, `region`

---

## 📱 Responsividade

| Breakpoint | Comportamento |
|---|---|
| Desktop (>900px) | Layout em grid de 3 colunas |
| Tablet (≤900px) | Layout em 2 colunas, sobre empilhado |
| Mobile (≤640px) | Layout em 1 coluna, menu hamburger |

---

## 🎨 Paleta de Cores

| Cor | Hex | Uso |
|---|---|---|
| Preto | `#0A0A0A` | Fundo principal |
| Branco | `#F5F0EB` | Texto e elementos claros |
| Vermelho | `#C0001A` | Botões de ação e destaques |
| Dourado | `#C9A84C` | Acentos e identidade da marca |

---

## 📌 Informações do Projeto

- **Disciplina:** Padrões Web para No Code e Low Code
- **Instituição:** UniFECAF
- **Ano:** 2025
- **Ferramenta Principal:** Webflow
- **Integrações:** Google Forms, Google Maps

---

*Desenvolvido como trabalho acadêmico. Imagens de uso livre via Unsplash. Todos os dados são fictícios.*
