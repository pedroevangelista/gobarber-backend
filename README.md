# GoBarber App

## Recuperação de senha

**RF (Requisitos Funcionais)**

- O usuário deve poder recuperar sua senha informando seu e-mail;
- O usuário deve receber um e-mail com instruções de recuperação de senha;
- O usuário deve poder resetar sua senha;

**RNF (Requisitos Não Funcionais)**

- Utilizar Mailtrap para testar envios em ambiente de dev;
- Utilizar Amazon SES para envios em produção;
- O envio de e-mails deve acontecer em segundo plano (background job);


**Regras de Negócio**

- O link enviado por e-mail para resetar senha deve expirar em 2h;
- O usuário precisa confirmar a nova senha ao resetar;


## Atualização do perfil

**RF (Requisitos Funcionais)**

- O usuário deve poder atualizar seu nome, e-mail e senha;

**Regras de Negócio**

- O usuário não pode alterar seu e-mail para um e-mail já utilizado;
- Para atualizar sua senha, o usuário deve informar a senha antiga;
- Para atualizar sua senha, o usuário previsa confirmar a nova senha;

## Painel do prestador

**RF (Requisitos Funcionais)**

- O usuário deve poder listar seus agendamentos de um dia específico;
- O prestador deve receber uma notificação sempre que houver um novo agendamento;
- O prestador deve poder visualizar as notificações não lidas;

**RNF (Requisitos Não Funcionais)**

- Os agendamentos do prestador do dia devem ser armazenados em cache;
- As notificações do prestador devem ser armazenadas no MongoDB;
- As notificações do prestador devem ser enviadas em tempo-real utilizando Socket.io;

**Regras de Negócio**

- A notificação deve ter um status de lida ou não-lida para que o prestador possa controlar;

## Agendamento de serviços

**RF (Requisitos Funcionais)**

- O usuário deve poder listar todos os prestadores de serviço cadastrador;
- O usuário deve poder listar os dias de um mês com pelo menos um horário disponível de um prestador;
- O usuário deve poder listar os horários disponíveis em um dia específico de um prestador;
- O usuário deve poder realizar um novo agendamento com um prestador;

**RNF (Requisitos Não Funcionais)**

- A listagem de prestadores deve ser armazenada em cache;

**Regras de Negócio**

- Cada agendamento deve durar 1h exatamente;
- Os agendamentos devem estar disponíveis entre 8h às 18h (Primeiro às 8, último às 17h);
- O usuário não pode agendar em um horário já ocupado;
- O usuário não pode agendar em um horário que já passou;
- O usuário não pode agendar serviços consigo mesmo;
