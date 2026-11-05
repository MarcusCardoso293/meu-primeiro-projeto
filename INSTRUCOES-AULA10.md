# Aula 10 - JWT e ViaCEP

## Preparar

Abra um terminal na pasta `api` e execute:

```bash
npm install
```

Copie `.env.example` para `.env` e troque `JWT_SECRET` por uma chave secreta de sua escolha.

Na primeira execução, crie os dados de exemplo:

```bash
node src/database/seed.js
```

Inicie a API:

```bash
npm start
```

## Testes

- `GET http://localhost:3001/api/health`
- `POST http://localhost:3001/api/auth/login` com JSON `{"email":"contato@technova.com","senha":"123456"}`
- `POST http://localhost:3001/api/vagas` sem token deve retornar 401.
- `POST http://localhost:3001/api/vagas` com `Authorization: Bearer SEU_TOKEN`, JSON `{"titulo":"Vaga Autenticada","tipo":"remoto","tecnologias":"Node"}` deve retornar 201.
- `GET http://localhost:3001/api/cep/01310100` deve retornar São Paulo / SP.
- `GET http://localhost:3001/api/cep/00000000` deve retornar 404.

O `package-lock.json` será atualizado pelo `npm install` para incluir as novas dependências. O ZIP original não foi alterado.
