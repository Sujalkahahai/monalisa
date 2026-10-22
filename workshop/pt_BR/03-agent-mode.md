<!-- l10n-sync: source-file="workshop/03-agent-mode.md" -->
# Parte 3: Construa o jogo com fluxos de trabalho agênticos

---

Nesta parte, o Copilot passa de planejador a implementador. Em vez de escrever código linha por linha, você descreve o que quer e deixa o Copilot executar o trabalho nos arquivos que precisam ser alterados.

## Tarefa 1: Conecte a batalha

<!-- track:vscode:start -->
1. Mude para o modo **Agent** no Copilot Chat.
2. Digite este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Retorne o Copilot CLI ao fluxo de programação padrão (ou continue no modo autopilot se quiser que o Copilot prossiga até você pará-lo).
2. Se for útil, mencione o arquivo da página para dar mais contexto: `@src/pages/index.astro`
3. Digite este prompt:
<!-- track:cli:end -->

   > Adicione JavaScript do lado do cliente à página de batalha para que:
   > 1. Ao clicar no botão Battle, obtenha os dois nomes de usuário dos campos.
   > 2. Valide se ambos foram preenchidos (e exiba um erro caso contrário).
   > 3. Busque em paralelo, pela nossa API, os dados de contribuições dos dois usuários.
   > 4. Exiba os gráficos de contribuições em grids coloridos — cada dia deve ser um quadrado colorido usando a paleta de cores do GitHub.
   > 5. Mostre um emblema VS entre os dois usuários.
   > 6. Exiba o nome de usuário, o total de contribuições e o intervalo de datas de cada usuário.
   > 7. Trate estados de carregamento e erros.
   > 8. Também inicie ao pressionar Enter nos campos de entrada.
   > 9. Use por enquanto a interface simples que já está pronta.
   >
   > Use interfaces do TypeScript para a estrutura de dados de contribuições.

<!-- track:vscode:start -->
3. Deixe o Agent Mode implementar as alterações em vários arquivos de `index.astro`.
4. Revise as alterações propostas na visualização de diff antes de aceitá-las.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deixe o Copilot CLI implementar as alterações em `src/pages/index.astro`.
5. Use `/diff` para inspecionar as alterações geradas e, em seguida, aprove-as.
<!-- track:cli:end -->

## Tarefa 2: Teste a batalha

> **⚠️ Não está vendo as alterações?** Se a página de batalha não tiver sido atualizada, pare o servidor de desenvolvimento (`Ctrl+C`), reinicie-o com `npm run dev` e atualize o navegador.

1. Digite `octocat` e `torvalds` como nomes de usuário e clique em **Battle**.
2. Você deve ver os gráficos de contribuições de ambos os usuários em grids coloridos, lado a lado.
3. Teste os casos de erro:
   - Deixe um ou ambos os campos vazios e clique em Battle — uma mensagem de validação deve aparecer.
   - Digite um nome de usuário inválido — o aplicativo deve exibir um erro da API.
4. Pressione **Enter** em qualquer campo — isso deve iniciar a batalha como se você tivesse clicado no botão.

## Tarefa 3: Itere com o Copilot

Se algo não estiver exatamente como deveria, envie comentários de acompanhamento diretamente ao Copilot. Por exemplo:

- *"Os quadrados de contribuição estão grandes demais; deixe-os com 12x12px"*
- *"Adicione uma dica ao passar o cursor que mostre a data e a contagem de contribuições"*
- *"O estado de carregamento precisa de uma animação pulsante"*

<!-- track:vscode:start -->
O Agent Mode lida naturalmente com alterações em vários arquivos e iterações. Cada prompt de acompanhamento aproveita o contexto da conversa anterior, permitindo refinar a implementação aos poucos sem recomeçar.
<!-- track:vscode:end -->

<!-- track:cli:start -->
As sessões do Copilot CLI mantêm o histórico, então cada prompt de acompanhamento aproveita o anterior. Use `/session` ou `/context` para consultar o contexto mantido pelo Copilot e `/review` após uma iteração maior, se quiser uma revisão extra de bugs ou melhorias.
<!-- track:cli:end -->

## Dicas para esta parte

- **Seja específico sobre o que você quer** — requisitos claros levam a resultados melhores.
- **Divida tarefas grandes em prompts menores** se o Copilot sair do rumo.
- **Revise as alterações antes de aceitá-las** — inspecionar o código gerado é mais rápido do que reescrevê-lo.
- **Teste o aplicativo após cada etapa de implementação** para encontrar problemas enquanto ainda estão localizados.

## ✅ Parte 3 concluída

Você aprendeu a:

- Usar o Copilot para **implementar alterações em vários arquivos**
- **Iterar nos resultados** com comentários de acompanhamento específicos
- Gerenciar o **ciclo completo de uma funcionalidade** — implementação, revisão, testes e refinamento
