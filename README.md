[README.md](https://github.com/user-attachments/files/28743778/README.md)
# `README.md`

```markdown
# Forma & Matéria — Arquitetura e Interiores

> **Estudo de Caso de UI Engineering, Estratégia de Nicho Premium e Co-Criação com Inteligência Artificial.**
> 
> Uma landing page conceitual de alto padrão desenvolvida sob o paradigma de **Human-in-the-Loop (HitL)**, demonstrando como alinhar de forma precisa decisões de design, psicologia de consumo, engenharia de interface e performance técnica.

---

## 🔗 Demonstração

*   **Live Demo:** [https://forma-e-materia.vercel.app/]
*   **Autor e Arquiteto de Software:** Lívio Eduardo

---

## 📐 O Desafio & Visão de Produto

Desenvolver para o mercado de **arquitetura e design de interiores de alto padrão** exige um nível de contenção visual que a maioria dos templates generativos não alcança. Clientes desse nicho rejeitam poluição visual, gatilhos de vendas agressivos (CTAs espalhafatosos) e elementos interativos barulhentos.

O objetivo deste projeto foi construir uma interface que respire **minimalismo, sofisticação e precisão técnica**, equilibrando uma paleta tátil de baixa saturação (marfim quente, carvão mineral e ouro fosco) com tipografia de forte contraste editorial (clássica *Libre Baskerville* para displays e a geométrica *Jost* para textos corridos).

---

## 🤖 O Fluxo de Trabalho AI-Native ( Claude ➔ Gemini ➔ Refinamento )

Este projeto é um exemplo prático de desenvolvimento acelerado por inteligência artificial sob **rigorosa arbitragem humana**. O processo de desenvolvimento passou por três etapas evolutivas de refinamento de prompt e tomada de decisão arquitetônica:

```
  [ Claude ]                 [ Gemini ]              [ Refinamento Final ]
Boilerplate & Layout  ➔  Otimização de UX & Responsivo  ➔  Ajuste Fino de Contraste,
     Inicial             Remoção de Elementos Ruidosos     Performance de GPU & Domínio
```

A IA atuou como uma excelente geradora de código-base (*boilerplate*), mas apresentou alucinações e decisões de design inadequadas para o nicho de luxo. A engenharia e a qualidade final do produto são o resultado direto de **intervenções manuais e correções cirúrgicas ao longo do processo**.

---

## 🛠️ Vitórias de Engenharia & Arbitragem Técnica

Abaixo estão detalhados os pontos críticos onde a tomada de decisão humana foi necessária para corrigir e aprimorar o código sugerido pelas ferramentas de inteligência artificial:

### 1. Engenharia de Contraste Seletivo Bilateral (CSS)
*   **O Problema da IA:** O layout da dobra inicial do site (*hero*) é dividido ao meio (50/50): lado esquerdo escuro (carvão) e lado direito claro (marfim). A IA propôs inicialmente uma cor escura genérica para o menu superior transparente. Isso fez com que os links do lado esquerdo (sobre fundo carvão) ficassem ilegíveis, com contraste quase nulo.
*   **A Arbitragem Humana:** Criação de uma lógica seletiva dinâmica em CSS utilizando seletores `:nth-child` dentro de media-queries específicas. No estado inicial antes do scroll, os links que se sobrepõem ao lado escuro herdam a cor marfim, enquanto os links do lado claro herdam a cor carvão. Ao rolar a página (*scrolled*), o cabeçalho ganha fundo marfim fosco e todos os links transicionam de forma suave e unificada para o tom carvão profundo.

```css
@media (min-width: 1025px) {
  /* Links sobre o lado escuro (esquerdo) */
  nav:not(.scrolled) .nav-links li:nth-child(1) a,
  nav:not(.scrolled) .nav-links li:nth-child(2) a {
    color: var(--ivory);
  }
  /* Links sobre o lado claro (direito) */
  nav:not(.scrolled) .nav-links li:nth-child(3) a,
  nav:not(.scrolled) .nav-links li:nth-child(4) a {
    color: var(--charcoal);
  }
}
```

### 2. Redução Drástica de Fricção no Contato (UX)
*   **O Problema da IA:** A solução inicial sugerida para o formulário de contato usava protocolos de envio baseados em e-mail padrão do sistema operacional (`mailto:`). Isso gerava fricção no usuário, forçando a abertura de aplicativos pesados (como Outlook ou Mail) e travando a experiência de navegação.
*   **A Arbitragem Humana:** Refatoração de toda a jornada de conversão. Foi desenvolvido um chatbot modular de contato em JavaScript puro, integrado a um formulário que realiza requisições AJAX assíncronas em segundo plano, mantendo o usuário na página e abrindo um canal de comunicação direto via WhatsApp no momento certo.

### 3. Remoção de Ruído de Interface (De-cluttering)
*   **O Problema da IA:** A primeira versão gerada continha um cursor interativo personalizado e animado via JavaScript, além de múltiplos botões pulsantes induzindo ao clique.
*   **A Arbitragem Humana:** Identificação de que o excesso de gatilhos visuais irrita o usuário de alto padrão e desvaloriza a experiência premium do site. O cursor personalizado foi descartado em prol do comportamento nativo do sistema operacional e o posicionamento dos CTAs foi desenhado para ser contido, pontual e elegante.

### 4. Aceleração de Hardware e Correção de Subpixel (GPU)
*   **O Problema da IA:** Durante as transições de escala do modal do chatbot, o motor de renderização (principalmente em navegadores Chromium e telas Retina) apresentava um efeito de desfoque/embaçamento temporário nas fontes e bordas.
*   **A Arbitragem Humana:** Otimização da renderização via CSS. Apliquei propriedades que forçam o navegador a processar o modal na GPU em vez de na CPU (`will-change`, `backface-visibility: hidden` e ajustes refinados no `scale(0.99)`), garantindo que os elementos textuais permaneçam perfeitamente nítidos durante toda a animação.

### 5. Alinhamento de Domínio e Terminologia de Mercado
*   **O Problema da IA:** Por não ter o contexto prático da profissão de arquiteto de interiores de luxo, a IA utilizou termos genéricos de tecnologia e engenharia de software para definir etapas do projeto (como *"Descoberta"* e *"Feedback Iterativo"*) ou erros conceituais de construção como *"amplificação de ambientes"*.
*   **A Arbitragem Humana:** Revisão de toda a redação publicitária (*copywriting*) para alinhar a página às práticas reais de mercado (mudança de *"Descoberta"* para **Briefing & Diagnóstico**, de *"feedback iterativo"* para **revisões colaborativas**, e de *"amplificação"* para **ampliação**, termo correto na engenharia civil para extensão física de área construída).

---

## 📦 Stack Tecnológico (Vanilla Core)

*   **HTML5 Semântico:** Marcação estruturada focada em SEO e acessibilidade (WAI-ARIA).
*   **CSS3 Moderno:** Layout responsivo baseado em CSS Grid e Flexbox, tipografia fluida baseada na função `clamp()` e variáveis globais para fácil manutenção do *Design System*.
*   **JavaScript (ES6+) Puro:** Animações nativas de scroll e comportamento lógico do chatbot sem dependência de bibliotecas ou frameworks pesados, garantindo tempo de carregamento de página inferior a 1 segundo.

---

## 🚀 Como Executar o Projeto Localmente

Como o projeto foi desenvolvido sobre a premissa de arquitetura limpa (sem frameworks ou empacotadores), você não precisa de nenhum gerenciador de pacotes ou instalação complexa.

1. Clone este repositório para a sua máquina:
   ```bash
   git clone https://github.com/livioeduardo/forma-e-materia/
   ```
2. Navegue até a pasta do projeto:
   ```bash
   cd forma-e-materia
   ```
3. Abra o arquivo `index.html` diretamente em seu navegador ou utilize a extensão **Live Server** do VSCode para emular em ambiente local de desenvolvimento.

---

## 📝 Licença & Autoria

*   **Desenvolvedor Front-end & UI Designer:** Lívio Eduardo
*   *Este projeto foi desenvolvido como peça de portfólio conceitual técnico de alto padrão.*
