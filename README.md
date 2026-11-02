# PineGLT

Aplicação de chat com inteligência artificial para conversar, pesquisar informações com referências e trabalhar com projetos locais.

## Finalidade

O PineGLT busca facilitar o acesso a informações por meio de perguntas em linguagem natural. Na área de jogos, o objetivo é reunir dados pertinentes de catálogos, lojas, páginas oficiais e serviços especializados, mantendo a origem das informações disponível para consulta.

Este repositório apresenta a finalidade, o escopo e a arquitetura geral do projeto para avaliação das integrações com provedores de dados. Ele contém documentação descritiva; o código da aplicação principal não está publicado aqui.

## Funcionalidades da aplicação

- Chat com modelos locais e opções de modelos externos configuradas pelo operador.
- Interpretação do contexto da conversa e da necessidade de pesquisa.
- Pesquisa de jogos por título, plataformas, gêneros, datas e requisitos disponíveis nas fontes.
- Consulta de preços e ofertas, preservando a moeda, a região e a edição informadas.
- Apresentação de fontes e atividade observável das consultas.
- Área de projetos com arquivos reais e operações de criação e edição.

Os recursos efetivamente acessíveis dependem das credenciais, da cobertura e da disponibilidade de cada provedor. A aplicação não considera a ausência de um resultado em uma fonte como prova de inexistência.

## Integração pretendida com a CurseForge

O objetivo é permitir perguntas sobre mods dos jogos suportados pela CurseForge e consultar:

- Nome, descrição e página original do mod.
- Versões e informações dos arquivos disponíveis nos metadados.
- Compatibilidade declarada com versões do jogo e loaders.
- Dependências e datas de atualização, quando informadas pela API.

As informações serão utilizadas para formular respostas contextualizadas, com referências às páginas originais. A aplicação não oferece instalação, hospedagem ou redistribuição de arquivos de mods nesse escopo. Links direcionam às páginas dos projetos para que o usuário consulte os autores e obtenha os arquivos na plataforma de origem.

A integração possui um adaptador em desenvolvimento na aplicação principal e ainda não foi validada com uma chave CurseForge aprovada. Antes da ativação, precisam ser concluídas a revisão das condições de uso, a adequação do tratamento e da retenção dos dados e a validação dos limites de acesso. Este documento não representa aprovação, parceria ou certificação pela CurseForge ou Overwolf.

## Uso de inteligência artificial

A IA auxilia na interpretação das perguntas e na organização das informações recuperadas. Registros de fontes externas são usados como contexto para as respostas; a integração descrita não implementa treinamento de modelos com dados da CurseForge.

O sistema procura distinguir o que a fonte informa de suposições. Uma versão de arquivo não é tratada automaticamente como prova de compatibilidade com uma versão do jogo. Pedidos sem cobertura suficiente podem exigir outra fonte ou um esclarecimento específico.

## Arquitetura geral

```text
Pergunta do usuário
        |
        v
Interpretação do pedido e do contexto
        |
        v
Seleção de fontes pertinentes
        |
        v
Consulta a APIs e páginas autorizadas
        |
        v
Conferência de identidade, campos e escopo
        |
        v
Resposta com referências
```

- Interface em HTML, CSS e JavaScript.
- Servidor e módulos de pesquisa em Python.
- Integração com modelos locais por Ollama e provedores externos configuráveis.
- Adaptadores separados por provedor e tipo de informação.
- Credenciais mantidas na configuração do servidor, fora do navegador e deste repositório.

## Estado do projeto

O PineGLT está em desenvolvimento e atualmente é executado em ambiente privado. Este repositório público permite consultar sua descrição sem acesso à instalação privada. A documentação será atualizada conforme o escopo e as integrações forem alterados.

## Contato

Dúvidas sobre o projeto podem ser registradas nas Issues deste repositório.

## Referências

- [CurseForge API](https://docs.curseforge.com/rest-api/)
- [Solicitação de acesso à API CurseForge](https://support.curseforge.com/support/solutions/articles/9000208346-about-the-curseforge-api-and-how-to-apply-for-a-key)
- [IGDB API](https://api-docs.igdb.com/)
- [RAWG API](https://rawg.io/apidocs)
