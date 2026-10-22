<!-- l10n-sync: source-file="workshop/04-design-vibes.md" -->
# Parte 4: Tematização com foco no design

---

Nesta parte, você vai usar os ciclos de planejamento e implementação do Copilot para criar uma transformação visual abrangente. Esta é uma abordagem de desenvolvimento com foco no design: comece com uma visão, itere nos elementos visuais e deixe o Copilot cuidar do trabalho pesado de CSS.

## Tarefa 1: Planeje o tema retrô

<!-- track:vscode:start -->
Mude para o modo **Plan** no GitHub Copilot Chat.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Use `/plan` no GitHub Copilot CLI ou pressione **Shift+Tab** até ativar o modo plan.
<!-- track:cli:end -->

Digite este prompt:

> Quero transformar esta página em uma experiência completa de arcade retrô. Planeje uma reformulação visual abrangente que inclua: efeitos de linhas de varredura CRT no fundo, brilho neon pulsante no título como um letreiro neon, emblema VS animado com mudanças nas cores do gradiente, camada de brilho e cintilação nos cartões de resultados dos usuários, animações de entrada flutuante nos campos de entrada, texto de carregamento alternando entre verde e roxo e efeitos de brilho ao passar o cursor sobre os quadrados de contribuição. Mantenha o fundo escuro (`#0a0a1a`) e as cores de destaque verde (`#5fed83`) e roxo (`#8a2be2`). Use um tema escuro com a fonte retrô Press Start 2P do Google Fonts.

O Copilot vai gerar um plano de implementação detalhado que abrange todos os efeitos visuais. **Não aceite imediatamente** — revise o plano e itere:

- Sugira ajustes no tempo das animações (por exemplo: *"Deixe o pulso neon mais lento, com cerca de 3 segundos"*).
- Pergunte sobre efeitos específicos (por exemplo: *"Como vai funcionar a camada de cintilação nos cartões?"*).
- Peça mudanças na abordagem se algo não parecer adequado.

## Tarefa 2: Implemente o tema

Quando estiver satisfeito com o plano, peça ao Copilot para implementá-lo:

> Implemente o plano do tema de arcade retrô que acabamos de criar.

O Copilot vai adicionar várias animações CSS, pseudoelementos e transições à sua folha de estilos. Isso pode incluir:

- `@keyframes` para linhas de varredura, pulso neon, cintilação e efeitos de entrada flutuante
- Pseudoelementos (`::before`, `::after`) para efeitos de sobreposição
- Propriedades personalizadas de CSS para as cores do tema
- Transições e estados ao passar o cursor sobre elementos interativos

<!-- track:cli:start -->
Depois que as alterações forem aplicadas, use `/diff` para revisar as mudanças de estilo antes de aprová-las.
<!-- track:cli:end -->

## Tarefa 3: Ajuste o visual

> **⚠️ Não está vendo as alterações?** Se o novo tema ou as animações não aparecerem, pare o servidor de desenvolvimento (`Ctrl+C`), reinicie-o com `npm run dev` e atualize o navegador forçando o recarregamento (`Ctrl+Shift+R`).

Mantenha a prévia do navegador aberta e itere no design. Experimente prompts como:

> O efeito das linhas de varredura está intenso demais; reduza a opacidade para 0.03.

> Adicione uma cintilação elétrica sutil ao texto do título.

> Faça o emblema VS pulsar com mais intensidade.

Isso é **desenvolvimento com foco no design** — você está iterando no resultado visual em tempo real. Cada prompt refina a experiência até ela ficar do jeito certo. Não se contente com "bom o suficiente" — aperfeiçoe o visual até a página parecer ter saído de um fliperama.

## Tarefa 4: Atualize as instruções

As instruções devem refletir as principais decisões de design para manter os próximos prompts alinhados.

<!-- track:vscode:start -->
Peça ao Copilot Chat:

> Adicione ao `copilot-instructions.md` uma seção de guia de design que descreva o tema de arcade retrô: cores, fontes e estilo das animações.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Peça ao Copilot CLI:

> Atualize as instruções do repositório com um guia de design curto para o tema de arcade retrô: cores, fontes, estilo das animações e a regra de que novas interfaces devem manter a estética neon.
<!-- track:cli:end -->

Quando a página estiver com a aparência desejada, faça commit das instruções e das alterações de design.

## ✅ Parte 4 concluída

**O que você aprendeu:**

- Use fluxos de planejamento para esboçar um **sistema de design antes da implementação**
- **Itere no resultado visual** com prompts rápidos de acompanhamento
- **Atualize as instruções após decisões importantes** para manter a identidade visual do Copilot consistente
