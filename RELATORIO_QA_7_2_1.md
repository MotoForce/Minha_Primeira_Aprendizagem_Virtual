# Relatório de QA — Correção de pronúncia 7.2.1

## Problema observado

No leitor por síntese de voz, a palavra **COM** em caixa alta podia ser interpretada por algumas vozes como uma sigla e pronunciada letra por letra. Os anos 1º e 2º exibem as atividades em caixa alta para apoiar a alfabetização; essa apresentação visual não deve influenciar a pronúncia natural de palavras.

## Correções implementadas

1. Criada normalização da entrada de voz, separada da renderização e das respostas da criança. Palavras de 2 ou mais letras em caixa alta passam a ser enviadas ao leitor com grafia minúscula quando não são siglas reconhecidas, por exemplo `COM → com`, `PÃO → pão`, `SOL → sol`, `CASA → casa`.
2. Artigos e conectivos de uma letra, como `A`, `O` e `E`, são convertidos para leitura natural, exceto quando usados como letras em enumerações ou no contexto explícito de ensinar uma letra.
3. Letras isoladas em atividades de alfabeto continuam preservadas (`A, B, C`). Siglas técnicas reconhecidas continuam diferenciadas, sem que a regra soletra automaticamente palavras comuns.
4. A leitura do **Universo da Diversão** e a leitura das demais atividades usam o mesmo mecanismo de síntese.
5. Idioma `pt-BR` definido para o leitor, com preferência por uma voz instalada de português brasileiro, ou outra voz de português como alternativa. Não há download de voz pelo aplicativo.
6. Três botões de teste adicionados em **Sobre**: palavra, frase e letras do alfabeto.
7. Rótulos históricos da interface revisados para exibir versão 7.2.1. O contrato, armazenamento local, respostas e registros de auditoria não foram alterados.

## Testes automatizados executados

- **33 de 33 verificações específicas aprovadas**, incluindo palavras em caixa alta, frases com artigos, palavras acentuadas, siglas, letras isoladas e sequências de soletração; integração de voz em um jogo, preferência por `pt-BR` e alternativas sem voz brasileira; botões de teste e a exibição de caixa alta em 1º e 2º ano; ausência de erro JavaScript nos fluxos visitados; ausência de corte horizontal nas larguras testadas.
- **31 de 31 testes de regressão aprovados**, contemplando abertura após contrato, jogos, dicas, acertos, encaixe, memória, missões, progressão escolar, auditoria e navegação em quatro larguras.
- **4.900 rodadas** de conteúdos geradas em **35 combinações de jogo e ano**, sem falhas estruturais capturadas na amostra.
- O navegador de automação utilizou simulações de `localStorage` e de **Web Speech API** para inspecionar exatamente o texto e a configuração que o código enviou para síntese.

## Limitações e validação necessária no dispositivo

A automação **não valida a pronúncia efetivamente ouvida**, porque o timbre, as regras de abreviação e o mecanismo de síntese dependem da voz e do dispositivo (Android/Windows/navegador). Há possibilidade de indisponibilidade do sintetizador, ausência de voz instalada para português ou comportamento diferente de palavras isoladas entre fabricantes.

Teste recomendado no dispositivo real: abra **Sobre → Teste da pronúncia** e acione as três opções. O primeiro botão deverá pronunciar a palavra `com` inteira, o segundo ler uma frase naturalmente e o terceiro ler letras separadas. Se a voz continuar soletrando, verifique a voz selecionada pelo sistema e instale/ative uma voz em português brasileiro.

O funcionamento offline do áudio depende de uma voz local disponível no dispositivo; a aplicação não inclui motor de TTS próprio. Testes técnicos não garantem ausência absoluta de erros, melhoria pedagógica ou homologação escolar.

**© Nailson Rodrigues de Lima**
