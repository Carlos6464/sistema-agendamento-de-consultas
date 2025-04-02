# Sistema de Gestão de Agendamentos Médicos - Laravel

Este repositório contém a implementação do backend do **Sistema de Gestão de Agendamentos Médicos** utilizando **Laravel**.

## Tecnologias Utilizadas

- **Backend:** Laravel (PHP)
- **Banco de Dados:** Oracle
- **Autenticação:** JWT (JSON Web Token)
- **Integração:** APIs de Saúde (TISS, TUSS)
- **Testes:** Pest
- **Metodologia:** Agile (Scrum)

## Requisitos Funcionais (Laravel)

### 1. Módulo de Autenticação

- [RF-01] O sistema deve permitir o cadastro de pacientes e médicos.
- [RF-02] O sistema deve permitir login e autenticação via JWT.
- [RF-03] O sistema deve permitir recuperação de senha via e-mail.

### 2. Módulo de Agendamento

- [RF-04] O paciente deve poder agendar consultas com base na disponibilidade dos médicos.
- [RF-05] O sistema deve permitir a edição e cancelamento de consultas.
- [RF-06] Os médicos devem visualizar seus agendamentos.
- [RF-07] O sistema deve permitir confirmação de consulta pelo paciente.

### 3. Módulo de Integração

- [RF-08] O sistema deve se integrar com APIs de saúde (TISS, TUSS) para validar informações.
- [RF-09] O sistema deve permitir a consulta de histórico de agendamentos.

## Requisitos Não Funcionais

- [RNF-01] A API deve seguir o padrão RESTful.
- [RNF-02] A API deve suportar autenticação via JWT.
- [RNF-03] O sistema deve suportar pelo menos 1000 usuários simultâneos.

## Endpoints da API

### 1. Autenticação

```http
POST /api/register
```
- Cadastra um novo usuário (paciente ou médico).

```http
POST /api/login
```
- Autentica um usuário e retorna um token JWT.

### 2. Agendamentos

```http
GET /api/appointments
```
- Lista todas as consultas agendadas.

```http
POST /api/appointments
```
- Cria um novo agendamento.

```http
PUT /api/appointments/{id}
```
- Atualiza um agendamento existente.

```http
DELETE /api/appointments/{id}
```
- Cancela um agendamento.

### 3. Integração com APIs de Saúde

```http
GET /api/health-data/{patientId}
```
- Consulta dados de saúde do paciente via API (TISS/TUSS).

## Fluxo do Sistema

### 1. Fluxo de Autenticação

1. Usuário acessa a tela de login e insere suas credenciais.
2. O sistema autentica via JWT e retorna um token.
3. O token é armazenado e usado nas próximas requisições.

### 2. Fluxo de Agendamento

1. O paciente acessa o painel de agendamentos.
2. O sistema exibe os horários disponíveis dos médicos.
3. O paciente seleciona um horário e confirma o agendamento.
4. O sistema registra a consulta no banco de dados.

### 3. Fluxo de Integração com APIs de Saúde

1. O sistema consulta informações do paciente via API (TISS, TUSS).
2. A API retorna os dados validados.
3. O sistema exibe informações atualizadas sobre o histórico médico do paciente.

## Como Rodar o Projeto

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/nome-do-projeto.git
   cd nome-do-projeto
   ```

2. Instale as dependências:
   ```bash
   composer install
   ```

3. Configure o arquivo `.env`:
   ```bash
   cp .env.example .env
   ```
   Edite as credenciais do banco de dados e gere a chave da aplicação:
   ```bash
   php artisan key:generate
   ```

4. Execute as migrações do banco de dados:
   ```bash
   php artisan migrate
   ```

5. Rode o servidor de desenvolvimento:
   ```bash
   php artisan serve
   ```

## Testes

Para rodar os testes com **Pest**, utilize o seguinte comando:
```bash
php artisan test
```

## Contribuição

1. Fork o repositório
2. Crie uma branch para sua funcionalidade (`git checkout -b minha-feature`)
3. Commit suas mudanças (`git commit -m 'Adiciona minha funcionalidade'`)
4. Envie para o repositório (`git push origin minha-feature`)
5. Abra um Pull Request

## Licença

Este projeto está licenciado sob a MIT License - veja o arquivo [LICENSE](LICENSE) para mais detalhes.



<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[WebReinvent](https://webreinvent.com/)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Jump24](https://jump24.co.uk)**
- **[Redberry](https://redberry.international/laravel/)**
- **[Active Logic](https://activelogic.com)**
- **[byte5](https://byte5.de)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
