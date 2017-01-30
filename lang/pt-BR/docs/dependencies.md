* * *

id: docs_dependencies guide: docs_dependencies layout: guide additional_reading_tags: ["package-json", "yarn-lock"]

* * *

Dependências de pacotes são essenciais para o sucesso de um pacote. Quando você desenvolve a funcionalidade d o seu pacote, você provavelmente usará código existente definido em outros pacotes. Esses Pacotes estão se tornam dependências do seu projeto.

Seu arquivo `package.json` é o lugar de declaração de todas as suas dependências, de desenvolvimento a produção a opcional. Você irá especificar tanto o nome do pacote como informação sobre a versão mínima de cada dependência.

Seu arquivo `yarn.lock` garante que seu pacote é consistente em instalações armazenando as versões de cada dependência são instaladas no seu pacote.