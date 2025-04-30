DOCUMENTO DE REQUISITOS

Projeto: FiadoFácil 
Cliente: Vendedores ambulantes
Responsáveis: Klebson Davi de Souza Magalhães


Versão
Data
Descrição
Autor
1.0
30/04/2025
Escrita dos requisitos
Klebson











1. Introdução

O propósito deste documento é especificar os principais requisitos do sistema que visa apoiar o controle de vendas fiadas realizado por vendedores ambulantes. O sistema será utilizado para gerenciar o cadastro de clientes, registrar vendas fiadas, controlar pagamentos, emitir relatórios e garantir a segurança e portabilidade das informações, mesmo em ambientes offline.
1.1. Propósito
O objetivo deste documento é detalhar os requisitos funcionais e não funcionais do FiadoFácil. Esses requisitos servirão como base para o desenvolvimento, validação e futura manutenção da aplicação.

2. Requisitos funcionais:

RF01
Nome: 
Cadastro de Cliente
Descrição: 
O sistema deve permitir que o vendedor ambulante cadastre informações de novos clientes, como nome, CPF, endereço e telefone, para que possam ser realizadas vendas fiadas posteriormente.
Atores: 
Vendedor
Prioridade: 
Alta
Anexo: 
Formulário de cadastro do cliente.
Entradas e pré-condições: 
O vendedor deve estar logado no sistema.
O cliente deve fornecer os dados necessários para o cadastro.
Saídas e pós-condições: 
O cliente será cadastrado no sistema.
O cliente terá um saldo devedor inicial de R$ 0,00.
Fluxos de eventos 
Fluxo principal: 
O vendedor acessa o menu de cadastro de clientes.
O vendedor preenche as informações do cliente no formulário.
O vendedor clica no botão "Cadastrar".
O sistema salva os dados e confirma o cadastro.
Fluxo secundário 1:
Caso algum campo obrigatório não seja preenchido, o sistema exibe uma mensagem de erro solicitando o preenchimento correto dos dados.


RF02
Nome: 
Realizar Venda Fiada
Descrição: 
O sistema deve permitir ao vendedor registrar uma venda fiada para um cliente já cadastrado, com o valor da venda sendo acrescido ao saldo devedor do cliente.
Atores: 
Vendedor
Prioridade: 
Alta
Anexo: 
Formulário de registro de venda.
Entradas e pré-condições: 
O cliente deve estar cadastrado no sistema.
O vendedor deve ter acesso ao menu de vendas.
O valor da venda deve ser informado.


Saídas e pós-condições: 
O valor da venda é somado ao saldo devedor do cliente.
O sistema gera um recibo da venda fiada.
Fluxos de eventos 
Fluxo principal: 
O vendedor acessa o menu de vendas.
O vendedor seleciona o cliente para a venda fiada.
O vendedor informa o valor da venda.
O sistema registra o valor e atualiza o saldo devedor do cliente.
O sistema gera um recibo com os detalhes da venda.
Fluxo secundário 1:
Caso o valor da venda seja superior ao saldo disponível do cliente (se houver esse controle), o sistema exibe uma mensagem de erro e não permite a venda.



RF03
Nome: 
Consulta de saldo devedor do cliente
Descrição: 
O sistema deve permitir ao vendedor consultar o saldo devedor de um cliente, exibindo o valor total das compras fiadas e o valor restante a ser pago.
Atores: 
Vendedor
Prioridade: 
Alta
Anexo: 
Tela de consulta de saldo devedor 
Entradas e pré-condições: 
O cliente deve estar cadastrado no sistema.
O vendedor deve estar logado e com permissão para acessar o saldo do cliente.
Saídas e pós-condições: 
O sistema exibe o saldo devedor atualizado.
O sistema exibe a data da última venda fiada.
Fluxos de eventos 
Fluxo principal: 
O vendedor acessa o menu de consulta de saldo.
O vendedor seleciona o cliente.
O sistema exibe o saldo devedor atualizado e a data da última compra fiada.
Fluxo secundário 1:
Caso o cliente não esteja cadastrado, o sistema exibe uma mensagem de erro informando que o cliente não foi encontrado.



RF04
Nome: 
Registro de Pagamento de Fiado
Descrição: 
O sistema deve permitir ao vendedor registrar um pagamento de um cliente, reduzindo o saldo devedor conforme o valor pago.
Atores: 
Vendedor
Prioridade: 
Alta
Anexo: 
Tela de pagamento de fiado
Entradas e pré-condições: 
O cliente deve estar cadastrado no sistema.
O vendedor deve ter acesso ao menu de pagamentos.
O valor pago deve ser informado.
Saídas e pós-condições: 
O saldo devedor do cliente é atualizado com a redução do valor pago.
O sistema gera um comprovante de pagamento.
Fluxos de eventos 
Fluxo principal: 
O vendedor acessa o menu de pagamentos.
O vendedor seleciona o cliente e informa o valor pago.
O sistema atualiza o saldo devedor e gera um comprovante de pagamento.
O sistema exibe o novo saldo devedor do cliente.
Fluxo secundário 1:
Caso o valor do pagamento seja maior que o saldo devedor, o sistema exibe uma mensagem de erro informando que o pagamento é excessivo.





RF05
Nome: 
Emissão de relatório de vendas fiadas
Descrição: 
O sistema deve gerar relatórios das vendas fiadas realizadas, incluindo informações como cliente, data, valor da venda e saldo devedor.
Atores: 
Vendedor, administrador
Prioridade: 
Média
Anexo: 
Relatório de vendas fiadas 
Entradas e pré-condições: 
O vendedor ou administrador deve estar logado no sistema.
O sistema deve conter registros de vendas fiadas.
Saídas e pós-condições: 
O relatório é gerado em formato PDF ou planilha (Excel).
O relatório contém todos os dados das vendas fiadas realizadas.
Fluxos de eventos 
Fluxo principal: 
O vendedor ou administrador acessa o menu de relatórios.
O vendedor ou administrador seleciona o período de consulta.
O sistema gera o relatório de vendas fiadas e permite o download ou impressão.
Fluxo secundário 1:
Caso não existam vendas fiadas no período selecionado, o sistema exibe uma mensagem informando que nenhum dado foi encontrado.



3. Requisitos não funcionais:


RNF01
Nome: 
Disponibilidade Offline
Descrição: 
O sistema deve funcionar sem necessidade de conexão com a internet, permitindo ao vendedor utilizar todas as funcionalidades básicas offline.
Atores: 
Vendedor
Prioridade: 
Alta
Anexo: 
Especificação de funcionamento offline.
Entradas e pré-condições: 
O sistema deve estar instalado no dispositivo do vendedor.
Os dados devem ser armazenados localmente.
Saídas e pós-condições: 
O vendedor consegue utilizar o sistema mesmo sem acesso à internet.
Quando a conexão for restabelecida, o sistema pode sincronizar dados (caso desejado).
Fluxos de eventos 
Fluxo principal: 
O sistema é aberto sem conexão à internet.
O vendedor realiza operações normalmente (cadastro, vendas, pagamentos).
Os dados são salvos no armazenamento local do dispositivo.
Fluxo secundário 1:
–



RNF02
Nome: 
Interface Acessível por Celular
Descrição: 
A interface do sistema deve ser responsiva e otimizada para uso em dispositivos móveis, como smartphones.
Atores: 
Vendedor
Prioridade: 
Alta
Anexo: 
Protótipos responsivos.
Entradas e pré-condições: 
O sistema deve ser acessado por um dispositivo móvel.
Saídas e pós-condições: 
A interface se adapta automaticamente ao tamanho da tela.
Fluxos de eventos 
Fluxo principal: 
O vendedor acessa o sistema em um celular.
A interface ajusta elementos visuais para boa usabilidade (botões, campos, menus).
O vendedor realiza todas as operações com conforto visual e operacional.
Fluxo secundário 1:
Caso o vendedor tenha dificuldade, o sistema deve exibir dicas ou um tutorial para guiá-lo.



RNF03
Nome: 
Armazenamento Seguro Local
Descrição: 
Todos os dados devem ser armazenados localmente de forma segura, usando criptografia para proteger informações sensíveis.
Atores: 
Sistema
Prioridade: 
Alta
Anexo: 
Política de segurança de dados
Entradas e pré-condições: 
O sistema deve implementar métodos de criptografia local.
Saídas e pós-condições: 
Os dados do cliente e transações estão protegidos contra acesso indevido.
Fluxos de eventos 
Fluxo principal: 
O sistema salva dados no dispositivo.
Os dados são criptografados automaticamente.
Apenas o aplicativo autorizado consegue ler e manipular os dados.
Fluxo secundário 1:
….



RNF04
Nome: 
Respostas rápidas (menos de 2 segundos)
Descrição: 
As funcionalidades do sistema devem responder em no máximo 2 segundos para garantir fluidez no uso.
Atores: 
Sistema
Prioridade: 
Alta
Anexo: 
Resultados de testes de desempenho
Entradas e pré-condições: 
O sistema deve estar em uso regular.
A base de dados deve estar em condições normais (sem excesso de registros).
Saídas e pós-condições: 
O tempo de resposta de cada operação é menor que 2 segundos.
Fluxos de eventos 
Fluxo principal: 
O vendedor executa uma operação (como consulta, venda ou cadastro).
O sistema processa e responde em até 2 segundos.


Fluxo secundário 1:





RF ou RNF05
Nome: 
Exportação dos Dados (formato CSV)
Descrição: 
O sistema deve permitir a exportação de registros (clientes, vendas, pagamentos) em arquivos no formato CSV.
Atores: 
Vendedor, Administrador
Prioridade: 
Média
Anexo: 
Exemplo de arquivos CSV exportados.
Entradas e pré-condições: 
O usuário seleciona o tipo de dado a ser exportado.
O sistema tem dados válidos para exportação.
Saídas e pós-condições: 
O sistema gera um arquivo .csv com os dados estruturados.
Fluxos de eventos 
Fluxo principal: 
O usuário acessa a opção de exportação.
O usuário seleciona o que deseja exportar (clientes, vendas etc.).
O sistema gera o arquivo CSV e disponibiliza para download.
Fluxo secundário 1:





RF ou RNF #
Nome: 


Descrição: 


Atores: 


Prioridade: 


Anexo: 
 ---- 
Entradas e pré-condições: 


Saídas e pós-condições: 


Fluxos de eventos 
Fluxo principal: 
1.  … 
Fluxo secundário 1:







