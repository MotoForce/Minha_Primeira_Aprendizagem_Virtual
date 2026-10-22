# Minha Primeira Aprendizagem Virtual — versão 7.2

**Projeto educacional de Português e Matemática — 1º ao 5º ano.**
**© Nailson Rodrigues de Lima.**

## O que há nesta edição

- 165 módulos pedagógicos herdados e preservados das versões anteriores, com geração de exercícios e variações.
- 14 novos jogos visuais e 3 aventuras sequenciais voltadas principalmente ao 1º, 2º e 3º anos.
- Jogos anteriores de alfabetização, encaixe de letras e números, frações, operações, interpretação e Mercadinho Divertido.
- Mascotes ilustrativos, dicas não punitivas, álbum de conquistas, resposta por toque ou teclado e leitura do enunciado quando o navegador oferece síntese de voz.
- Tutor local por regras e biblioteca pedagógica; **não** é um modelo generativo capaz de resolver qualquer dúvida.
- Letras em CAIXA ALTA automaticamente no 1º e no 2º ano; grafia convencional do 3º ao 5º ano.
- Registro local de progresso e trilha de auditoria, contrato e política de privacidade para consulta pelo adulto.

## Instalação e uso

1. Extraia este ZIP para uma pasta; abra **index.html** em um navegador atualizado.
2. Um adulto responsável deve ler as condições, marcar os consentimentos e confirmar o aceite declaratório.
3. Escolha o ano no topo, depois **Jogos** → **Universo da Diversão** para acessar as missões.
4. Os jogos principais funcionam offline, sem serviços pagos ou Python. A sincronização opcional do catálogo BNCC requer internet e a disponibilidade da fonte externa.
5. O acompanhamento é **local ao navegador**: se trocar de dispositivo/navegador, os dados não sincronizam. Antes de limpar os dados ou reinstalar o sistema, exporte os registros que deseja guardar.

## Identidade visual

A logomarca é incluída separadamente em **logomarca.png** e também é referenciada/incorporada na experiência web conforme o HTML entregue.

## Limitações importantes

- A edição é experimental e requer validação pedagógica com alunos, famílias e professores antes de uso institucional ou venda em escala.
- O aceite digital **não** comprova juridicamente a identidade do responsável nem substitui assinatura certificada.
- A auditoria local com SHA-256 pode detectar inconsistências, mas não é inviolável nem autenticação de servidor.
- A persistência real de dados locais depende das permissões e políticas do navegador; não foi possível validá-la em uma sessão normal de navegador neste ambiente automatizado.
- O QA cobre cenários selecionados e gerações amostradas; não demonstra ausência absoluta de falhas nem eficácia de aprendizagem.

Consulte **RELATORIO_QA_7_2.md** para os resultados e limites dos testes.


## Correção 7.2.1 — leitura em voz alta

A leitura de palavras em caixa alta foi ajustada. O texto mostrado aos alunos do 1º e 2º ano continua em letras maiúsculas, porém a voz recebe palavras comuns em minúsculas para evitar que sejam interpretadas como siglas. Por exemplo, **COM** é enviado ao sintetizador como `com`. Letras isoladas e siglas identificadas permanecem distintas. O leitor principal e a leitura do Universo da Diversão agora usam o mesmo mecanismo.

Para testar no seu aparelho: abra **Sobre** e clique em **Ouvir COM**, **Ouvir frase** e **Ouvir letras**. Verifique se existe uma voz de português (Brasil) instalada. A qualidade depende do dispositivo, navegador e vozes disponíveis.

A correção não muda conteúdos, contratos, dados pessoais, gabaritos ou o formato de caixa alta das atividades.
