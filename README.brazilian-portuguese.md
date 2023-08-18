[✔]: assets/images/checkbox-small-blue.png

# Melhores Práticas em Node.js

<h1 align="center">
  <img src="assets/images/banner-2.jpg" alt="Node.js Best Practices"/>
</h1>

<br/>

<div align="center">
  <img src="https://img.shields.io/badge/⚙%20Item%20count%20-%20102%20Best%20Practices-blue.svg" alt="102 items"/> <img id="last-update-badge" src="https://img.shields.io/badge/%F0%9F%93%85%20Last%20update%20-%20July%2019%2C%202023-green.svg" alt="Última atualização: 19 de julho, 2023" /> <img src="https://img.shields.io/badge/ %E2%9C%94%20Updated%20For%20Version%20-%20Node%2019.0.0-brightgreen.svg" alt="Atualizado para Node 19.0.0"/>
</div>

<br/>

[<img src="assets/images/twitter.svg" width="16" height="16" alt="" />](https://twitter.com/nodepractices/) **Siga-nos no Twitter!** [**@nodepractices**](https://twitter.com/nodepractices/)

<br/>

Leia em diferentes idiomas: [![CN](./assets/flags/CN.png)**CN**](./README.chinese.md), [![FR](./assets/flags/FR.png)**FR**](./README.french.md), [![BR](./assets/flags/BR.png)**BR**](./README.brazilian-portuguese.md), [![RU](./assets/flags/RU.png)**RU**](./README.russian.md), [![PL](./assets/flags/PL.png)**PL**](./README.polish.md), [![JA](./assets/flags/JA.png)**JA**](./README.japanese.md), [![EU](./assets/flags/EU.png)**EU**](./README.basque.md) [(![ES](./assets/flags/ES.png)**ES**, ![HE](./assets/flags/HE.png)**HE**, ![KR](./assets/flags/KR.png)**KR** e ![TR](./assets/flags/TR.png)**TR** em progresso! )](#translations)

<br/>

# 🎊 A edição 2023 edition está aqui!

- **🛰 Modernizado para 2023**: Várias revisões de texto, novas bibliotecas recomendadas, e algumas novas boas práticas

- **✨ Foque facilmente no novo conteúdo**: Já visitou anteriormente? Procure pelas etiquetas `#new` ou `#updated` para apenas novos conteúdos

- **🔖 Curioso para ver novos exemplos? Temos um projeto inicial**: Visite [Practica.js](https://github.com/practicajs/practica), nosso exemplo de aplicação e _boilerplate_ (beta) para ver algumas práticas em ação

<br/><br/>

# Bem-vindo! 3 Coisas Que Você Precisa Saber

**1. Você está lendo dezenas dentre os melhores artigos sobre Node.js -** este repositório é um resumo e curadoria do conteúdo mais bem ranqueado sobre as melhores práticas em Node.js, bem como conteúdo escrito aqui por colaboradores

**2. Esta é a maior coletânea, e está crescendo mais a cada semana -** atualmente, são apresentadas mais de 80 melhores práticas, guias de estilo e dicas de arquitetura. Novas _issues_ e _pull requests_ são criadas diariamente para manter este livro vivo atualizado. Gostaríamos muito de ver você contribuindo aqui, seja corrigindo algum erro de código ou sugerindo novas ideias brilhantes. Veja nossas [diretrizes de escrita aqui](./.operations/writing-guidelines.md)

**3. A maioria dos tópicos possuem informações adicionais -** a maioria dos tópicos incluem um link **🔗Leia Mais** que irá expandir sobre as práticas com exemplos de códigos, citações de blogs selecionados, e mais informações.

<br/><br/>

## Índice

<details>
  <summary>
    <a href="#1-praticas-de-arquitetura-de-projeto">1. Práticas de Arquitetura de Projeto (6)</a>
  </summary>

&emsp;&emsp;[1.1 Estruture sua solução por componentes `#strategic` `#updated`](#-11-estruture-suas-solucoes-por-componentes)</br>
&emsp;&emsp;[1.2 Estratifique seus componentes em três camadas, mantenha a camada web dentro de seus limites `#strategic` `#updated`](#-12-estratifique-seus-componentes-em-tres-camadas-mantenha-a-camada-web-dentro-de-seus-limites)</br>
&emsp;&emsp;[1.3 Envolva os utilitários comuns em pacotes, considere publicá-los](#-13-envolva-os-utilitarios-comuns-em-pacotes-considere-publicalos)</br>
&emsp;&emsp;[1.4 Use configurações hierárquicas, seguras e sensíveis aos seus ambientes `#updated`](#-14-use-configuracoes-hierarquicas-seguras-e-sensiveis-aos-seus-ambientes)</br>
&emsp;&emsp;[1.5 Considere todas as consequências ao escolher o framework principal `#new`](#-15-considere-todas-as-consequencias-ao-escolher-o-framework-principal)</br>
&emsp;&emsp;[1.6 Use TypeScript espaçadamente e conscientemente `#new`](#-16-use-typescript-espaçadamente-e-conscientemente)</br>

</details>

<details>
  <summary>
    <a href="#2-praticas-de-tratamento-de-erros">2. Práticas de Tratamento de Erros (12)</a>
  </summary>

&emsp;&emsp;[2.1 Use Async-Await ou promises para tratamento de erros assíncronos](#-21-use-asyncawait-ou-promises-para-tratamento-de-erros-assincronos)</br>
&emsp;&emsp;[2.2 Extenda o objeto de Erro nativo `#strategic` `#updated`](#-22-extenda-o-objecto-de-erro-nativo)</br>
&emsp;&emsp;[2.3 Diferencie erros operacionais e erros de programação `#strategic` `#updated`](#-23-diferencie-erros-operacionais-e-erros-de-programacao)</br>
&emsp;&emsp;[2.4 Trate erros de forma centralizada, não dentro de um middleware `#strategic`](#-24-trate-erros-de-forma-centralizada-nao-dentro-de-um-middleware)</br>
&emsp;&emsp;[2.5 Documente erros de API usando a OpenAPI ou o GraphQL](#-25-documente-errors-de-api-usando-a-openapi-ou-o-graphql)</br>
&emsp;&emsp;[2.6 Finalize o processo quando um estranho aparecer `#strategic`](#-26-finalize-o-processo-quando-um-estranho-aparecer)</br>
&emsp;&emsp;[2.7 Use um agente de log maduro para aumentar a visibilidade de erros `#updated`](#-27-use-i,-agente-de-log-maduro-para-aumentar-a-visibilidade-de-erros)</br>
&emsp;&emsp;[2.8 Teste os fluxos de erro com o seu framework de teste favorito `#updated`](#-28-test-error-flows-using-your-favorite-test-framework)</br>
&emsp;&emsp;[2.9 Descubra erros e downtime usando produtos APM](#-29-descubra-erros-e-downtime-usando-produtos-apm)</br>
&emsp;&emsp;[2.10 Capture rejeições de promises não tratadas `#updated`](#-210-capture-rejeicoes-de-promises-nao-tratadas)</br>
&emsp;&emsp;[2.11 Falhe rápido, valide argumentos usando uma biblioteca dedicada](#-211-falhe-rápido-valide-argumentos-usando-uma-biblioteca-dedicada)</br>
&emsp;&emsp;[2.12 Sempre use 'await' ao retornar promises para evitar um rastreamento parcial da pilha de erro `#new`](#-212-sempre-use-await-ao-retornar-promises-para-evitar-um-rastreamento-parcial-da-pilha-de-erro)</br>
&emsp;&emsp;[2.13 Inscreva-se aos eventos de erro de emissores de eventos `#new`](#-213-inscrevase-aos-eventos-de-erro-de-emissores-de-eventos)</br>

</details>

<details>
  <summary>
    <a href="#3-praticas-de-estilo-de-codigo">3. Práticas de Estilo de Código (12)</a>
  </summary>

&emsp;&emsp;[3.1 Use ESLint `#strategic`](#-31-use-eslint)</br>
&emsp;&emsp;[3.2 Use as extensões de eslint do Node.js `#updated`](#-32-use-as-extensoes-de-eslint-do-nodejs)</br>
&emsp;&emsp;[3.3 Abra as chaves de um bloco de código na mesma linha](#-33-abra-as-chaves-de-um-bloco-de-codigo-na-mesma-linha)</br>
&emsp;&emsp;[3.4 Separe suas declarações corretamente](#-34-separe-suas-declaracoes-corretamente)</br>
&emsp;&emsp;[3.5 Nomeie suas funções](#-35-nomeie-suas-funcoes)</br>
&emsp;&emsp;[3.6 Use convenções de nomenclatura para variáveis, constantes, funções e classes](#-36-use-convencoes-de-nomenclatura-para-variaveis-constantes-funcoes-e-classes)</br>
&emsp;&emsp;[3.7 Prefira const ao let. Esqueça o var](#-37-prefira-const-ao-let-esqueca-o-var)</br>
&emsp;&emsp;[3.8 Importe módulos primeiro, não dentro de funções](#-38-importe-modulos-primeiro-nao-dentro-de-funcoes)</br>
&emsp;&emsp;[3.9 Defina um ponto de entrada explícito para um módulo/pasta `#updated`](#-39-defina-um-ponto-de-entrada-explicito-para-um-modulopasta)</br>
&emsp;&emsp;[3.10 Use o operador ===](#-310-use-o-operador-)</br>
&emsp;&emsp;[3.11 Use Async Await, evite callbacks `#strategic`](#-311-use-async-await-evite-callbacks)</br>
&emsp;&emsp;[3.12 Use expressões _arrow functions_ (=>)](#-312-use-expressoes-arrow-functions-)</br>
&emsp;&emsp;[3.13 Evite efeitos fora de funções `#new`](#-313-evite-efeitos-fora-de-funcoes)</br>

</details>

<details>
  <summary>
    <a href="#4-praticas-de-testes-e-qualidade-geral">4. Práticas de Testes e Qualidade Geral (13)</a>
  </summary>

&emsp;&emsp;[4.1 No mínimo, escreva testes de API (componente) `#strategic`](#-41-no-minimo-escreva-testes-de-api-componente)</br>
&emsp;&emsp;[4.2 Inclua 3 partes em cada nome de teste `#new`](#-42-inclua-3-partes-em-cada-nome-de-teste)</br>
&emsp;&emsp;[4.3 Estuture testes a partir do padrão AAA `#strategic`](#-43-estruture-testes-a-partir-do-padrao-aaa)</br>
&emsp;&emsp;[4.4 Garanta que a versão Node esteja unificada `#new`](#-44-garanta-que-a-versao-node-esteja-unificada)</br>
&emsp;&emsp;[4.5 Evite dados fixos e seeds em testes, adicione dados a cada teste `#strategic`](#-45-evite-dados-fixos-e-seeds-em-testes-adicione-dados-a-cada-teste)</br>
&emsp;&emsp;[4.6 Rotule seus testes `#advanced`](#-46-rotule-seus-testes)</br>
&emsp;&emsp;[4.7 Verifique suas coberturas de testes, isso te ajuda a identificar padrões incorretos de teste](#-47-verifique-suas-coberturas-de-testes-isso-te-ajuda-a-identificar-padroes-incorretos-de-testes)</br>
&emsp;&emsp;[4.8 Use ambientes à nível de produção para testes e2e ](#-48-use-ambientes-a-nivel-de-producao-para-testes-e2e)</br>
&emsp;&emsp;[4.9 Refatore regularmente usando ferramentas de análise estática](#-49-refatore-regularmente-usando-ferramentas-de-analise-estatica)</br>
&emsp;&emsp;[4.10 Simule respostas de serviços HTTP externos `#new` `#advanced`](#-410-simule-respostas-de-servicos-http-externos)</br>
&emsp;&emsp;[4.11 Teste seus 'middlewares' isoladamente](#-411-teste-seus-middlewares-isoladamente)</br>
&emsp;&emsp;[4.12 Especifique uma porta em produção, randomize em testes `#new`](#-412-especifique-uma-porta-em-producao-randomize-em-testes)</br>
&emsp;&emsp;[4.13 Teste os cinco resultados possíveis `#strategic` `#new`](#-413-teste-os-cinco-resultados-possiveis)</br>

</details>

<details>
  <summary>
    <a href="#5-praticas-ao-escalar-para-producao">5. Práticas ao escalar para Produção (19)</a>
  </summary>

&emsp;&emsp;[5.1. Monitoramento `#strategic`](#-51-monitoramento)</br>
&emsp;&emsp;[5.2. Aumente a observabilidade usando smart logging `#strategic`](#-52-aumente-a-observabilidade-usando-smart-logging)</br>
&emsp;&emsp;[5.3. Delegue tudo o que for possível (ex.: gzip, SSL) a um proxy reverso `#strategic`](#-53-delegue-tudo-o-quer-for-possivel-ex-gzip-ssl-a-um-proxy-reverso)</br>
&emsp;&emsp;[5.4. Bloqueie as dependências](#-54-bloqueie-as-dependencias)</br>
&emsp;&emsp;[5.5. Poupe tempo de atividade do processo usando a ferramenta certa](#-55-poupe-tempo-de-atividade-do-processo-usando-a-ferramenta-certa)</br>
&emsp;&emsp;[5.6. Utilize todos os núcleos do processador](#-56-utilize-todos-os-núcleos-do-processador)</br>
&emsp;&emsp;[5.7. Crie um ‘endpoint de manutenção’](#-57-crie-um-endpoint-de-manutencao)</br>
&emsp;&emsp;[5.8. Descubra o que está oculto usando produtos APM `#advanced` `#updated`](#-58-descubra-o-que-esta-oculto-usando-produtos-apm)</br>
&emsp;&emsp;[5.9. Deixe seu código pronto para produção](#-59-deixe-seu-codigo-pronto-para-producao)</br>
&emsp;&emsp;[5.10. Meça e proteja o uso de memória `#advanced`](#-510-meca-e-proteja-o-uso-de-memoria)</br>
&emsp;&emsp;[5.11. Deixe seus recursos de frontend fora do Node](#-511-deixe-seus-recursos-de-frontend-fora-do-node)</br>
&emsp;&emsp;[5.12. Aspire a ser stateless `#strategic`](#-512-aspire-a-ser-stateless)</br>
&emsp;&emsp;[5.13. Utilize ferramentas que detectam vulnerabilidades automaticamente](#-513-utilize-ferramentas-que-detectam-vulnerabilidades-automaticamente)</br>
&emsp;&emsp;[5.14. Atribua 'transaction-id's para cada declaração de log `#advanced`](#-514-atribua-transaction-ids-para-cada-declaracao-de-log)</br>
&emsp;&emsp;[5.15. Defina NODE_ENV=production](#-515-defina-node_envproduction)</br>
&emsp;&emsp;[5.16. Projete deploys automáticos, atômicos e com tempo de inatividade zero `#advanced`](#-516-projete-deploys-automáticos-atômicos-e-com-tempo-de-inatividade-zero)</br>
&emsp;&emsp;[5.17. Use uma versão LTS do Node.js](#-517-use-uma-versao-lts-do-nodejs)</br>
&emsp;&emsp;[5.18. Direcione logs para o stdout, evite direcioná-los para dentro do aplicativo `#updated`](#-518-direcione-logs-para-o-stdout-evite-direcionalos-para-dentro-do-aplicativo)</br>
&emsp;&emsp;[5.19. Instale seus pacotes com npm ci `#new`](#-519-instalce-seus-pacotes-com-npm-ci)</br>

</details>

<details>
  <summary>
    <a href="#6-praticas-de-seguranca">6. Práticas de Seguraça (25)</a>
  </summary>

&emsp;&emsp;[6.1. Adote as regras de segurança do linter](#-61-adote-as-regras-de-segurança-do-linter)</br>
&emsp;&emsp;[6.2. Limite requisições simultâneas usando um middleware](#-62-limite-requisicoes-simultaneas-usando-um-middleware)</br>
&emsp;&emsp;[6.3. Extraia segredos dos arquivos de configuração ou use pacotes para criptografá-los `#strategic`](#-63-extraia-segredos-dos-arquivos-de-configuracao-ou-use-pacotes-para-criptografalos)</br>
&emsp;&emsp;[6.4. Previna-se contra vulnerabilidades de query injection com bibliotecas ORM/ODM `#strategic`](#-64-previnase-contra-vulnerabilidades-de-query-injection-com-bibliotecas-ormodm)</br>
&emsp;&emsp;[6.5. Coleção genérica de boas práticas de segurança](#-65-colecao-generica-de-boas-praticas-de-seguranca)</br>
&emsp;&emsp;[6.6. Ajuste os headers de resposta HTTP para uma segurança aprimorada](#-66-ajuste-os-headers-de-resposta-http-para-uma-seguranca-aprimorada)</br>
&emsp;&emsp;[6.7. Inspecione constante e automaticamente por dependências vulneráveis `#strategic`](#-67-inspecione-constante-e-automaticamente-por-dependencias-vulneraveis)</br>
&emsp;&emsp;[6.8. Proteja Senhas e Segredos de Usuários com bcrypt ou scrypt `#strategic`](#-68-proteja-senhas-e-segredos-de-usuarios-com-bcrypt-ou-scrypt)</br>
&emsp;&emsp;[6.9. Escape saídas HTML, JS e CSS](#-69-escape-saidas-html-js-and-css)</br>
&emsp;&emsp;[6.10. Valide os esquemas de entrada JSON `#strategic`](#-610-valide-os-esquemas-de-entrada-json)</br>
&emsp;&emsp;[6.11. Ajude a inserir JWTs em listas de restrição](#-611-ajude-a-inserir-jwts-em-listaas-de-restricao)</br>
&emsp;&emsp;[6.12. Previna-se de ataques de força bruta contra autorização `#advanced`](#-612-previnase-de-ataques-de-forca-bruta-contra-autorizacao)</br>
&emsp;&emsp;[6.13. Execute o Node.js como um usuário não-root](#-613-execute-o-nodejs-como-um-usuario-naoroot)</br>
&emsp;&emsp;[6.14. Limite o tamanho do payload usando um proxy reverso ou um middleware](#-614-limite-o-tamanho-do-payload-usando-um-proxy-reverso-ou-um-middleware)</br>
&emsp;&emsp;[6.15. Evite instruções eval do JavaScript](#-615-evite-instrucoes-eval-do-javascript)</br>
&emsp;&emsp;[6.16. Evite que RegEx maliciosos sobrecarreguem sua execução de thread único](#-616-evite-que-regex-maliciosos-sobrecarreguem-sua-execucao-de-thread-unico)</br>
&emsp;&emsp;[6.17. Evite o carregamento de módulos usando uma variável](#-617-evite-o-carregamento-de-modulos-usando-uma-variavel)</br>
&emsp;&emsp;[6.18. Execute códigos não seguros em uma sandbox](#-618-execute-codigos-nao-seguros-em-uma-sandbox)</br>
&emsp;&emsp;[6.19. Tome cuidado extra ao trabalhar com processos filhos `#advanced`](#-619-take-extra-care-when-working-with-child-processes)</br>
&emsp;&emsp;[6.20. Oculte detalhes de erros dos usuários](#-620-hide-error-details-from-clients)</br>
&emsp;&emsp;[6.21. Configure 2FA para o npm ou Yarn `#strategic`](#-621-configure-2fa-for-npm-or-yarn)</br>
&emsp;&emsp;[6.22. Modifique as configurações do middleware de sessão](#-622-modify-session-middleware-settings)</br>
&emsp;&emsp;[6.23. Evite ataques do DOS definindo explicitamente quando um processo deve falhar `#advanced`](#-623-avoid-dos-attacks-by-explicitly-setting-when-a-process-should-crash)</br>
&emsp;&emsp;[6.24. Impeça redirecionamentos não seguros](#-624-prevent-unsafe-redirects)</br>
&emsp;&emsp;[6.25. Evite publicar segredos no registro do npm](#-625-avoid-publishing-secrets-to-the-npm-registry)</br>
&emsp;&emsp;[6.26. Inspecione por pacotes defasados](#-626-inspecione-por-pacotes-defasados)</br>
&emsp;&emsp;[6.27. Importe módulos nativos usando o protocolo 'node:' `#new`](#-627-importe-modulos-nativos-usando-o-protocolo-node)</br>

</details>

<details>
  <summary>
    <a href="#7-praticas-de-performance">7. Práticas de Performance (2) (Work In Progress️ ✍️)</a>
  </summary>

&emsp;&emsp;[7.1. Não bloqueie o Event Loop](#-71-nao-bloqueie-o-event-loop)</br>
&emsp;&emsp;[7.2. Prefira métodos JS nativos ao invés de utilitários de usuário, como o Lodash](#-72-prefire-metodos-js-nativos-ao-inves-de-utilitarios-de-usuoario-como-o-lodash)</br>

</details>

<details>
  <summary>
    <a href="#8-praticas-em-docker">8. Práticas em Docker (15)</a>
  </summary>

&emsp;&emsp;[8.1 Use builds de estágios múltiplos para imagens Docker mais compactas e seguras `#strategic`](#-81-use-builds-de-multiplos-estagios-para-imagens-docker-mais-compactas-e-seguras)</br>
&emsp;&emsp;[8.2. Inicialize usando comandos node, evite npm start](#-82-inicialize-usando-comandos-node-evite-npm-start)</br>
&emsp;&emsp;[8.3. Deixe que o momento de execução do Docker lide com replicações e o tempo de atividade `#strategic`](#-83-dexe-que-o-momento-de-execucao-do-docker-life-com-replicacoes-e-o-tempo-de-atividade)</br>
&emsp;&emsp;[8.4. Use .dockerignore para prevenir segredos vazados](#-84-use-dockerignore-para-prevenir-segredos-vazados)</br>
&emsp;&emsp;[8.5. Despolua as dependências antes de subir para produção](#-85-despolua-as-dependencias-antes-de-subir-para-producao)</br>
&emsp;&emsp;[8.6. Encerre a execução de forma inteligente e segura `#advanced`](#-86-encerre-a-execucao-de-forma-inteligente-e-segura)</br>
&emsp;&emsp;[8.7. Defina limites de memória usando ambos Docker e a v8 `#advanced` `#strategic`](#-87-defina-limites-de-memoria-usando-ambos-docker-e-a-v8)</br>
&emsp;&emsp;[8.8. Planeje-se para um uso eficiente de cache](#-88-planejese-para-um-uso-eficiente-de-cache)</br>
&emsp;&emsp;[8.9. Use etiquetas de imagem explícitas, evite a etiqueta latest](#-89-use-etiquetas-de-imagem-eplicitas-evite-a-etiqueta-latest)</br>
&emsp;&emsp;[8.10. Prefira imagens Docker base menores](#-810-prefira-imagens-docker-base-menores)</br>
&emsp;&emsp;[8.11. Limpe os segredos de tempo de compilação, evite segredos em args `#strategic` `#new`](#-811-limpe-os-segredos-de-tempo-de-compilacao-evite-segredos-em-args)</br>
&emsp;&emsp;[8.12. Escaneie imagens por camadas múltiplas de vulnerabilidades `#advanced`](#-812-escaneie-imagens-por-camadas-multiplas-de-vulnerabilidades)</br>
&emsp;&emsp;[8.13 Despolua o cache NODE_MODULE](#-813-despolua-o-cache-node_module)</br>
&emsp;&emsp;[8.14. Práticas genéricas em Docker](#-814-praticas-genericas-em-docker)</br>
&emsp;&emsp;[8.15. Despolua seu Dockerfile `#new`](#-815-despolua-seu-dockerfile)</br>

</details>

<br/><br/>

# `1. Práticas de Estrutura de Projeto`

## ![✔] 1.1 Estruture sua solução por componentes

### `📝 #updated`

**TL;DR:** A raíz de um sistema deve conter pastas ou repositórios que representem módulos de negócios de porte razoável. Cada componente representa uma esfera do produt (ex.: contextos limitados), como 'user-component', 'order-component', etc. CXada componente possui sua própria API, lógica, e banco de dados lógico, Qual a vantagem significativa? Com um componente autônomo, cada mudança é realizada através de escopos menores e mais ganulares — a sobrecarga mental, fricção de desenvolvimento, e o temor por deploys são bem menores e melhores. Por conseguência, desenvolvedores podem trabalhar bem mais rápido. Isso não necessariamente demanda separação física e pode ser alcançado usando um Monorepo ou com uma estrutura de repositórios múltiplos.

```bash
my-system
├─ apps (components)
│  ├─ orders
│  ├─ users
│  ├─ payments
├─ libraries (generic cross-component functionality)
│  ├─ logger
│  ├─ authenticator
```

**Caso contrário:** quando artefatos de vários módulos/tópicos são embaralhados, há grandes chances de um sistema ultra-justo 'espaguetado'. Por exemplo, numa arquitetura no qual um 'module-a controller' pode chamar um 'module-b service', não há limites claros de modularidade — cada alteração no código pode afetar qualquer outra coisa. Com esta abordagem, desenvolvedores que programam novos recursos têm dificuldade em reconhecer o escopo e impacto de suas alterações. Consequentemente, eles temem quebrar outros módulos, e cada deploy se torna mais lento e arriscado.

🔗 [**Leia mais: estruture por componentes**](./sections/projectstructre/breakintcomponents.brazilian-portuguese.md)

<br/><br/>

## ![✔] 1.2 Estratifique seus componentes em três camadas, mantenha a camada web dentro de seus limites

### `📝 #updated`

**TL;DR:** Cada componente deve conter 'camadas' — uma pasta decidada para preocupações comuns: 'entry-point' onde o controlador vive, 'domain' onde a lógica vive, e 'data-access'. O princípio primário das arquiteturas mais populares é separar as preocupações técnicas (ex.: HTTP, DB, etc) da lógica pura da aplicação para que o desenvolvedor possa programar mais recursos sem se preocupar com as preocupações infraestruturais. Colocar cada preocupação em uma pasta dedicada, também conhecido como [padrão de camada tripla](https://pt.wikipedia.org/wiki/Arquitetura_multicamada), é a maneira _mais simples_ de atender a este objetivo.

```bash
my-system
├─ apps (components)
│  ├─ component-a
   │  ├─ entry-points
   │  │  ├─ api # o controlador fica aqui
   │  │  ├─ message-queue # mensagens ao consumidor ficam aqui
   │  ├─ domain # recursos e fluxos: DTO (Objeto de Transferência de Dados), serviços, lógica
   │  ├─ data-access # chamadas ao banco de dados sem ORM
```

**Caso contrário:** É comum ver desenvolvedores passando objetos web como request/response para funções na camada de domínio/lógica - isso viola o princípio de separação e torna mais difícil acessar posteriormente o código de lógica por outros clientes como código de teste, jobs agendados, filas de mensagens, etc.

🔗 [**Leia Mais: seu app em camadas**](./sections/projectstructre/createlayers.brazilian-portuguese.md)

<br/><br/>

## ![✔] 1.3 Envolva os utilitários comuns como pacotes npm, considere publicá-los

**TL;DR:** Coloque todos os módulos reutilizáveis em uma pasta dedicada, por exemplo, "libraries", e embaixo de cada módulo em sua própria pasta, por exemplo, "/libraries/logger". Faça do módulo um pacote independente com seu próprio arquivo `package.json` para aumentar a encapsulação do módulo e permitir a publicação futura em um repositório. Em uma configuração de Monorepo, os módulos podem ser consumidos por 'npm linking' para seus caminhos físicos, usando ts-paths ou publicando e instalando de um repositório de gerenciador de pacotes como o registro npm

```bash
my-system
├─ apps (components)
  │  ├─ component-a
├─ libraries # (funcionalidade genérica entre componentes)
│  ├─ logger
│  │  ├─ package.json
│  │  ├─ src
│  │  │ ├─ index.js

```

**Caso contrário:** Os clientes de um módulo podem importar e se acoplar à funcionalidade interna de um módulo. Com um `package.json` na raíz, pode-se definir um `package.json.main` ou `package.json.exports` para explicitar quais arquivos e funções fazem parte da interface pública.

🔗 [**Leia Mais: Estruture por recurso**](./sections/projectstructre/wraputilities.brazilian-portuguese.md)

<br/><br/>

## ![✔] 1.4 Use configurações hierárquicas, seguras e sensíveis aos seus ambientes

### `📝 #updated`

**TL;DR:** Uma configuração de setup impecável deve garantir que (a) as chaves possam ser lidas a partir do arquivo E TAMBÉM da variáveis de ambiente (b) os segredos sejam mantidos fora do código consolidado (c) a configuração é hierárquica para facilitar a localização (d) suporte para tipagens (e) validação para falhar rapidamente (f) Especificar um padrão para cada chave. Existem alguns pacotes que podem auxiliar a marcar a maioria destes tópicos, como [convict](https://www.npmjs.com/package/convict), [env-var](https://github.com/evanshortiss/env-var), [zod](https://github.com/colinhacks/zod), entre outros.

**Caso contrário:** Considere uma variável de ambiente obrigatória que não foi fornecida. O aplicativo inicializa com sucesso e atende às solicitações, algumas informações já estão persistidas no banco de dados. Então, percebe-se que, sem essa chave obrigatória, a solicitação não pode ser concluída, deixando a aplicação em um estado sujo.

🔗 [**Leia Mais: boas práticas de configuração**](./sections/projectstructre/configguide.brazilian-portuguese.md)

<br/><br/>

## ![✔] 1.5 Considere todas as consequências ao escolher o framework principal

### `🌟 #new`

**TL;DR:** Ao construir aplicações e APIs, utilizar um framework é obrigatório. É fácil ignorar frameworks alternativos ou considerações importantes e, finalmente, acabar em uma opção sub-ótima. A partir de 2023/2024, acreditamos que estes quatro frameworks valem a pena considerar: [Nest.js](https://nestjs.com/), [Fastify](https://www.fastify.io/), [express](https://expressjs.com/), e [Koa](https://koajs.com/). Clique em "Leia Mais" abaixo para uma análise detalhada dos prós e contras de cada framework. Simplificando, acreditamos que Nest.js é a melhor opção para equipes que desejam ir para a OOP e/ou construir aplicações de grande escala que não podem ser particionadas em componentes menores e autônomos. Fastify é nossa recomendação para aplicações com componentes de tamanho razoável (ex.: Microsserviços) que são construídos em torno de mecânicas simples do Node.js. Leia nosso [guia completo de considerações aqui](./sections/projectstructre/choose-framework.brazilian-portuguese.md).

**Caso contrário:** Por causa da quantidade esmagadora de considerações, é fácil tomar decisões com base em informações parciais e comparar maçãs com laranjas. Por exemplo, acredita-se que o Fastify é um servidor web mínimo que deve ser comparado apenas com o express. Na realidade, é um framework rico com muitos plugins oficiais que cobrem diversas preocupações.

🔗 [**Read More: Escolhendo o framework certo**](./sections/projectstructre/choose-framework.brazilian-portuguese.md)

## ![✔] 1.6 Use TypeScript espaçadamente e conscientemente

### `🌟 #new`

**TL;DR:** Programar sem segurança de tipagem não é mais uma opção, TypeScript é a alternativa mais popular nesta missão. Use-o para definir variáveis e tipos de retorno de funções. Dito isso, também é uma espada de dois gumes que pode _encorajar_ a complexidade com suas ~ 50 palavras-chave adicionais e recursos sofisticados. Considere usá-lo com moderação, principalmente com tipagens simples, e utilize recursos avançados apenas quando surgir uma necessidade real.

**Caso contrário:** [Pesquisas](https://earlbarr.com/publications/typestudy.pdf) apontam que o uso do TypeScript pode ajudar a detectar ~ 20% dos bugs mais cedo. Sem ele, a experiência do desenvolvedor no IDE também é intolerável. Por outro lado, 80% dos outros bugs não foram descobertos usando tipagens. Consequentemente, a sintaxe tipada é valiosa, mas limitada. Somente testes eficientes podem descobrir todo o espectro de bugs, incluindo bugs relacionados a tipagens. O TypeScrit também pode causar um efeito contrário: recursos de código sofisticados provavelmente aumentarão a complexidade do código, o que por si só aumenta tanto a quantidade de bugs, quanto o tempo médio de correção de bugs.

🔗 [**Read More: Considerações relacionadas ao TypeScript**](./sections/projectstructre/typescript-considerations.brazilian-portuguese.md)

<br/><br/><br/>

<p align="right"><a href="#índice">⬆ Voltar ao topo</a></p>

# `2. Práticas de Tratamento de Erros`

## ![✔] 2.1 Utilize Async-Await ou promises para tratamento de erros assíncronos

**TL;DR:** Tratar erros assíncronos no estilo callback provavelmente é o caminho mais rápido para o inferno (também conhecido como a pyramid of doom - ou pirâmide da desgraça em bom português). O melhor presente que você pode dar ao seu código é utilizar uma biblioteca respeitável de promise ou async-await, que proporciona uma sintaxe de código muito mais compacta e familiar, como o try-catch.

**Caso contrário:** O estilo de callback do Node.js, function(err, response), é um caminho promissor para um código insustentável devido à combinação de manipulação de erro com código casual, aninhamento excessivo e padrões de codificação inadequados.

🔗 [**Leia Mais: evitando callbacks**](./sections/errorhandling/asyncerrorhandling.brazilian-portuguese.md)

<br/><br/>

## ![✔] 2.2 Utilize apenas objetos de erro interno

**TL;DR:** Muitos geram erros como uma string ou como algum tipo personalizado - isso complica a lógica de tratamento de erros e a interoperabilidade entre módulos. Se você rejeita uma promise, lance uma mensagem de erro ou uma exceção - utilizando somente o objeto de erro interno aumentará a uniformidade e evitará a perda de informações.

**Caso contrário:** Ao invocar algum componente, sendo incerto qual tipo de erro irá retornar - isso faz com que o tratamento de erros seja muito mais difícil. Até pior, usar tipos personalizados para descrever erros pode levar à perda de informações de erros críticos, como o stack trace!

🔗 [**Leia Mais: usando o objeto interno de erro**](./sections/errorhandling/useonlythebuiltinerror.brazilian-portuguese.md)

<br/><br/>

## ![✔] 2.3 Diferencie erros operacionais vs erros de programação

**TL;DR:** Erros operacionais (ex: API recebeu um input inválido) referem-se a casos onde o impacto do erro é totalmente compreendido e pode ser tratado com cuidado. Por outro lado, erro de programação (ex: tentar ler uma variável não definida) refere-se a falhas de código desconhecidas que ditam para reiniciar a aplicação.

**Caso contrário:** Você pode sempre reiniciar o aplicativo quando um erro aparecer, mas por que derrubar aproximadamente 5000 usuários que estavam online por causa de um pequeno erro operacional previsto? O contrário também não é ideal - manter a aplicação rodando quando um problema desconhecido (erro de programação) ocorreu, pode levar para um comportamento não esperado. Diferenciá-los, permite agir com tato e aplicar uma abordagem equilibrada baseada no dado contexto.

🔗 [**Leia Mais: erros operacionais vs erros de programação**](./sections/errorhandling/operationalvsprogrammererror.brazilian-portuguese.md)

<br/><br/>

## ![✔] 2.4 Trate erros de forma centralizada, não dentro de um middleware do Express

**TL;DR:** A lógica de tratamento de erros, bem como email para administrador e registros (logs), deve ser encapsulada em um objeto dedicado e centralizado que todos os endpoints (por exemplo, middleware do Express, cron jobs, testes unitários) chamem quando um erro é recebido.

**Caso contrário:** Não tratar os erros em um mesmo lugar irá levar à duplicidade de código, e provavelmente, a erros tratados incorretamente.

🔗 [**Leia Mais: tratando erros de forma centralizada**](./sections/errorhandling/centralizedhandling.brazilian-portuguese.md)

<br/><br/>

## ![✔] 2.5 Documente erros de API usando a OpenAPI ou o GraphQL

**TL;DR:** Permita que os clientes de sua API saibam quais erros podem ser retornados para que eles possam lidar com esses detalhes, sem causar falhas. Para RESTful APIs geralmente, isto é feito com frameworks de documentação REST API, como o Swagger. Se você está usando GraphQL, você também pode utilizar seu esquema e comentários.

**Caso contrário:** Um cliente de uma API pode decidir travar e reiniciar, apenas pelo motivo de ter recebido de volta um erro que não conseguiu entender. Nota: o visitante de sua API pode ser você (muito comum em um ambiente de microsserviço).

🔗 [**Leia Mais: documentando erros de API no Swagger ou GraphQL**](./sections/errorhandling/documentingusingswagger.brazilian-portuguese.md)

<br/><br/>

## ![✔] 2.6 Finalize o processo quando um estranho aparecer

**TL;DR:** Quando ocorre um erro desconhecido (um erro de programação, veja a melhor prática #3) - há incerteza sobre a integridade da aplicação. Uma prática comum sugere reiniciar cuidadosamente o processo utilizando uma ferramenta de “reinicialização” como [Forever](https://www.npmjs.com/package/forever) e [PM2](http://pm2.keymetrics.io/).

**Caso contrário:** Quando uma exceção desconhecida é lançada, algum objeto pode estar com defeito (por exemplo, um emissor de evento que é usado globalmente e não dispara mais eventos devido a alguma falha interna) e todas as requisições futuras podem falhar ou se comportar loucamente.

🔗 [**Leia Mais: finalizando o processo**](./sections/errorhandling/shuttingtheprocess.brazilian-portuguese.md)

<br/><br/>

## ![✔] 2.7 Utilize um agente de log maduro para aumentar a visibilidade de erros

**TL;DR:** Um conjunto de ferramentas de registro maduras como [Pino](https://www.npmjs.com/package/pino), [Winston](https://www.npmjs.com/package/winston), [Bunyan](https://www.npmjs.com/package/bunyan) ou [Log4js](https://www.npmjs.com/package/log4js), irão acelerar a descoberta e entendimento de erros. Portanto, esqueça o console.log.

**Caso contrário:** Ficar procurando através de console.logs ou manualmente em arquivos de texto confusos sem utilizar ferramentas de consulta ou um visualizador de log decente, pode mantê-lo ocupado até tarde.

🔗 [**Leia Mais: usando um logger maduro**](./sections/errorhandling/usematurelogger.brazilian-portuguese.md)

<br/><br/>

## ![✔] 2.8 Teste os fluxos de erro com o seu framework de teste favorito

**TL;DR:** Se o analista de QA ou o desenvolvedor de testes - Certifique-se de que seu código não atenda apenas o cenário positivo, mas também trate e retorne os erros corretos. Frameworks de teste como Mocha e Chai podem lidar com isso facilmente (veja exemplos de códigos no “Gist popup”)

**Caso contrário:** Sem testes, seja automático ou manual, não podemos confiar em nosso código para retornar os erros certos. Sem erros significantes, não há tratamento de erros.

🔗 [**Leia Mais: fluxos de testes de erros**](./sections/errorhandling/testingerrorflows.brazilian-portuguese.md)

<br/><br/>

## ![✔] 2.9 Descubra erros e downtime usando APM

**TL;DR:** Produtos de monitoramento e desempenho (também conhecido como APM), avaliam sua base de código ou API de forma proativa, para que possam destacar automaticamente erros, falhas e lentidões não percebidos.

**Caso contrário:** Você pode gastar muito esforço medindo o desempenho e os tempos de inatividade (downtime) da API. Provavelmente, você nunca saberá quais são suas partes de código mais lentas no cenário real e como elas afetam o UX.

🔗 [**Leia Mais: usando APM**](./sections/errorhandling/apmproducts.brazilian-portuguese.md)

<br/><br/>

## ![✔] 2.10 Capture rejeições de promises não tratadas

**TL;DR:** Qualquer exceção lançada dentro de uma promise será descartada, a menos que o desenvolvedor não se esqueça de tratá-la explicitamente. Mesmo que seu código esteja inscrito no process.uncaughtException! Supere isso, registrando no evento process.unhandledRejection.

**Caso contrário:** Seus erros serão engolidos e não vão deixar rastros. Nada para se preocupar.

🔗 [**Leia Mais: capturando rejeições de promises não tratadas**](./sections/errorhandling/catchunhandledpromiserejection.brazilian-portuguese.md)

<br/><br/>

## ![✔] 2.11 Falhe rápido, valide argumentos usando uma biblioteca dedicada

**TL;DR:** Isto deveria fazer parte das melhores práticas de Express - Confirme a entrada da API para evitar erros desagradáveis ​​que são muito mais difíceis de acompanhar mais tarde. A validação de código geralmente é entediante ao menos que você esteja utilizando uma biblioteca de ajuda bem legal, como a Joi.

**Caso contrário:** Considere isto: sua função espera receber um “Desconto” como argumento numérico que foi esquecido de passar. Mais adiante, seu código verifica se Desconto!=0 (valor do desconto permitido é maior que zero). Depois, irá permitir que o usuário desfrute de um desconto. Meu Deus, que baita bug. Entendeu?

🔗 [**Leia Mais: falhando rápido**](./sections/errorhandling/failfast.brazilian-portuguese.md)

<br/><br/>

## ![✔] 2.12 Sempre use 'await' antes de retornar as 'promises' para evitar um rastreamento parcial da pilha de erro

**TL;DR:** Sempre use `return await` quando retornar uma 'promise' para beneficiar o rastreamento completo da pilha de erro. Se um função retorna uma 'promise', essa função deve ser declarada como função `async` e  explicitamente `await` na `promise` antes de devolvê-la

**Caso contrário:** Uma função que retorna uma `promise` sem o `await` não aparecerá na pilha de erro.
A ausência dessas informações provavelmente complicariam a compreensão do fluxo que leva ao erro,
especialmente se a causa do comportamento anormal estiver dentro da função ausente

🔗 [**Leia Mais: retornando promises**](./sections/errorhandling/returningpromises.md)

<br/><br/><br/>

<p align="right"><a href="#índice">⬆ Voltar ao topo</a></p>

# `3. Práticas de Estilo de Código`

## ![✔] 3.1 Use ESLint

**TL;DR:** O [ESLint](https://eslint.org) é de fato o padrão para verificar possíveis erros e consertar o estilo de código, não apenas para identificar problemas básicos de espaçamento, mas também para detectar antipadrões de código, como desenvolvedores lançando erros sem classificação. Embora o ESLint possa corrigir automaticamente estilos de código, outra ferramentas como o [prettier](https://www.npmjs.com/package/prettier) e o [beautify](https://www.npmjs.com/package/js-beautify) são mais poderosos no quesito correção de formatação e trabalham em conjunto com o ESLint.

**Caso contrário:** Desenvolvedores irão focar nas preocupações tediosas de espaçamento e largura de linha e o tempo poderá ser desperdiçado pensando sobre o estilo de código do projeto.

🔗 [**Leia Mais: Usando ESLint e Prettier**](./sections/codestylepractices/eslint_prettier.brazilian-portuguese.md)

<br/><br/>

## ![✔] 3.2 Use as extensões de eslint do Node.js

**TL;DR:** Além das regras padrões do ESLint que cobrem somente o Vanilla JS, adicione plug-ins específicos do Node, como o [eslint-plugin-node](https://www.npmjs.com/package/eslint-plugin-node), o [eslint-plugin-mocha](https://www.npmjs.com/package/eslint-plugin-mocha) e o [eslint-plugin-node-security](https://www.npmjs.com/package/eslint-plugin-security)

**Caso contrário:** Muitos padrões de código do Node.js com falha podem escapar do radar. Por exemplo, desenvolvedores podem chamar arquivos fazendo o require(variavelComoCaminho) com uma determinada variável como caminho, o que permite que invasores executem qualquer script JS. Os linters do Node.js podem detectar tais padrões e reclamar cedo.

<br/><br/>

## ![✔] 3.3 Abra as chaves de um bloco de código na mesma linha

**TL;DR:** As chaves que abrem um bloco de código devem estar na mesma linha da instrução de abertura

### Exemplo de Código

```javascript
// Do
function someFunction() {
  // code block
}

// Avoid
function someFunction()
{
  // code block
}
```

**Caso contrário:** Evitar esta recomendação pode levar a resultados inesperados, como visto nesta thread do StackOverflow:

🔗 [**Leia Mais:** "Por que os resultados variam com base no posicionamento da chave?" (Stackoverflow)](https://stackoverflow.com/questions/3641519/why-does-a-results-vary-based-on-curly-brace-placement)

<br/><br/>

## ![✔] 3.4 Separe suas declarações corretamente

Não importa se você usa ponto-e-vírgula ou não para separar suas declarações, conhecer as armadilhas comuns de quebras de linha impróprias ou inserção automática de ponto e vírgula, irá ajudá-lo a eliminar erros regulares de sintaxe.

**TL;DR:** Use o ESLint para obter conhecimento sobre as preocupações de separação. [Prettier](https://prettier.io/) ou [Standardjs](https://standardjs.com/) podem resolver automaticamente esses problemas.

**Caso contrário:** Como visto na seção anterior, o interpretador do JavaScript adiciona automaticamente um ponto-e-vírgula ao final de uma instrução, se não houver uma, ou considera uma instrução como não terminada onde deveria, o que pode levar a alguns resultados indesejáveis. Você pode usar atribuições e evitar o uso de expressões de função chamadas imediatas para evitar a maioria dos erros inesperados.

### Exemplo de código

```javascript
// Faça
function doThing() {
    // ...
}

doThing()

// Faça

const items = [1, 2, 3]
items.forEach(console.log)

// Evitar - lança exceção
const m = new Map()
const a = [1,2,3]
[...m.values()].forEach(console.log)
> [...m.values()].forEach(console.log)
>  ^^^
> SyntaxError: Unexpected token ...

// Evitar - lança exceção
const count = 2 // tenta executar 2(), mas 2 não é uma função
(function doSomething() {
  // Faça algo incrível
}())
// Coloque um ponto-e-vírgula antes da função invocada imediatamente, após a definição const, salve o valor de retorno da função anônima para uma variável ou evite IIFEs no conjunto
```

🔗 [**Leia mais:** "Regra Semi ESLint"](https://eslint.org/docs/rules/semi)
🔗 [**Leia mais:** "Nenhuma regra ESLint de múltiplas linhas inesperada"](https://eslint.org/docs/rules/no-unexpected-multiline)

<br/><br/>

## ![✔] 3.5 Nomeie suas funções

**TL;DR:** Nomeie todas as funções, incluindo closures e callbacks. Evite funções anônimas. Isso é especialmente útil em uma aplicação node. Nomear todas a funções permitirá que você entenda facilmente o que está olhando quando verificar um snapshot da memória.

**Caso contrário:** A depuração de problemas de produção usando um dump principal (snapshot da memória) pode se tornar um desafio quando você percebe um consumo significativo de memória de funções anônimas.

<br/><br/>

## ![✔] 3.6 Convenções de nomenclatura para variáveis, constantes, funções e classes

**TL;DR:** Utilize **_lowerCamelCase_** quando nomeando constantes, variáveis e funções, e **_UpperCamelCase_** (primeira letra maiúscula também) quando nomeando classes. Isso irá lhe ajudar a distinguir facilmente entre variáveis/funções, e classes que necessitam de instanciação. Use nomes descritivos, mas tente mantê-los curtos.

**Caso contrário:** O JavaScript é a única linguagem no mundo que permite invocar um construtor (“Class”) diretamente sem instanciá-lo primeiro. Consequentemente, Classes e construtores de funções são diferenciados começando com UpperCamelCase

### 3.6 Exemplo de Código

```javascript
// para classes nós usamos UpperCamelCase
class SomeClassExample {}

// para nomes de constantes nós usamos a palavra const e lowerCamelCase
const config = {
  key: "value",
};

// para nomes de variáveis e funções nós usamos lowerCamelCase
let someVariableExample = "value";
function doSomething() {}
```

<br/><br/>

## ![✔] 3.7 Prefira const ao let. Esqueça o var

**TL;DR:** Usar `const` significa que uma vez que a variável foi atribuída, ela não pode ser reatribuída. Preferir const irá te ajudar a não cair na tentação de utilizar a mesma variável para diferentes usos, e irá deixar seu código mais limpo. Se uma variável precisa ser reatribuída, em um for loop, por exemplo, use `let` para declarar. Outro aspecto importante do `let` é que esta variável só estará disponível no escopo de código em que ela foi definida. `var` tem escopo de função, não de bloco, e [não deveria ser utilizada em ES6](https://hackernoon.com/why-you-shouldnt-use-var-anymore-f109a58b9b70)
, agora que você tem const e let ao seu dispor.

**Caso contrário:** A depuração se torna muito mais complicada ao seguir uma variável que frequentemente muda

🔗 [**Leia Mais: JavaScript ES6+: var, let ou const?** ](https://medium.com/javascript-scene/javascript-es6-var-let-or-const-ba58b8dcde75)

<br/><br/>

## ![✔] 3.8 Importe módulos primeiro, não dentro de funções

**TL;DR:** Faça o require de módulos no início de cada arquivo, antes e fora de qualquer função. Esta simples prática irá te ajudar não apenas a reconhecer as dependências de um determinado arquivo com facilidade e rapidez, como também evitará alguns possíveis problemas.

**Caso contrário:** Os requires rodam de forma síncrona pelo Node.js. Se eles forem chamados de dentro de uma função, isso pode impedir que outras solicitações sejam tratadas em um momento mais crítico. Além disso, se um módulo necessário ou qualquer uma de suas dependências lançar um erro e travar o servidor, é melhor descobrir isso o mais rápido possível, o que pode não ser o caso se este módulo tiver sido declarado dentro de uma função.

<br/><br/>

## ![✔] 3.9 Defina um ponto de entrada explícito para um módulo/pasta

**TL;DR:** Ao desenvolver um módulo/biblioteca em uma pasta, coloque um arquivo index.js que exponha os componentes internos do módulo para que cada consumidor passe por ele. Isso serve como uma 'interface' para seu módulo e facilita futuras mudanças sem causar perdas.

**Caso contrário:** Alterar a estrutura interna dos arquivos ou a assinatura pode quebrar a interface com clientes.

### 3.9 Exemplo de Código

```javascript
// Do
module.exports.SMSProvider = require("./SMSProvider");
module.exports.SMSNumberResolver = require("./SMSNumberResolver");

// Avoid
module.exports.SMSProvider = require("./SMSProvider/SMSProvider.js");
module.exports.SMSNumberResolver = require("./SMSNumberResolver/SMSNumberResolver.js");
```

<br/><br/>

## ![✔] 3.10 Use o operador `===`

**TL;DR:** Dê preferência em usar o operador de comparação estrita `===` ao invés do operador de comparação abstrata `==`, que é mais fraco. `==` irá comparar duas variáveis depois de convertê-las para o mesmo tipo. Não há conversão de tipo no `===` e ambas as variáveis devem ser do mesmo tipo para serem iguais.

**Caso contrário:** Variáveis diferentes podem retornar verdadeiro quando comparadas usando o operador `==`.

### 3.10 Exemplo de Código

```javascript
"" == "0"; // false
0 == ""; // true
0 == "0"; // true

false == "false"; // false
false == "0"; // true

false == undefined; // false
false == null; // false
null == undefined; // true

" \t\r\n " == 0; // true
```

Todas as declarações acima false se feitas com `===`.

<br/><br/>

## ![✔] 3.11 Use Async Await, evite callbacks

**TL;DR:** Agora o Node 8 LTS possui suporte completo para Async-await. Esta é uma nova maneira de lidar com códigos assíncronos que substitui callbacks e promises. Async-await é não-bloqueante, e isso faz com que os códigos assíncronos pareçam síncronos. O melhor presente que você pode dar ao seu código é usar async-await, que fornece uma sintaxe de código muito mais compacta e familiar como o try-catch.

**Caso contrário:** Lidar com erros assíncronos no estilo de callback é provavelmente o caminho mais rápido para o inferno - esse estilo força verificar todos os erros, lidar com desajeitados aninhamentos de código e torna difícil raciocinar sobre o fluxo de código.

🔗[**Leia mais:** Guia do async await 1.0](https://github.com/yortus/asyncawait)

<br/><br/>

## ![✔] 3.12 Use expressões _arrow functions_ (=>)

**TL;DR:** Embora seja recomendado usar async-await e evitar parâmetros de função ao lidar com APIs antigas, que aceitam promises ou callbacks - arrow functions tornam a estrutura do código mais compacta e mantém o contexto léxico da função raiz (por exemplo, 'this').

**Caso contrário:** Códigos mais longos (em funções ES5) são mais propensos a erros e são mais difíceis de ler.

🔗 [**Leia mais: Arrow Functions - é hora de abraçar a causa**](https://medium.com/javascript-scene/familiarity-bias-is-holding-you-back-its-time-to-embrace-arrow-functions-3d37e1a9bb75)

<br/><br/><br/>

<p align="right"><a href="#índice">⬆ Voltar ao topo</a></p>

# `4. Práticas de Testes e Qualidade Geral`

## ![✔] 4.1 No mínimo, escreva testes de API (componente)

**TL;DR:** A maioria dos projetos simplesmente não possuem testes automatizados devido a falta de tempo ou geralmente o 'testing project' fica fora de controle e acaba sendo abandonado. Por esse motivo, priorize e comece com o teste de API, que é o mais fácil de escrever e proporciona mais cobertura do que os testes unitários (você pode inclusive criar testes de API sem código usando ferramentas como [Postman](https://www.getpostman.com/)). Depois, se você tiver mais recursos e tempo, continue com testes avançados, como testes unitários, testes de banco de dados, testes de desempenho, etc.

**Caso contrário:** Voce pode passar longos dias escrevendo testes unitários para perceber que possui apenas 20% de cobertura de sistema.

<br/><br/>

## ![✔] 4.2 Inclua 3 partes em cada nome de teste

**TL;DR:** Faça o teste falar no nível de requisitos, de modo que seja autoexplicativo para engenheiros de garantia de qualidade e desenvolvedores que não estão familiarizados com o código. Indicar no nome do teste o que está sendo testado (unidade em teste), em que circunstâncias e qual é o resultado esperado.

**Caso contrário:** Uma implantação falhou, um teste chamado "Adicionar produto" falhou. Isso lhe diz exatamente o que está errado?

🔗 [**Leia Mais: Inclua 3 partes em cada nome de teste**](./sections/testingandquality/3-parts-in-name.brazilian-portuguese.md)

<br/><br/>

## ![✔] 4.3 Estuture testes a partir do padrão AAA

**TL;DR:** Estruture seus testes com 3 seções bem separadas: Arrange, Act & Assert (AAA). A primeira parte inclui a configuração do teste, depois a execução do teste unitário, e finalmente, a fase de asserção. Seguir esta estrutura garante que o leitor não gaste nenhuma CPU cerebral para entender o plano de teste

**Caso contrário:** Você não somente passará várias horas do dia para entender o código principal, mas agora também gastará várias horas no que deveria ter sido uma simples parte do dia (testando) esticando seu cérebro.

🔗 [**Leia Mais: Estutura de testes padrão AAA**](./sections/testingandquality/aaa.md)

<br/><br/>

## ![✔] 4.4 Detecte problemas de código com um linter

**TL;DR:** Use um code linter para checar a qualidade básica e detectar antipadrões antecipadamente. Rode-o antes de qualquer teste e adicione-o como um pre-commit git-hook para minimizar o tempo necessário para revisar e corrigir qualquer problema. Veja também [Seção 3](https://github.com/goldbergyoni/nodebestpractices#3-code-style-practices) no Prática de Estilo de Código.

**Caso contrário:** Você pode deixar passar algum antipadrão e possível código vulnerável para seu ambiente de produção.

<br/><br/>

## ![✔] 4.5 Evite dados fixos e seeds em testes, adicione dados a cada teste

**TL;DR:** Para evitar o acoplamento de testes e facilitar o entendimento do fluxo do teste, cada teste deve adicionar e atuar em seu próprio conjunto de linhas de banco de dados. Sempre que um teste precisar extrair ou assumir a existência de alguns dados do banco de dados - ele deve incluir explicitamente esses dados e evitar a mutação de outros registros

**Caso contrário:** Considere um cenário em que a implementação é abortada devido a falhas nos testes. Agora, a equipe gastará um tempo precioso de investigação que termina em uma triste conclusão: o sistema funciona bem, mas os testes interferem uns nos outros e quebram a compilação

🔗 [**Leia Mais: Evite dados fixos para teste**](./sections/testingandquality/avoid-global-test-fixture.brazilian-portuguese.md)

<br/><br/>

## ![✔] 4.6 Inspencione constantemente por dependências vulneráveis

**TL;DR:** Até mesmo as dependências mais confiáveis, como o Express, têm vulnerabilidades conhecidas. Isso pode ser facilmente contornado usando ferramentas comunitárias e comerciais como 🔗 [nsp](https://github.com/nodesecurity/nsp) que pode ser invocado a partir do seu CI em cada build.

**Caso contrário:** Manter seu código livre de vulnerabilidades sem ferramentas dedicadas exigirá o acompanhamento constante de publicações online sobre novas ameaças. Saia do tédio.

<br/><br/>

## ![✔] 4.7 Marque seus testes

**TL;DR:** Diferentes testes devem rodar em diferentes cenários: testes de rápidos, sem IO, devem ser executados quando um desenvolvedor salva ou faz commit em um arquivo, testes completos de ponta a ponta geralmente são executados quando uma nova solicitação de request é enviada, etc. Isso pode ser conseguido através da marcação de testes com palavras-chave como #cold #api #sanity. Assim você pode invocar o subconjunto desejado. Por exemplo, é desta forma que você invocaria apenas o grupo de sanity test usando o [Mocha](https://mochajs.org/): mocha --grep 'sanity'

**Caso contrário:** Rodar todos os testes, incluindo aqueles que executam dezenas de consultas de banco de dados, sempre que o desenvolvedor fizer uma pequena alteração pode ser extremamente lento e impedir que desenvolvedores executem testes.

<br/><br/>

## ![✔] 4.8 Verifique suas coberturas de testes, isso te ajuda a identificar padrões incorretos de teste

**TL;DR:** Ferramentas de cobertura de código como [Istanbul](https://github.com/istanbuljs/istanbuljs)/[NYC](https://github.com/istanbuljs/nyc), são ótimas por 3 motivos: elas são gratuitas (nenhum esforço é necessário para beneficiar esses relatórios), elas ajuda a identificar diminuição na cobertura de testes, e por último mas não menos importante, ela destacam a incompatibilidade de testes: olhando relatórios coloridos de cobertura de código, você pode notar, por exemplo, áreas de código que nunca são testadas como cláusulas catch (o que significa que os testes só invocam os caminhos felizes e não como o aplicativo se comporta em erros). Configure-o para falhas se a cobertura estiver abaixo de um certo limite.

**Caso contrário:** Não haverá nenhuma métrica automática informando quando uma grande parte de seu código não é coberta pelo teste.

<br/><br/>

## ![✔] 4.9 Inspecione pacotes desatualizados

**TL;DR:** Use sua ferramenta preferida (por exemplo, 'npm outdated' ou [npm-check-updates](https://www.npmjs.com/package/npm-check-updates) para detectar pacotes instalados que estão desatualizados, injetar essa verificação em seu pipeline de CI e até mesmo fazer uma falha grave em um cenário grave. Por exemplo, um cenário grave pode ser quando um pacote instalado esteja há 5 commits atrás (por exemplo, a versão local é 1.3.1 e a versão no repositório é 1.3.8) ou está marcada como descontinuada pelo autor - mate o build e impeça a implantação desta versão.

**Caso contrário:** Sua produção executará pacotes que foram explicitamente marcados pelo autor como arriscados.

<br/><br/>

## ![✔] 4.10 Use docker-compose para testes e2e

**TL;DR:** Teste de ponta a ponta (end to end, ou e2e), que inclui dados ativos, costumava ser o elo mais fraco do processo de CI, já que depende de vários serviços pesados como o banco de dados. O docker-compose deixa isso mamão com açúcar, criando um ambiente de produção usando um arquivo de texto simples e comandos fáceis. Isto permite criar todos os serviços dependentes, banco de dados e rede isolada para teste e2e. Por último mas não menos importante, ele pode manter um ambiente sem estado que é invocado antes de cada suíte de testes e é encerrado logo após.

**Caso contrário:** Sem o docker-compose, as equipes devem manter um banco de dados de teste para cada ambiente de teste, incluindo as máquinas dos desenvolvedores, e manter todos esses bancos de dados sincronizados para que os resultados dos testes não variem entre os ambientes.

<br/><br/>

## ![✔] 4.11 Refatore regularmente usando ferramentas de análise estática

**TL;DR:** O uso de ferramentas de análise estática ajuda fornecendo maneiras objetivas de melhorar a qualidade do código e manter seu código sustentável. Você pode adicionar ferramentas de análise estática para seu build de Integração Contínua (CI) falhar quando encontre code smells. Seus principais pontos de vantagem sobre o linting são a abilidade de inspecionar a qualidade no contexto de múltiplos arquivos (por exemplo, detectar duplicidades), realizar análises avançadas (por exemplo, complexidade de código), e acompanhar histórico e progresso de problemas de código. Dois dexemplos de ferramentas que podem ser utilizadas são [Sonarqube](https://www.sonarqube.org/) (mais de 2.600 [stars](https://github.com/SonarSource/sonarqube)) e [Code Climate](https://codeclimate.com/) (mais de 1.500 [stars](https://github.com/codeclimate/codeclimate)).

**Caso contrário:** Com qualidade de código ruim, bugs e desempenho sempre serão um problema que nenhuma nova biblioteca maravilhosa ou recursos de última geração podem corrigir.

🔗 [**Leia Mais: Refatoração!**](./sections/testingandquality/refactoring.brazilian-portuguese.md)

<br/><br/>

## ![✔] 4.12 Escolha cuidadosamente sua plataforma de Integração Contínua - CI (Jenkins vs CircleCI vs Travis vs Resto do mundo)

**TL;DR:** Sua plataforma de integração contínua (CICD) irá hospedar todas as ferramentas de qualidade (por exemplo, teste, lint), então ela deve vir com um ecosistema de plugins arrebatador. O [Jenkins](https://jenkins.io/) costumava ser o padrão de muitos projetos, pois tem a maior comunidade, juntamente com uma poderosa plataforma, ao preço de configuração complexa que exige uma curva de aprendizado íngreme. Atualmente, ficou bem mais fácil para configurar uma solução de CI usando ferramentas SaaS como [CircleCI](https://circleci.com) e outras. Essas ferramentas permitem a criação de um pipeline de CI flexível sem o peso de gerenciar toda a infraestrutura. Eventualmente, é um perde e ganha entre robustez e velocidade - escolha seu lado com cuidado!

**Caso contrário:** Escolher algum fornecedor de nicho pode fazer com que você fique engessado quando precisar de alguma personalização avançada. Por outro lado, escolher o Jenkins pode ser uma perda de tempo precioso na configuração da infraestrutura.

🔗 [**Leia Mais: Escolhendo a plataforma de CI**](./sections/testingandquality/citools.brazilian-portuguese.md)

<br/><br/>

## ![✔] 4.13 Teste seus 'middlewares' isoladamente

**TL;DR:** quando um 'middleware' contém alguma lógica imensa que abrange muitas solicitações, vale a pena testá-lo isoladamente, sem ativar todo o framework. Isso pode ser facilmente alcançado por 'stubbing' e espionando os objetos {req, res, next}

**Caso contrário:** Um bug no 'middleware Express' === um bug em todas ou na maioria das solicitações

🔗 [**Read More: Test middlewares in isolation**](./sections/testingandquality/test-middlewares.md)

<br/><br/><br/>

<p align="right"><a href="#índice">⬆ Voltar ao topo</a></p>

# `5. Práticas ao escalar para Produção`

## ![✔] 5.1. Monitoramento

**TL;DR:** O monitoramento é um jogo de descobrir problemas antes que os clientes os encontrem - obviamente deve ser atribuída muita importância para isto. O mercado está sobrecarregado de ofertas, portanto, considere começar com a definição das métricas básicas que você deve seguir (sugestões minhas dentro), depois passe por recursos extras e escolha a solução que marca todas as caixas. Acesse o ‘Gist’ abaixo para uma visão geral das soluções.

**Caso contrário:** Falha === clientes desapontados. Simples

🔗 [**Leia Mais: Monitoramento!**](./sections/production/monitoring.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.2. Aumente a transparência usando smart logging

**TL;DR:** Logs podem ser um armazém inútil de instruções de debug ou o ativador de um belo dashboard que conta a história do seu app. Planeje sua plataforma de logs desde o primeiro dia: como os logs são coletados, armazenados e analisados para ter certeza de que as informações desejadas possam realmente ser extraídas, por exemplo, a avaliação de erro, após uma transação inteira através de serviços e servidores, etc.

**Caso contrário:** Você acaba com uma caixa preta que é difícil de raciocinar, então você começa a reescrever todas as declarações de log para adicionar informações adicionais.

🔗 [**Leia Mais: Aumente a transparência usando smart logging**](./sections/production/smartlogging.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.3. Delegue tudo o que for possível (por exemplo, gzip, SSL) a um proxy reverso

**TL;DR:** O Node é terrivelmente ruim em fazer tarefas intensas de CPU como gzipping, SSL termination, etc. Você deve usar serviços de middleware “reais” como nginx, HAproxy ou serviços de nuvem.

**Caso contrário:** Seu único e pobre thread permanecerá ocupado fazendo tarefas de infra-estrutura em vez de lidar com o núcleo da sua aplicação e o desempenho certamente será degradado.

🔗 [**Leia Mais: Delegue tudo o que for possível (por exemplo, gzip, SSL) a um proxy reverso**](./sections/production/delegatetoproxy.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.4. Bloqueio de dependências

**TL;DR:** Seu código deve ser idêntico em todos os ambientes, mas, surpreendentemente, o npm permite que as dependências derivem entre os ambientes por padrão - quando você instala pacotes em vários ambientes, ele tenta buscar a versão mais recente dos pacotes. Supere isso usando arquivos de configuração do npm, .npmrc, que dirão a cada ambiente para salvar a versão exata (não a última) de cada pacote. Outra alternativa, para um controle melhor, use o “shirinkwrap” do npm. \*Atualização: a partir do NPM5, as dependências são bloqueadas por padrão. O novo gerenciador de pacotes no pedaço, Yarn, também faz isso por padrão.

**Caso contrário:** O QA testará completamente o código e aprovará uma versão que se comportará de maneira diferente na produção. Pior ainda, servidores diferentes no mesmo cluster de produção podem executar código diferente.

🔗 [**Leia Mais: Bloqueio de dependências**](./sections/production/lockdependencies.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.5. Poupe tempo de atividade do processo usando a ferramenta certa

**TL;DR:** O processo deve continuar e ser reiniciado após falhas. Para cenários simples, as ferramentas de "reinicialização", como PM2, podem ser suficientes. Entretanto, no mundo atual "dockerizado", as ferramentas de gerenciamento de cluster também devem ser consideradas

**Caso contrário:** Rodar dezenas de instâncias sem uma estratégia clara e muitas ferramentas juntas (gerenciamento de cluster, docker, PM2) pode levar o DevOps ao caos.

🔗 [**Leia Mais: Poupe tempo de atividade do processo usando a ferramenta certa**](./sections/production/guardprocess.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.6. Utilize todos os núcleos do processador

**TL;DR:** Em sua forma básica, uma aplicação Node roda em um único núcleo do processador enquanto todos os demais ficam inativos. É seu dever replicar o processamento do Node e utilizar todos os processadores. Para aplicações pequenas/médias você pode usar o Node Cluster ou PM2. Para uma aplicação maior, considere replicar o processo usando algum cluster do Docker (por exemplo, o K8S ou o ECS) ou scripts de deploy que são baseados no sistema de inicialização do Linux (por exemplo, systemd)

**Caso contrário:** Sua aplicação vai utilizar apenas 25% dos recursos disponíveis(!) ou talvez até menos. Note que um servidor típico possui 4 núcleos de processamento ou mais, o deploy ingênuo do Node.js utiliza apenas 1 (mesmo usando serviços de PaaS como AWS Beanstalk!)

🔗 [**Leia Mais: Utilize todos os núcleos do processador**](./sections/production/utilizecpu.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.7. Crie um ‘endpoint de manutenção’

**TL;DR:** Exponha um conjunto de informações relacionadas ao sistema, como uso de memória e REPL, etc, em uma API segura. Embora seja altamente recomendado confiar em ferramentas padrões e de battle-tests, algumas informações e operações valiosas são mais fáceis de serem feitas usando código.

**Caso contrário:** Você perceberá que está realizando muitos “deploys de diagnóstico” - enviando código para produção apenas para extrair algumas informações para fins de diagnóstico.

🔗 [**Leia Mais: Crie um ‘endpoint de manutenção’**](./sections/production/createmaintenanceendpoint.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.8. Descubra o que está oculto usando produtos APM

**TL;DR:** Produtos de monitoramento e desempenho (também conhecidos como APM) medem a base de código e a API de forma proativa para que possam ir “automagicamente” além do monitoramento tradicional e medir a experiência geral do usuário entre os serviços e camadas. Por exemplo, alguns APMs podem destacar uma transação que é carregada muito lentamente no lado do usuário final, sugerindo a causa raiz.

**Caso contrário:** Você pode gastar muito esforço medindo o desempenho e os tempos de inatividade da API, provavelmente você nunca saberá quais são suas partes de código mais lentas no cenário do mundo real e como elas afetam o UX.

🔗 [**Leia Mais: Descubra erros e tempo de inatividade usando produtos APM**](./sections/production/apmproducts.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.9. Deixe seu código pronto para produção

**TL;DR:** Programe com o fim em mente, planeje para produção desde o primeiro dia. Isso pode parecer vago, então eu compilei algumas dicas de desenvolvimento que estão relacionadas à manutenção de produção (clique no Gist abaixo).

**Caso contrário:** Uma pessoa fera em TI/DevOps não salvará um sistema mal escrito.

🔗 [**Leia Mais: Deixe seu código pronto para produção**](./sections/production/productioncode.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.10. Meça e proteja o uso de memória

**TL;DR:** O Node.js tem uma relação controversa com o uso de memória: o motor v8 possui limites no uso de memória (1.4GB) e existem caminhos conhecidos para vazamentos de memória no código do Node - portanto, observar a memória do processo do Node é uma obrigação. Em aplicações pequenas, você pode medir a memória periodicamente usando comandos shell, mas em aplicação média-grande considere utilizar um sistema de monitoramento de memória robusto.

**Caso contrário:** A memória de seus processos pode vazar cem megabytes por dia, assim como aconteceu no [Walmart](https://www.joyent.com/blog/walmart-node-js-memory-leak).

🔗 [**Leia Mais: Meça e proteja o uso de memória**](./sections/production/measurememory.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.11. Deixe seus recursos de frontend fora do Node

**TL;DR:** Sirva conteúdo de frontend usando um middleware dedicado (nginx, S3, CDN) pois o desempenho do Node fica realmente prejudicado quando se lida com muitos arquivos estáticos devido ao seu modelo single threaded (segmento único).

**Caso contrário:** Seu único thread do Node ficará ocupado fazendo streaming the centenas de arquivos de html/imagens/angular/react ao invés de alocar todo seu recurso para a tarefa que ele foi designado - servir conteúdo dinâmico.

🔗 [**Leia Mais: Deixe seus recursos de frontend fora do Node**](./sections/production/frontendout.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.12. Aspire a ser stateless

**TL;DR:** Armazene qualquer tipo de dados (por exemplo, sessões de usuário, cache, arquivos de upload) em armazenamentos externos. Considere ‘matar’ seus servidores periódicamente ou utilize plataformas ‘serverless’ (por exemplo, AWS Lambda) que forçam explicitamente um comportamento stateless.

**Caso contrário:** Falha em um determinado servidor resultará em tempo de inatividade da aplicação, em vez de apenas matar uma máquina defeituosa. Além do mais, dimensionar a elasticidade será mais desafiador devido à dependência de um servidor específico.

🔗 [**Leia Mais: Seja stateless, mate seus Servidores quase todos os dias**](./sections/production/bestateless.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.13. Utilize ferramentas que detectam vulnerabilidades automaticamente

**TL;DR:** Mesmo as dependências mais confiáveis, como o Express, têm vulnerabilidades conhecidas (de tempos em tempos) que podem colocar um sistema em risco. Isso pode ser contornado usando ferramentas comunitárias e comerciais que constantemente verificam vulnerabilidades e avisam (localmente ou no Github). Algumas podem até corrigí-las imediatamente.

**Caso contrário:** Manter seu código limpo com vulnerabilidades sem ferramentas dedicadas exigirá o acompanhamento constante de publicações online sobre novas ameaças. Bem entendiante.

🔗 [**Leia Mais: Utilize ferramentas que detectam vulnerabilidades automaticamente**](./sections/production/detectvulnerabilities.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.14. Atribua 'transaction-id's para cada declaração de log

**TL;DR:** Atribua o mesmo identificador, transaction-id: {some value}, para cada entrada de log dentro de um mesmo request. Depois, ao inspecionar erros em logs, conclua facilmente o que aconteceu antes e depois. Infelizmente, isso não é fácil de se conseguir no Node, devido à sua natureza assíncrona. Veja exemplos de código.

**Caso contrário:** Observar um log de erros de produção sem o contexto - o que aconteceu antes - torna muito mais difícil e mais lento raciocinar sobre o problema.

🔗 [**Leia Mais: Atribua ‘TransactionId’ para cada declaração de log**](./sections/production/assigntransactionid.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.15. Defina NODE_ENV=production

**TL;DR:** Defina a variável de ambiente NODE_ENV para ‘production’ ou ‘development’ para sinalizar se as otimizações de produção devem ser ativadas - muitos pacotes npm determinam o ambiente atual e otimizam seu código para produção.

**Caso contrário:** Omitir esta simples propriedade pode degradar muito o desempenho. Por exemplo, ao utilizar o Express para renderização do lado do servidor, omitir o NODE_ENV o torna mais lento!

🔗 [**Leia Mais: Defina NODE_ENV=production**](./sections/production/setnodeenv.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.16. Projete deploys automáticos, atômicos e com tempo de inatividade zero

**TL;DR:** Pesquisas mostram que times que executam muitos deploys, reduzem a probabilidade de problemas graves em produção. Deploys rápidos e automatizados que não necessitam de processos manuais arriscados e significativo tempo de inatividade, melhoram o processo de deploy. Provavelmente, você irá alcançar isso usando Docker, combinado com ferramentas de CI, pois elas se tornaram o padrão do setor para deploy simplificado.

**Caso contrário:** Deploys demorados -> tempo de inatividade de produção e erro relacionado a humanos -> equipe não-confiante com os deploys -> menos implantações e recursos.

<br/><br/>

## ![✔] 5.17. Use uma versão LTS do Node.js

**TL;DR:** Certifique de que você está usando uma versão LTS do Node.js para receber correção de bugs críticos, atualizações de segurança e melhorias de performance.

**Caso contrário:** Bugs recentemente descobertos e vulnerabilidades podem ser usados para explorar uma aplicação em produção, e sua aplicação pode se tornar incompatível com vários módulos e mais difícil de manter.

🔗 [**Leia Mais: Use uma versão LTS do Node.js**](./sections/production/LTSrelease.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.18. Não direcione logs dentro do aplicativo

**TL;DR:** O destino dos logs não devem ser codificados na unha por desenvolvedores, dentro do código da aplicação. Ao invés disso, deve ser definido pelo ambiente de execução no qual a aplicação é executada. Desenvolvedores devem escrever logs para stdout usando um utilitário logger e depois deixar o ambiente de execução (container, servidor, etc) canalizar o fluxo do stdout para o destino apropriado (por exemplo: Splunk, Graylog, ElasticSearch, etc).

**Caso contrário:** Aplicações manipulando o roteamento de log === difícil de dimensionar, perda de logs, separação ruim de preocupações.

🔗 [**Leia Mais: Roteamento de Logs**](./sections/production/logrouting.brazilian-portuguese.md)

<br/><br/>

## ![✔] 5.19. Instale seus pacotes com `npm ci`

**TL;DR:** Você precisa ter certeza de que o código de produção usa a versão exata dos pacotes que você realizou os testes. Execute `npm ci` para fazer estritamente uma instalação limpa de suas dependências correspondentes do package.json e do package-lock.json. O uso desse comando é recomendado em ambientes automatizados, como pipelines de integração contínua.

**Caso contrário:** o QA testará completamente o código e aprovará uma versão que se comportará de maneira diferente em produção. Pior ainda, diferentes servidores no mesmo cluster de produção podem executar códigos diferentes.

🔗 [**Read More: Use npm ci**](./sections/production/installpackageswithnpmci.md)

<br/><br/><br/>

<p align="right"><a href="#índice">⬆ Voltar ao topo</a></p>

# `6. Práticas de Seguraça`

<div align="center">
<img src="https://img.shields.io/badge/OWASP%20Threats-Top%2010-green.svg" alt="54 items"/>
</div>

## ![✔] 6.1. Adote as regras de segurança do linter

<a href="https://www.owasp.org/index.php/Top_10-2017_A1-Injection" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A1:Injection%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A7-Cross-Site_Scripting_(XSS)" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20XSS%20-green.svg" alt=""/></a>

**TL;DR:** Faça uso de plugins de linter relacionados à segurança, como por exemplo o [eslint-plugin-security](https://github.com/nodesecurity/eslint-plugin-security) para capturar vulnerabilidades de segurança e erros o mais cedo possível, na melhor das hipóteses, enquanto estão sendo codificados. Isso pode ajudar a detectar pontos fracos de segurança, como usar o eval, invocar um processo filho ou importar um módulo com string literal (por exemplo, input do usuário). Clique em ‘Leia Mais’ abaixo para ver exemplos de códigos que serão capturados por um linter de segurança.

**Caso contrário:** O que poderia ser um ponto fraco de segurança durante o desenvolvimento, pode se tornar um grande problema no ambiente de produção. Além disso, o projeto pode não seguir práticas de segurança de código consistentes, levando a vulnerabilidades sendo introduzidas ou segredos confidenciais comprometidos em repositórios remotos.

🔗 [**Leia Mais: Regras de Lint**](sections/security/lintrules.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.2. Limite requests simultâneos usando um middleware

<a href="https://www.owasp.org/index.php/Denial_of_Service" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20DDOS%20-green.svg" alt=""/></a>

**TL;DR:** Ataques DOS são muito populares e relativamente fáceis de conduzir. Implemente uma limitação de taxa, usando um serviço externo como balanceadores de carga de nuvem, firewalls de nuvem, nginx, o pacote [rate-limiter-flexible](https://www.npmjs.com/package/rate-limiter-flexible), ou (para aplicações menores e menos críticas) um middleware limitador de taxa (por exemplo, [express-rate-limit](https://www.npmjs.com/package/express-rate-limit))

**Caso contrário:** Uma aplicação pode estar sujeita a um ataque resultando em uma queda do serviço, onde usuários reais recebem um serviço degradado ou indisponível.

🔗 [**Leia Mais: Implementando limitador de taxa**](sections/security/limitrequests.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.3. Extraia segredos dos arquivos de configuração ou use pacotes para criptografá-los

<a href="https://www.owasp.org/index.php/Top_10-2017_A6-Security_Misconfiguration" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A6:Security%20Misconfiguration%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A3-Sensitive_Data_Exposure" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A3:Sensitive%20Data%20Exposure%20-green.svg" alt=""/></a>

**TL;DR:** Nunca armazene segredos em textos simples em arquivos de configuração ou códigos fonte. Em vez disso, use sistemas de gerenciamento secreto como produtos Vault, Kubernetes/Docker Secrets, ou use variáveis de ambiente. Como resultado final, os segredos armazenados no código fonte devem ser criptografados e gerenciados(rolling keys, expiring, auditing, etc). Faça uso de hooks de pre-commit/push para evitar que faça o commit de secredos acidentalmente.

**Caso contrário:** O controle de origem, mesmo para repositórios privados, pode ser tornado público por engano, quando todos os segredos são expostos. O acesso ao controle de origem para uma parte externa fornecerá inadvertidamente acesso a sistemas relacionados (bancos de dados, APIs, serviços, etc.).

🔗 [**Leia Mais: Gerenciamento de segredos**](sections/security/secretmanagement.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.4. Previna-se contra vulnerabilidades de query injection com bibliotecas ORM/ODM

<a href="https://www.owasp.org/index.php/Top_10-2017_A1-Injection" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A1:Injection%20-green.svg" alt=""/></a>

**TL;DR:** Para evitar SQL/NoSQL injection e outros ataques maliciosos, sempre faça uso de um ORM/ODM ou de uma biblioteca de banco de dados que proteja os dados ou suporte consultas parametrizadas nomeadas ou indexadas, e que cuide da validação de entrada do usuário para os tipos esperados. Nunca use apenas template strings do JavaScript ou concatenação de string para injetar valores em queries, pois isto abre sua aplicação para muitas vulnerabilidades. Todas as bibliotecas respeitáveis de acesso a dados do Node.js (por exemplo, [Sequelize](https://github.com/sequelize/sequelize), [Knex](https://github.com/tgriesser/knex), [mongoose](https://github.com/Automattic/mongoose)) possuem proteção contra ataques de injeção.

**Caso contrário:** A entrada de usuários não validados pode levar à injeção do operador ao trabalhar com MongoDB para NoSQL e não usar um sistema próprio ou ORM irão permitir facilmente um ataque de SQL injection, criando uma grande vulnerabilidade.

🔗 [**Leia Mais: Prevenção de query injection usando bibliotecas de ORM/ODM**](./sections/security/ormodmusage.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.5. Coleção genérica de boas práticas de segurança

**TL;DR:** Esta é uma coleção de conselhos de segurança que não estão relacionadas diretamente com Node.js - a implementação do Node não é muito diferente comparado a outras linguagens. Clique em “leia mais” para dar uma olhada.

🔗 [**Leia Mais: Boas práticas comuns de segurança**](./sections/security/commonsecuritybestpractices.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.6. Ajuste os headers de resposta HTTP para uma segurança aprimorada

<a href="https://www.owasp.org/index.php/Top_10-2017_A6-Security_Misconfiguration" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A6:Security%20Misconfiguration%20-green.svg" alt=""/></a>

**TL;DR:** Sua aplicação deve estar utilizando headers seguros para evitar que invasores façam ataques comuns, como scripts entre sites (XSS), clickjacking, dentre outros ataques maliciosos. Eles podem ser configurados facilmente usando módulos como o [helmet](https://www.npmjs.com/package/helmet).

**Caso contrário:** Invasores podem realizar ataques diretos aos usuários de sua aplicação, levando a grandes vulnerabilidades de segurança.

🔗 [**Leia Mais: Usando headers seguros em sua aplicação**](./sections/security/secureheaders.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.7. Inspecione constante e automaticamente por dependências vulneráveis

<a href="https://www.owasp.org/index.php/Top_10-2017_A9-Using_Components_with_Known_Vulnerabilities" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A9:Known%20Vulnerabilities%20-green.svg" alt=""/></a>

**TL;DR:** Com o ecosistema do npm, é comum um projeto ter várias dependências. Dependências sempre devem ser checadas em caso de novas vulnerabilidades serem encontradas. Utilize ferramentas como [npm audit](https://docs.npmjs.com/cli/audit) ou [snyk](https://snyk.io/) para rastrear, monitorar e corrigir dependências vulneráveis. Integre estas ferramentas com a configuração de seu CI, para que você possa capturar uma dependência vulnerável antes que ela afete o ambiente de produção.

**Caso contrário:** Um invasor pode detectar seu framework web e atacar todas suas vulnerabilidades.

🔗 [**Leia Mais: Segurança de dependências**](./sections/security/dependencysecurity.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.8. Evite usar a biblioteca de criptografia do Node.js para manipular senhas, use Bcrypt

<a href="https://www.owasp.org/index.php/Top_10-2017_A2-Broken_Authentication" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A9:Broken%20Authentication%20-green.svg" alt=""/></a>

**TL;DR:** Senhas ou segredos (chaves de API), devem ser armazenadas usando um hash seguro + salt function como bcrypt, que deve ser a escolha preferencial em relação à sua implementação de JavaScript, devido a razões de desempenho e segurança.

**Caso contrário:** Senhas ou segredos que são persistidos sem o uso de uma função segura, são vulneráveis a força bruta e ataques de dicionário que levarão eventualmente à sua divulgação.

🔗 [**Leia Mais: Use o Bcrypt**](./sections/security/bcryptpasswords.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.9. Fuja de saídas HTML, JS e CSS

<a href="https://www.owasp.org/index.php/Top_10-2017_A7-Cross-Site_Scripting_(XSS)" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A7:XSS%20-green.svg" alt=""/></a>

**TL;DR:** Dados não confiáveis que são enviados para o browser podem ser executados em invés de serem exibidos. Isso está sendo comumente referido como um ataque de script entre sites (XSS). Evite isto, usando bibliotecas dedicadas que marcam explicitamente os dados como conteúdo puro que nunca deve ser executado (por exemplo: encoding, escaping).

**Caso contrário:** Um invasor pode armazenar um código JavaScript malicioso em seu banco de dados, que será enviado para os clientes.

🔗 [**Leia Mais: Evite saídas**](./sections/security/escape-output.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.10. Valide os esquemas de entrada JSON

<a href="https://www.owasp.org/index.php/Top_10-2017_A7-Cross-Site_Scripting_(XSS)" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A7: XSS%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A8-Insecure_Deserialization" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A8:Insecured%20Deserialization%20-green.svg" alt=""/></a>

**TL;DR:** Valide as requisições do body e garanta que elas atendem as expectativas e falhem rápido se não atender. Para evitar o tédio de códigos de validação para cada rota, você pode usar leves esquemas de validação baseados em JSON, como [jsonschema](https://www.npmjs.com/package/jsonschema) ou [joi](https://www.npmjs.com/package/joi)

**Caso contrário:** Sua generosidade e abordagem permissiva aumentam muito a superfície de ataque e incentivam o invasor a experimentar muitas entradas até encontrar alguma combinação para travar a aplicação.

🔗 [**Leia Mais: Valide os esquemas de entrada JSON**](./sections/security/validation.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.11. Ajude a inserir JWTs em listas negras

<a href="https://www.owasp.org/index.php/Top_10-2017_A2-Broken_Authentication" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A9:Broken%20Authentication%20-green.svg" alt=""/></a>

**TL;DR:** Ao usar JSON Web Tokens (por exemplo, com [Passport.js](https://github.com/jaredhanson/passport)), por padrão não existem mecanismos para revogar o acesso de tokens problemáticos. Uma vez descoberta alguma atividade maliciosa do usuário, não há como impedi-lo de acessar o sistema, desde que ele tenha um token válido. Abrande isso implementando uma lista negra de tokens não confiáveis que são validados em cada solicitação.

**Caso contrário:** Tokens expirados ou extraviados, podem ser usados maliciosamente por terceiros para acessar uma aplicação e para representar o proprietário do token.

🔗 [**Leia Mais: Blacklist de JSON Web Tokens**](./sections/security/expirejwt.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.12. Evite ataques de força bruta contra autorização

<a href="https://www.owasp.org/index.php/Top_10-2017_A2-Broken_Authentication" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A9:Broken%20Authentication%20-green.svg" alt=""/></a>

**TL;DR:** Uma técnica simples e poderosa é limitar as tentativas de autorização usando duas métricas:

1. A primeiro é o número de tentativas consecutivas com falha do mesmo ID/nome e endereço IP exclusivos do usuário.
2. A segundo é o número de tentativas malsucedidas de um endereço IP durante um longo período de tempo. Por exemplo, bloqueie um endereço IP se ele fizer 100 tentativas com falha em um dia.

**Caso contrário:** Um invasor pode emitir tentativas ilimitadas de senha automatizada para obter acesso a contas com privilégios em uma aplicação.

🔗 [**Leia Mais: Limitando a taxa de login**](./sections/security/login-rate-limit.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.13. Execute o Node.js como um usuário não-root

<a href="https://www.owasp.org/index.php/Top_10-2017_A5-Broken_Access_Control" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A5:Broken%20Access%20Access%20Control-green.svg" alt=""/></a>

**TL;DR:** Existe um cenário comum em que o Node.js é executado como um usuário root com permissões ilimitadas. Por exemplo, esse é o comportamento padrão em contêineres do Docker. É recomendável criar um usuário não raiz e associá-lo à imagem do Docker (exemplos abaixo) ou executar o processo em nome desse usuário chamando o container com o sinalizador "-u username".

**Caso contrário:** Um invasor que consiga executar um script no servidor obtém poder ilimitado sobre a máquina local (por exemplo, alterar o iptable e redirecionar o tráfego para seu servidor).

🔗 [**Leia Mais: Rode o Node.js com um usuário não raiz**](./sections/security/non-root-user.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.14. Limite o tamanho do payload usando um proxy reverso ou um middleware

<a href="https://www.owasp.org/index.php/Top_10-2017_A8-Insecure_Deserialization" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A8:Insecured%20Deserialization%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A1-Injection" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20DDOS%20-green.svg" alt=""/></a>

**TL;DR:** Quanto maior o payload do body, mais difícil será o processamento de um único segmento. Esta é uma oportunidade para os invasores colocarem seus servidores de joelhos sem uma enorme quantidade de solicitações (ataques DOS / DDOS). Reduza isso limitando o tamanho do corpo das solicitações recebidas (por exemplo, firewall, ELB) ou configurando o [express body parser](https://github.com/expressjs/body-parser) para aceitar somente cargas de tamanho pequeno.

**Caso contrário:** Sua aplicação terá que lidar com solicitações grandes, incapazes de processar o outro trabalho importante que ele precisa realizar, o que leva a implicações de desempenho e vulnerabilidade em relação a ataques DOS.

🔗 [**Leia Mais: Limite o tamanho dos payloads**](./sections/security/requestpayloadsizelimit.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.15. Evite instruções eval do JavaScript

<a href="https://www.owasp.org/index.php/Top_10-2017_A7-Cross-Site_Scripting_(XSS)" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A7:XSS%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A1-Injection" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A1:Injection%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A4-XML_External_Entities_(XXE)" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A4:External%20Entities%20-green.svg" alt=""/></a>

**TL;DR:** `eval` é do mal, pois permite a execução de um código JavaScript personalizado durante o tempo de execução. Isso não é apenas uma preocupação de desempenho, mas também uma importante preocupação de segurança devido ao código JavaScript malicioso que pode ser originado da entrada do usuário. Outra feature da linguagem que deve ser evitada é o construtor `new Function` constructor. `setTimeout` e `setInterval` também não devem ser receber código JavaScript dinâmico.

**Caso contrário:** o código JavaScript malicioso encontra um caminho para um texto passado para o eval ou outras funções de avaliação em tempo real da linguagem JavaScript, e terá acesso total às permissões do JavaScript na página. Essa vulnerabilidade geralmente se manifesta como um ataque XSS.

🔗 [**Leia Mais: Evite instruções eval do JavaScript**](./sections/security/avoideval.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.16. Evite que RegEx maliciosos sobrecarreguem sua execução de thread único

<a href="https://www.owasp.org/index.php/Denial_of_Service" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20DDOS%20-green.svg" alt=""/></a>

**TL;DR:** Regular Expressions, embora sejam úteis, representam uma ameaça real para aplicativos JavaScript em geral, e a plataforma Node.js em particular .Uma entrada do usuário para correspondência de texto pode exigir uma quantidade maior de ciclos de CPU para processar. O processamento RegEx pode ser ineficiente até um ponto em que uma única solicitação que valida 10 palavras pode bloquear todo o loop de eventos por 6 segundos e botar 🔥 na CPU. Por essa razão, prefira pacotes de validação de terceiros como [validator.js](https://github.com/chriso/validator.js) ao invés de escrever seus próprios pardrões de Regex, ou faça uso do [safe-regex](https://github.com/substack/safe-regex) para detectar padrões vulneráveis de regex.

**Caso contrário:** Expressões regulares mal escritas podem ser suscetíveis a ataques de Regular Expresssion DoS, que irão bloquear completamente o loop de eventos. Por exemplo, o popular pacote `moment` foi encontrado com vulnerabilidades de uso de RegEx maliciosos em novembro de 2017.

🔗 [**Leia Mais: Evite RegEx maliciosos**](./sections/security/regex.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.17. Evite o carregamento de módulos usando uma variável

<a href="https://www.owasp.org/index.php/Top_10-2017_A7-Cross-Site_Scripting_(XSS)" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A7:XSS%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A1-Injection" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A1:Injection%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A4-XML_External_Entities_(XXE)" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A4:External%20Entities%20-green.svg" alt=""/></a>

**TL;DR:** Evite fazer require ou importar outro arquivo com um caminho que tenha sido fornecido como parâmetro devido à preocupação de que ele possa ter se originado da entrada do usuário. Esta regra pode ser estendida para acessar arquivos em geral (ou seja, `fs.readFile()`) ou outro acesso a recursos confidenciais com variáveis dinâmicas provenientes da entrada do usuário. O linter [Eslint-plugin-security](https://www.npmjs.com/package/eslint-plugin-security) pode pegar esses padrões e avisar o quanto antes.

**Caso contrário:** A entrada de usuário mal-intencionada pode encontrar o caminho para um parâmetro usado para require de arquivos adulterados, por exemplo, um arquivo carregado anteriormente no sistema de arquivos ou para acessar arquivos de sistema já existentes.

🔗 [**Leia Mais: Carregamento seguro de módulos**](./sections/security/safemoduleloading.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.18. Rode códigos não seguros em uma sandbox

<a href="https://www.owasp.org/index.php/Top_10-2017_A7-Cross-Site_Scripting_(XSS)" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A7:XSS%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A1-Injection" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A1:Injection%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A4-XML_External_Entities_(XXE)" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A4:External%20Entities%20-green.svg" alt=""/></a>

**TL;DR:** Quando a tarefa for executar código externo que é fornecido em tempo de execução (por exemplo, plug-in), use qualquer tipo de ambiente de execução 'sandbox' que isole e proteja o código principal em relação ao plug-in. Isso pode ser feito usando um processo dedicado (por exemplo, cluster.fork ()), ambiente serverless ou pacotes npm dedicados que atuam como uma sandbox.

**Caso contrário:** Um plugin pode atacar através de uma infinita variedade de opções, como loops infinitos, sobrecarga de memória e acesso a variáveis sensíveis do ambiente de processo.

🔗 [**Leia Mais: Rode códigos não seguros em uma sandbox**](./sections/security/sandbox.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.19. Tome cuidado extra ao trabalhar com processos filhos

<a href="https://www.owasp.org/index.php/Top_10-2017_A7-Cross-Site_Scripting_(XSS)" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A7:XSS%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A1-Injection" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A1:Injection%20-green.svg" alt=""/></a> <a href="https://www.owasp.org/index.php/Top_10-2017_A4-XML_External_Entities_(XXE)" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A4:External%20Entities%20-green.svg" alt=""/></a>

**TL;DR:** Evite usar processos filhos quando possível e valide e limpe a entrada para mitigar os ataques de shell injection se ainda precisar. Prefira usar `child_process.execFile` que, por definição, só executará um único comando com um conjunto de atributos e não permitirá a expansão de parâmetros do shell.

**Caso contrário:** O uso ingênuo de processos filhos pode resultar na execução de comandos remotos ou em ataques de shell injection, devido à entrada do usuário mal-intencionado passada para um comando do sistema não-autorizado.

🔗 [**Leia Mais: Tenha cautela ao trabalhar com processos filhos**](./sections/security/childprocesses.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.20. Oculte detalhes de erros dos usuários

<a href="https://www.owasp.org/index.php/Top_10-2017_A6-Security_Misconfiguration" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A6:Security%20Misconfiguration%20-green.svg" alt=""/></a>

**TL;DR:** Um manipulador de erros integrado do express oculta os detalhes de erros por padrão. Entretanto, são grandes as chances de você implementar sua própria lógica para manipular erros com objetos de erro customizados (considerado por muitos, a melhor prática). Se você faz isso, tenha certeza de que não está retornando o objeto Error inteiro para o cliente, pois ele pode conter detalhes confidenciais da aplicação.

**Caso contrário:** Detalhes confidenciais da aplicação como caminhos e arquivos do servidor, módulos de terceiros em uso e outros workflows internos da aplicação poderiam ser explorados e expostos por um invasor.

🔗 [**Leia Mais: Oculte detalhes de erros dos usuários**](./sections/security/hideerrors.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.21. Configure 2FA para o npm ou Yarn

<a href="https://www.owasp.org/index.php/Top_10-2017_A6-Security_Misconfiguration" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A6:Security%20Misconfiguration%20-green.svg" alt=""/></a>

**TL;DR:** Qualquer passo na cadeia de desenvolvimento deve ser protegido com o MFA (multi-factor authentication, ou autenticação em várias etapas), e o npm / Yarn é uma boa oportunidade para os invasores poderem colocar as mãos na senha de algum desenvolvedor. Usando as credenciais de desenvolvedor, os invasores podem injetar código malicioso em bibliotecas que são amplamente instaladas em projetos e serviços. Talvez, até mesmo por toda a rede de internet, se publicado abertamente. Ativando a 2-factor-authentication (autenticação em duas etapas) no npm, reduz a quase zero as chances de invasores alterarem seu código.

**Caso contrário:** [Você já ouviu falar sobre o desenvolvedor do eslint cuja senha foi hackeada?](https://medium.com/@oprearocks/eslint-backdoor-what-it-is-and-how-to-fix-the-issue-221f58f1a8c8)

<br/><br/>

## ![✔] 6.22. Modifique as configurações do middleware de sessão

<a href="https://www.owasp.org/index.php/Top_10-2017_A6-Security_Misconfiguration" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A6:Security%20Misconfiguration%20-green.svg" alt=""/></a>

**TL;DR:** Cada framework e tecnologia web tem seus pontos fracos conhecidos - dizer aos invasores qual framework utilizamos é uma grande ajuda para eles. Usar as configurações padrões para middlewares de sessão pode expor sua aplicação - e ataques específicos ao framework, semelhantes ao heade `X-Powered-By` header. Tente ocultar qualquer coisa que possa identificar ou revelar sua stack (por exemplo, Node.js, express).

**Caso contrário:** Cookies podem ser enviados através de conexões não seguras, e um hacker pode usar a sessão do usuário para identificar o framework utilizado na aplicação, bem como vulnerabilidades específicas do módulo.

🔗 [**Leia Mais: Segurança de cookies e sessões**](./sections/security/sessions.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.23. Evite ataques do DOS definindo explicitamente quando um processo deve falhar

<a href="https://www.owasp.org/index.php/Denial_of_Service" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20DDOS%20-green.svg" alt=""/></a>

**TL;DR:** O processo do Node irá falhar quando os erros não forem tratados. Muitas boas práticas recomendam sair, mesmo que um erro tenha sido detectado e resolvido. O Express, por exemplo, irá falhar em qualquer erro assíncrono - a menos que você envolva rotas com uma cláusula catch. Isso abre um ponto de ataque muito fácil para os hackers que reconhecem qual entrada faz o processo falhar e enviam repetidamente o mesmo request. Não existe solução instantânea para isso, mas algumas técnicas podem aliviar a dor: Alertar com severidade crítica sempre que um processo falha devido a um erro não tratado, validar a entrada e evitar travar o processo devido à entrada inválida do usuário, envolver todas as rotas com uma cláusula catch e considerar não travar quando um erro é originado em uma solicitação o que acontece globalmente).

**Caso contrário:** Este é apenas um palpite: dado muitos aplicações Node.js, se tentarmos passar um JSON vazio para todas as solicitações POST, um punhado de aplicações falhará. Nesse ponto, podemos apenas repetir o envio da mesma solicitação para derrubar as aplicações com facilidade.

<br/><br/>

## ![✔] 6.24. Impeça redirecionamentos não seguros

<a href="https://www.owasp.org/index.php/Top_10-2017_A1-Injection" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20OWASP%20Threats%20-%20A1:Injection%20-green.svg" alt=""/></a>

**TL;DR:** Redirecionamentos que não validam a entrada do usuário podem permitir que invasores iniciem tentativas de phishing, roubem credenciais de usuários e executem outras ações mal-intencionadas.

**Caso contrário:** Se um invasor descobrir que você não está validando informações externas fornecidas pelo usuário, ele poderá explorar essa vulnerabilidade postando links especialmente em fóruns, mídias sociais e outros locais públicos para que os usuários cliquem.

🔗 [**Leia Mais: Impeça redirecionamentos não seguros**](./sections/security/saferedirects.brazilian-portuguese.md)

<br/><br/>

## ![✔] 6.25. Evite publicar segredos no registro do npm

<a href="https://www.owasp.org/index.php/Top_10-2017_A6-Security_Misconfiguration" target="_blank"><img src="https://img.shields.io/badge/%E2%9C%94%20Ameaças%20OWASP%20-%20A6:Configuração%20Incorreta%20de%20Segurança%20-green.svg" alt=""/></a>

**TL;DR:** Precauções devem ser tomadas para evitar o risco de publicação acidental de segredos nos registros públicos do npm. Um arquivo `.npmignore` pode ser usado para colocar arquivos ou pastas específicos em uma blacklist, ou a lista `files` no `package.json` pode atuar como uma whitelist.

**Caso contrário:** As chaves, as senhas ou outros segredos da API do seu projeto estão sujeitos a abusos por qualquer pessoa que os encontre, o que pode resultar em perda financeira, falsificação de identidade e outros riscos.

🔗 [**Leia Mais: Evite publicar segredos**](./sections/security/avoid_publishing_secrets.brazilian-portuguese.md)
<br/><br/><br/>

<p align="right"><a href="#índice">⬆ Voltar ao topo</a></p>

# `7. Boas Práticas em Performance`

## Nossos colaboradores estão trabalhando nesta seção. [Gostaria de participar?](https://github.com/goldbergyoni/nodebestpractices/issues/256)

## ![✔] 7.1. Prefira métodos JS nativos ao invés de utilitários de usuário, como o Lodash

**TL;DR:** Muitas vezes é mais complicado usar bibliotecas de utilitários como o `lodash` e `underscore` sobre os métodos nativos, pois leva a dependências desnecessárias e desempenho mais lento.
Tenha em mente que, com a introdução do novo motor V8 juntamente com os novos padrões ES, os métodos nativos foram aprimorados de tal forma que agora ele tem cerca de 50% a mais de desempenho que as bibliotecas de utilitários.

**Caso contrário:** Você terá que manter projetos de menor desempenho onde você poderia simplesmente ter usado o que **já estava** disponível ou lidar com mais algumas linhas em troca de mais alguns arquivos.

🔗 [**Leia Mais: Prefira métodos nativos ao invés de utilitários do usuário como Lodash**](./sections/performance/nativeoverutil.brazilian-portuguese.md)

<br/><br/><br/>

# Feitos

Para manter este guia e deixá-lo atualizado, estamos constantemente atualizando e aprimorando as diretrizes e as práticas recomendadas com a ajuda da comunidade. Você pode acompanhar nossos [feitos](https://github.com/goldbergyoni/nodebestpractices/milestones) e se juntar aos grupos de trabalho, caso queira contribuir com este projeto.

<br/>

## Traduções

Todas as traduções são contribuições da comunidade. Nós ficaremos felizes em obter ajuda com traduções concluídas, em andamento, ou mesmo com novas traduções!

### Traduções concluídas

- ![BR](./assets/flags/BR.png) [Português Brasileiro](./README.brazilian-portuguese.md) - Cortesia de [Marcelo Melo](https://github.com/marcelosdm)
- ![CN](./assets/flags/CN.png) [Chinês](README.chinese.md) - Cortesia de [Matt Jin](https://github.com/mattjin)
- ![EU](./assets/flags/EU.png) [Vasco](README.basque.md) - Cortesia de [Ane Diaz de Tuesta](https://github.com/anediaz) & Joxefe Diaz de Tuesta

### Traduções em andamento

- ![FR](./assets/flags/FR.png) [Francês](https://github.com/gaspaonrocks/nodebestpractices/blob/french-translation/README.french.md) ([Discussão](https://github.com/goldbergyoni/nodebestpractices/issues/129))
- ![HE](./assets/flags/HE.png) Hebraico ([Discussão](https://github.com/goldbergyoni/nodebestpractices/issues/156))
- ![KR](./assets/flags/KR.png) [Coreano](https://github.com/goldbergyoni/nodebestpractices/blob/korean-translation/README.md) ([Discussão](https://github.com/goldbergyoni/nodebestpractices/issues/94))
- ![RU](./assets/flags/RU.png) [Russo](https://github.com/goldbergyoni/nodebestpractices/blob/russian-translation/README.russian.md) ([Discussão](https://github.com/goldbergyoni/nodebestpractices/issues/454))
- ![ES](./assets/flags/ES.png) [Espanhol](https://github.com/goldbergyoni/nodebestpractices/blob/spanish-translation/README.spanish.md) ([Discussão](https://github.com/goldbergyoni/nodebestpractices/issues/95))
- ![TR](./assets/flags/TR.png) Turco ([Discussão](https://github.com/goldbergyoni/nodebestpractices/issues/139))

<br/><br/>

## Comitê Diretivo

Conheça os membros do comitê diretivo - as pessoas que trabalham juntas para fornecer orientação e direção futura para o projeto. Além disso, cada membro do comitê lidera um projeto rastreado em nossos [projetos do Github](https://github.com/goldbergyoni/nodebestpractices/projects).

<img align="left" width="100" height="100" src="assets/images/members/yoni.png"/>

[Yoni Goldberg](https://github.com/goldbergyoni)
<a href="https://twitter.com/goldbergyoni"><img src="assets/images/twitter-s.png" width="16" height="16"></img></a>
<a href="https://goldbergyoni.com"><img src="assets/images/www.png" width="16" height="16"></img></a>

Consultor de Node.js independente, que trabalha com clientes nos EUA, Europa e Israel, na criação de aplicações Node dimensionáveis em grande escala. Muitas das melhores práticas acima foram publicadas primeiro em um post em seu blog em [goldbergyoni.com](https://goldbergyoni.com). Encontre-o como @goldbergyoni ou me@goldbergyoni.com

<br/>

<img align="left" width="100" height="100" src="assets/images/members/bruno.png"/>

[Bruno Scheufler](https://github.com/BrunoScheufler)
<a href="https://brunoscheufler.com/"><img src="assets/images/www.png" width="16" height="16"></img></a>

💻 full-stack web engineer e entusiasta de Node.js & GraphQL

<br/>

<img align="left" width="100" height="100" src="assets/images/members/kyle.png"/>

[Kyle Martin](https://github.com/js-kyle)
<a href="https://twitter.com/kylemartin_93"><img src="assets/images/twitter-s.png" width="16" height="16"></img></a>
<a href="https://www.linkedin.com/in/kylemartinnz"><img src="assets/images/linkedin.png" width="16" height="16"></img></a>

Full Stack Developer e Engenheiro de Confiabilidade de Sites com sede na Nova Zelândia, interessados ​​em segurança de aplicativos da Web, e arquitetando e construindo aplicativos Node.js para executar em escala global.

<br/>

<img align="left" width="100" height="100" src="assets/images/members/sagir.png"/>

[Sagir Khan](https://github.com/sagirk)
<a href="https://twitter.com/sagir_k"><img src="assets/images/twitter-s.png" width="16" height="16"></img></a>
<a href="https://sagirk.com"><img src="assets/images/www.png" width="16" height="16"></img></a>
<a href="https://linkedin.com/in/sagirk"><img src="assets/images/linkedin.png" width="16" height="16"></img></a>

Especialista profundo em JavaScript e seu ecossistema - React, Node.js, MongoDB, praticamente qualquer coisa que envolva o uso de JavaScript/JSON em qualquer camada do sistema - criando produtos usando a plataforma da web para as marcas mais reconhecidas do mundo. Membro individual da "Node.js Foundation", colaborando em "Community Committee's Website Redesign Initiative".

<br/>

## Colaboradores

Obrigado a todos nossos colaboradores! 🙏

Nossos colaboradores são membros que estão contribuindo com o repositório em base regular, sugerindo novas práticas recomendadas, triando problemas, analisando solicitações de pull e muito mais. Se você estiver interessado em nos ajudar a orientar milhares de pessoas a criar melhores aplicações Node.js, leia nossas [diretrizes de colaborador](./.operations/CONTRIBUTING.md) 🎉

| <a href="https://github.com/idori" target="_blank"><img src="assets/images/members/ido.png" width="75" height="75"/></a> | <a href="https://github.com/TheHollidayInn" target="_blank"><img src="assets/images/members/keith.png" width="75" height="75"/></a> |
| :---------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------: |
|                                    [Ido Richter (Founder)](https://github.com/idori)                                    |                                        [Keith Holliday](https://github.com/TheHollidayInn)                                         |

### Colaboradores anteriores

| <a href="https://github.com/refack" target="_blank"><img src="assets/images/members/refael.png" width="50" height="50"/></a> |
| :-------------------------------------------------------------------------------------------------------------------------: |
|                                        [Refael Ackermann](https://github.com/refack)                                        |

<br/>

## Thank You Notes

We appreciate any contribution, from a single word fix to a new best practice. View our contributors and [contributing documentation here!](./README.md#contributors-)

<br/><br/><br/>
