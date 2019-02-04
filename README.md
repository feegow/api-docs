---
title: API Feegow v.1.0
language_tabs:
  - http: HTTP
toc_footers:
  - >-
    <a href="https://www.feegowclinic.com.br/">feegow clinic</a>
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

# Autorização

Para realizar qualquer tipo de requisição (GET, POST) nos endpoints da API você precisa de uma chave de autorização.
Chamamos essa chave de **Token**.

Para utilizar o Token nas requisições basta adiciona-lo ao header com a chave **x-access-token**.

*Exemplo*: <br>
**x-access-token:** eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyTA...

*Em caso de dúvidas entre em contato com nosso suporte.*


<h1 id="company">Empresa</h1>


## Listar unidades

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/company/list-unity
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": {
        "matriz": [
            {
                "unidade_id" : 0,
                "nome_fantasia": "Matriz",
                "cnpj": "11.111.111.0001-16",
                "endereco": "Jose",
                "cep": "03502-060",
                "numero": "12",
                "bairro": "Sobradinho",
                "telefone_1": "(21) 1111-1111",
                "telefone_2": "(21) 2222-2222",
                "email_1": "josebaroni@feegow.com.br",
                "email_2": "maiavinicius@feegow.com.br"
            }
        ],
        "unidades": [
            {
                "unidade_id" : 6,
                "nome_fantasia": "Filial",
                "cnpj": "11.111.111.0001-16",
                "endereco": "Estrada do Guanumbi",
                "cep": "22745-200",
                "numero": "000",
                "bairro": "Freguesia (Jacarepaguá)",
                "telefone_1": "(21) 1111-1111",
                "telefone_2": "(21) 2222-2222",
                "email_1": "josebaroni@feegow.com.br",
                "email_2": "maiavinicius@feegow.com.br"
            }
        ]
    }
}

```

`GET /company/list-unity`

Lista as informações de unidades e matriz da sua clínica.


<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|

## Listar locais

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/company/list-local
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "id": 1,
            "local": "Sala 01",
            "unidade_id": 6
        },
        {
            "id": 2,
            "local": "Sala 02",
            "unidade_id": 6
        },
        {
            "id": 3,
            "local": "Sala 01",
            "unidade_id": 0
        },
        {
            "id": 4,
            "local": "Sala 04",
            "unidade_id": 0
        },
        {
            "id": 5,
            "local": "Sala 05",
            "unidade_id": 0
        },
        {
            "id": 6,
            "local": "Sala 06",
            "unidade_id": 0
        },
        {
            "id": 7,
            "local": "Sala 07",
            "unidade_id": 0
        },
        {
            "id": 8,
            "local": "Sala 08",
            "unidade_id": 0
        },
        {
            "id": 9,
            "local": "Sala 09",
            "unidade_id": 0
        },
        {
            "id": 10,
            "local": "Sala 10",
            "unidade_id": 0
        },
        {
            "id": 11,
            "local": "Sala 11",
            "unidade_id": 0
        },
        {
            "id": 12,
            "local": "Sala 15",
            "unidade_id": 0
        },
        {
            "id": 13,
            "local": "Sala 17",
            "unidade_id": 0
        },
        {
            "id": 14,
            "local": "Sala 18",
            "unidade_id": 0
        },
        {
            "id": 15,
            "local": "Centro Cirúrgico",
            "unidade_id": 0
        },
        {
            "id": 16,
            "local": "k",
            "unidade_id": 0
        },
        {
            "id": 17,
            "local": "Sala triagem",
            "unidade_id": 6
        }
    ]
}

```

`GET /company/list-local`

Lista os locais relacionados 


<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


<h1 id="reports">Relatórios</h1>


## Listar relatórios

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/reports/list
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Exemplo Resposta
```json
[
    {
        "id": 53,
        "Ct": "Agenda",
        "Relatorio": "Agendamentos",
        "Arquivo": "schedule-appointments",
        "sysActive": 1,
        "Permissoes": "relatoriosagendaV"
    },
    {
        "id": 49,
        "Ct": "Agenda",
        "Relatorio": "Atendimentos",
        "Arquivo": "duration-of-service",
        "sysActive": 1,
        "Permissoes": "relatoriosagendaV"
    }
]

```

`GET /reports/list`

Lista os relatórios disponíveis para utilização.


<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|

## Gerar Relatório

> Exemplo Request
```http
POST http://clinic5.feegow.com.br/components/public/api/reports/generate
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Exemplo Resposta
```json
{
    "success": true,
    "reportId": 49,
    "route": "duration-of-service",
    "reportName": "Atendimentos",
    "columns": false,
    "filters": false,
    "data": [
        {
            "id": 2274,
            "PacienteID": 4059073,
            "AgendamentoID": 20168920,
            "Data": "22/11/2018",
            "HoraInicio": "08:08",
            "HoraFim": "08:54",
            "Obs": "",
            "sysUser": 13184,
            "ProfissionalID": 8386,
            "Triagem": "N",
            "UsuariosNotificados": null,
            "UnidadeID": 1,
            "TabelaID": null,
            "DHUp": "2018-11-22 08:54:51",
            "TempoProcedimento": "0",
            "DataMensal": "2018-11-22",
            "NomePaciente": "TESTE FEEGOW",
            "Tel1": "(47) 00000-0000",
            "Origem": "",
            "NomeLocal": "Sala 1",
            "LocalID": 21,
            "Quantidade": "1",
            "Valor": 30,
            "Duracao": "46",
            "TempoPermanencia": "55",
            "TempoAtraso": 0,
            "TipoCompromissoID": 96267,
            "EspecialidadeID": 109,
            "NomeProfissional": "JOSÉ SILVA",
            "ProcedimentoID": 96267,
            "TempoEspera": "9",
            "HoraSta": "07:59",
            "Hora": "08:20",
            "PeriodoHora": "Manhã",
            "HoraArredondada": "08:00",
            "NomeProcedimento": "Retorno",
            "NomeUnidade": "CLINICA DE TESTE"
        }
    ]
}

```

`POST /reports/generate`

Gera um relatório específico. 

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**report** <br> |string|Rota do relatório obtida pelo método <a href="#listar-relatórios">Listar relatórios</a> (Parâmetro "Arquivo")|
|**DATA_INICIO** <br> *(opcional)*|date|dd/mm/YYYY|
|**DATA_FIM** <br> *(opcional)*|date|dd/mm/YYYY|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


<aside class="warning">
Existe um limite de 60 dias entre o intervalo das datas para qualquer relatório.
</aside>

## Listar filtros

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/reports/get-filters
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Exemplo Resposta
```json


```

`GET /reports/get-filters`

Obter filtros disponíveis para um relatório. 

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**report** <br> |string|Rota do relatório obtida pelo método <a href="#listar-relatórios">Listar relatórios</a> (Parâmetro "Arquivo")|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|

<h1 id="professional">Profissionais</h1>


## Listar profissionais

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/professional/list
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
  "ativo": true,
  "unidade_id": 1
}

```

> Exemplo Resposta
```json
[
    {
        "profissional_id": 19,
        "nome": "Andre de Paula",
        "CRM": "11.11111-1",
        "especialidades": [
            {
                "especialidade_id": 5,
                "nome_especialidade": "Dermatologia",
                "CBOS": 11111
            }
        ]
    }
]

```

`GET /professional/list`

Lista os nomes e ids dos profissionais. Você pode filtrar por profissional ativo ou inativo.

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**ativo** <br> *(opcional)*|numeric|0 = Profissional inativo <br> 1 = Profissional ativo|
|**<a href="#listar-unidades">unidade_id</a>** <br> *(opcional)*|numeric|ID da unidade|
|**<a href="#listar-especialidades">especialidade_id</a>** <br> *(opcional)*|numeric|ID da da especialidade|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|

<aside class="warning">
O caminho para utilizar o campo foto é
</aside>

## Informações e Especialidades

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/professional/search
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
  "profissional_id": 1
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": {
        "informacoes": [
            {
                "CRM": "11.11111-1",
                "CPF": "111.111.111-1"
                "nome": "Vinicius",
                "foto": "9fb966e7a2e981f16d5b56eea6d90323.jpg",
                "data_nascimento": "02-05-1995",
                "sexo": "Masculino",
                "telefones": [
                    "(21) 2767-1515",
                    ""
                ],
                "celulares": [
                    "(21) 9988-03190",
                    ""
                ],
                "email": "vinicius.feegow@gmail.com",
                "idade_minima": 13
            }
        ],
        "especialidades": [
            {
                "especialidade_id": 5,
                "nome_especialidade": "Dermatologia",
                "CBOS": "225135"
            }
        ]
    }
}

```

`GET /professional/search`

Lista as informações e especialidades do profissional informado.

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**<a href="#professional">profissional_id</a>**|numeric|Identificação do profissional|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|
|409|erro|Profissional não existe|

## Convênios aceitos

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/professional/insurance
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
  "profissional_id": 1
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "convenio_id": 16,
            "nome": "BRADESCO"
        }
    ]
}
```

`GET /professional/insurance`

Lista todos convênios aceitos por um profissional específico.

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**<a href="#professional">profissional_id</a>**|numeric|Identificação do profissional|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


<h1 id="patient">Pacientes</h1>


## Informações

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/patient/search
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
  "paciente_id": 5
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": {
        "nome": "JOSE RENATO BARONI",
        "nascimento": "18-07-1998",
        "sexo": "Masculino",
        "endereco": "AV THIAGO CASTRO",
        "numero": "05",
        "complemento": "CASA",
        "bairro": "CENTRO",
        "cidade": "NATAL",
        "estado": "RJ",
        "cep": "59022020",
        "profissao": "Funcionário Público",
        "telefones": [
            "2907-1177",
            null
        ],
        "celulares": [
            "99762-1587",
            null
        ],
        "documentos": {
            "rg": "11111111111111",
            "cpf": "11111111"
        },
        "email": [
            "josebaroni@feegow.com.br",
            null
        ],
        "convenios": [
            {
                "convenio_id": 5,
                "plano_id": 3,
                "matricula": 21212121,
                "titular": "JOSE BARONI",
                "validade": "2018-05-18"
            },
            {
                "convenio_id": null,
                "plano_id": null,
                "matricula": null,
                "titular": null,
                "validade": null
            },
            {
                "convenio_id": null,
                "plano_id": null,
                "matricula": null,
                "titular": null,
                "validade": null
            }
        ]
    }
}

```

`GET /patient/search`

Busca informações de paciente específico.


<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**<a href="#patient">paciente_id</a>**|numeric|Identificação do paciente|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|
|409|erro|Paciente não existe|


## Listar pacientes

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/patient/list
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
  "limit": 5,
  "offset" : 1
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "patient_id": 9,
            "nome": "ANA CAROLINA GOMES REBELO MELO"
        },
        {
            "patient_id": 10,
            "nome": "ADRIANA GONDIM VIEIRA GONÇALVES"
        },
        {
            "patient_id": 11,
            "nome": "ARTHUR CESAR DANTAS DA SILVA"
        },
        {
            "patient_id": 12,
            "nome": "BRENDA RIBEIRO GIRAO"
        },
        {
            "patient_id": 13,
            "nome": "INGRID RIBEIRO TAVARES"
        }
    ]
}

```

`GET /patient/list`

Lista todos pacientes cadastrados.

Para utilizar o sistema de pagination defina a **posição inicial** (offset) e o **limite de resultados** (limit).

*Exemplo* <br>
**offset:** 5 <br>
**limit:** 10 <br>

Irá retornar 10 registros a partir do quinto.

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**limit** <br> *(opcional)*|numeric|Limite na quantidade de resultados que irão ser retornados|
|**offset** <br> *(opcional)*|numeric|Número de registros que irão ser pulados na requisição|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


## Criar paciente

> Exemplo Request
```http
POST http://clinic5.feegow.com.br/components/public/api/patient/create
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
  "nome_completo": "JOSE RENATO BARONI",
  "cpf" : "11111111111",
  "data_nascimento" : "03-09-1998",
  "genero" : "M",
  "telefone" : "2127678745",
  "email" : "josebaroni@feegow.com.br",
  "origem_id": 1,
  "tabela_id": 5,
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": {
        "paciente_id": 6655
    }
}
```

`POST /patient/create`

Cria um novo paciente e retorna o paciente_id.

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**nome_completo**|string|Nome do paciente|
|**cpf**|numeric|CPF do paciente, 11 digitos <br> *sem pontos e hífen*|
|**email** <br> *(opcional)*|string|E-mail do paciente|
|**data_nascimento** <br> *(opcional)*|date|Data de nascimento do paciente <br>*(dd-mm-yyyy)*|
|**sexo** <br> *(opcional)*|string|M = Masculino <br> F = Feminino|
|**tabela_id** <br> *(opcional)*|string|ID da tabela particular|
|**origem_id** <br> *(opcional)*|string|ID da origem|
|**telefone** <br> *(opcional)*|string|Telefone do paciente|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|

<aside class="warning">
Caso o CPF já esteja cadastrado é retornado o paciente_id
</aside>

## Listar origens

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/patient/list-sources
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "origem_id": 1,
            "nome_origem": "Eventos2"
        }
    ]
}
```

`GET /patient/list-sources`

Lista todas origens.

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|

## Listar tabelas particulares

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/patient/list-privates
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "tabela_id": 1,
            "nome_tabela": "Exemplo"
        }
    ]
}
```

`GET /patient/list-privates`

Lista todas tabelas particulares.

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


<h1 id="specialties">Especialidades</h1>

## Listar especialidades

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/specialties/list
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```


> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "especialidade_id": 157,
            "nome": "Cirurgião dentista (endodontia)"
        },
        {
            "especialidade_id": 98,
            "nome": "Médico dermatologista"
        }
    ]
}

```

`GET /specialties/list`

Lista todas especialidades disponíveis para agendamento.


<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|



<h1 id="financial">Financeiro</h1>

## Listar fornecedores

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/financial/list-suppliers
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "id": 1,
            "nome_fornecedor": "Teste",
            "CEP": null,
            "endereco": null,
            "numero": null,
            "complemento": null,
            "cidade": null,
            "CNPJ": null
        },
        {
            "id": 3,
            "nome_fornecedor": "Teste",
            "CEP": "111111-11",
            "endereco": "rua teste",
            "numero": "12",
            "complemento": "",
            "cidade": "Joinville",
            "CNPJ": "11.111.111/0001-42"
        }
    ]
}
```

`GET /financial/list-suppliers`

Lista os fornecedores da clínica.

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


## Informações do fornecedor

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/financial/search-supplier
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
  "fornecedor_id": 1
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "id": 1,
            "nome_fornecedor": "Teste",
            "CEP": null,
            "endereco": null,
            "numero": null,
            "complemento": null,
            "cidade": null,
            "CNPJ": null
        }
    ]
}
```

`GET /financial/search-supplier`

Busca informações de um fornecedor específico.

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|fornecedor_id|numeric|ID do fornecedor|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


## Listar repasses

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/financial/list-medical-transfer
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
  "success": true,
  "content": [
    {
      "funcao": "executante",
      "valor": 9000,
      "associacao_id": 5,
      "conta_id": 59,
      "criado_em": "2018-01-01 09:10:30",
      "situacao": "PAGO"
    },
    {
      "funcao": "executante",
      "valor": 9500,
      "associacao_id": 5,
      "conta_id": 13,
      "criado_em": "2018-01-01 09:13:30",
      "situacao": "NAO PAGO"
    }
  ]
}

```

`GET /financial/list-medical-transfer`

Busca a listagem de repasses.
**Os valores são tratados em centavos.**

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**data_start**|date|Listar a partir dessa data <br> *dd-mm-YYYY*|
|**data_end**|date|Limitar consulta até essa data <br> *dd-mm-YYYY*|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


## Listar contas

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/financial/list-invoice
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
  "data_start": "15-05-2018",
  "data_end": "15-05-2019",
  "tipo_transacao": "D",
  "unidade_id": 0
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "detalhes": [
                {
                    "invoice_id": 600056,
                    "tipo_conta": 2,
                    "conta_id": 896944,
                    "valor": 22590,
                    "descricao": null,
                    "data": "18-05-2018"
                }
            ],
            "pagamentos": [
                {
                    "pagamento_id": 600113,
                    "descricao": null,
                    "valor": 22590,
                    "data": "20-04-2018",
                    "forma_pagamento": 1,
                    "tipo_conta": 2,
                    "conta_id": 896944,
                    "parcelas": null
                }
            ]
        }
    ]
}
```

`GET /financial/list-invoice`

Lista informações de contas no sistema.

<h3 id="addPet-parameters">forma_pagamento</h3>

|forma_id|Descrição
|---|---|
|1|Dinheiro|
|2|Cheque|
|3|Transferência|
|4|Boleto|
|5|DOC|
|6|TED|
|7|Transferência Bancária|
|8|Cartão de crédito|
|9|Cartão de débito|

<h3 id="addPet-parameters">tipo_conta</h3>

|tipo_id|Descrição
|---|---|
|1|Conta Corrente|
|2|Fornecedor|
|3|Paciente|
|4|Funcionário|
|5|Profissional|
|6|Convênios|
|7|Caixa|
|8|Profissional externo|

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|data_start|date|Data de início do filtro|
|data_end|date|Data de fim do filtro|
|tipo_transacao|numeric|C = Contas a receber <br> D = Contas a pagar|
|unidade_id <br> *(opcional)*|numeric|ID da unidade|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


<h1 id="procedures">Procedimentos</h1>

## Listar procedimentos

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/procedures/list
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
    "unidade_id": 0,
    "paciente_id": 15,
    "tipo_procedimento": 2,
    "especialidade_id": 5,
    "profissional_id": 35
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "procedimento_id": 1,
            "nome": "Consulta",
            "valor": 75000
        }
    ]
}
```

`GET /procedures/list`

Lista todos procedimentos e seus valores, os valores são determinados de acordo com o valor dos parâmetros enviados na solicitação. <br>
**Os valores são tratados em centavos.**

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**<a href="#tipos-de-procedimentos">tipo_procedimento</a>**|numeric|Tipo de procedimento|
|**<a href="#procedures">procedimento_id</a>** <br> *(Caso não possua **tipo_procedimento**)*|numeric|Tipo de procedimento|
|**<a href="#listar-unidades">unidade_id</a>** <br> *(opcional)*|numeric|Identificação da unidade|
|**<a href="#patient">paciente_id</a>** <br> *(opcional)*|numeric|Identificação do paciente|
|**<a href="#specialties">especialidade_id</a>** <br> *(opcional)*|numeric|Identificação da especialidade|
|**<a href="#professional">profissional_id</a>** <br> *(opcional)*|numeric|Identificação do profissional|
|**nome_procedimento** <br> *(opcional)*|string|Nome do procedimento para filtro de busca|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


## Tipos de procedimentos

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/procedures/types
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "id": 1,
            "tipo": "Cirurgia"
        },
        {
            "id": 2,
            "tipo": "Consulta"
        },
        {
            "id": 3,
            "tipo": "Exame"
        },
        {
            "id": 4,
            "tipo": "Procedimento"
        },
        {
            "id": 9,
            "tipo": "Retorno"
        }
    ]
}
```

`GET /procedures/types`

Busca todos os tipos de procedimento. Essa identificação é utilizada em outros métodos como **(/procedures/list)**

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


<h1 id="insurance">Convênios</h1>

## Listar convênios

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/insurance/list
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "convenio_id": 16,
            "nome": "BRADESCO",
            "registro_ans": "1111",
            "planos": []
        },
        {
            "convenio_id": 2,
            "nome": "CAPERJ",
            "registro_ans": "1232323",
            "planos": [
                {
                    "plano_id": 2,
                    "plano": "Alfa"
                },
                {
                    "plano_id": 7,
                    "plano": "Beta"
                },
                {
                    "plano_id": 8,
                    "plano": "Delta"
                }
            ]
        }
    ]
}
```

`GET /insurance/list`

Busca todos convênios aceitos e seus respectivos planos.


<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


<h1 id="pabx">PABX</h1>

## Novo evento

> Exemplo Request
```http
POST http://clinic5.feegow.com.br/components/public/pabx/new-event
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
    "operation": "R",
    "datetime": "2018-09-25 15:00:35",
    "dest": "3002",
    "channel": "locaweb",
    "caller_id": "5521997622208"
}

```

> Exemplo Resposta
```json
{
    "success": true
}
```

Registra um novo evento.

`POST /pabx/new-event`

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**operation**|string| R = ring <br> A = answer <br> C = cancel|
|**dest**|numeric| Número do ramal|
|**channel**|string| Canal|
|**caller_id**|string| Número do telefone|
|**datetime**|string| Data e hora do evento <br> *(Y-m-d H:i:s)*|


<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


<h1 id="appoints">Agendamentos</h1>

## Tipos de status

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/appoints/status
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```



> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "id": 1,
            "status": "Marcado - não confirmado"
        },
        {
            "id": 2,
            "status": "Em atendimento"
        },
        {
            "id": 3,
            "status": "Atendido"
        },
        {
            "id": 4,
            "status": "Aguardando | Atendimento"
        },
        {
            "id": 5,
            "status": "Chamando | atendimento"
        },
        {
            "id": 6,
            "status": "Não compareceu"
        },
        {
            "id": 7,
            "status": "Marcado - confirmado"
        },
        {
            "id": 11,
            "status": "Desmarcado pelo paciente"
        },
        {
            "id": 15,
            "status": "Remarcado"
        },
        {
            "id": 101,
            "status": "Aguardando | Triagem"
        },
        {
            "id": 103,
            "status": "Em atendimento | Triagem"
        },
        {
            "id": 105,
            "status": "Chamando | Triagem"
        }
    ]
}
```

`GET /appoints/status`

Lista todos os tipos de status para o agendamento.

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


## Lista motivos

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/appoints/motives
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```



> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "id": 1,
            "motivo": "Solicitado pelo paciente"
        },
        {
            "id": 2,
            "motivo": "Solicitado pelo profissional"
        }
        
    ]
}
```

`GET /appoints/motives`

Lista todos os motivos para reagendamento ou cancelamento.

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|

## Listar canais

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/appoints/list-channel
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "id": 1,
            "canal": "Agendamento Online"
        },
        {
            "id": 2,
            "canal": "Clínica"
        }
    ]
}

```

`GET /appoints/list-channel`

Lista todos canais de agendamento disponíveis.


<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|

## Listar agendamentos

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/appoints/search
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```


> Parâmetros
```json
{
    "profissional_id": 1,
    "paciente_id": 100003,
    "data_start": "05-08-2018",
    "data_end": "08-08-2018"
}

```


> Exemplo Resposta
```json
{
    "success": true,
    "content": [
        {
            "agendamento_id": 30,
            "data": "07-08-2018",
            "horario": "09:00:00",
            "paciente_id": 100003,
            "procedimento_id": 3,
            "status_id": 1,
            "local_id": 0,
            "profissional_id": 1
        },
        {
            "agendamento_id": 35,
            "data": "06-08-2018",
            "horario": "08:00:00",
            "paciente_id": 100003,
            "procedimento_id": 3,
            "status_id": 1,
            "local_id": 0,
            "profissional_id": 1
        }
    ]
}
```

`GET /appoints/search`

Lista agendamentos por filtros.

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**agendamento_id**|numeric|ID do agendamento|
|**data_start** <br> *(opcional com agendamento_id)*|date|Data inicio do filtro. <br> *DD-MM-YYYY*|
|**data_end** <br> *(opcional com agendamento_id)*|date|Data final do filtro. <br> *DD-MM-YYYY*|
|**<a href="#professional">profissional_id</a>** <br> *(opcional)*|numeric|Identificação do profissional|
|**<a href="#patient">paciente_id</a>** <br> *(opcional)*|numeric|Identificação do paciente|
|**<a href="#company">unidade_id</a>** <br> *(opcional)*|numeric|Identificação da unidade|
|**<a href="#company">local_id</a>** <br> *(opcional)*|numeric|Identificação do Local|
|**<a href="#specialties">especialidade_id</a>** <br> *(opcional)*|numeric|Identificação da especialidade|
|**<a href="#company">canal_id</a>** <br> *(opcional)*|numeric|Identificação do canal|
|**<a href="#procedures">procedimento_id</a>** <br> *(opcional)*|numeric|Identificação do procedimento|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|

## Disponibilidade de horários

> Exemplo Request
```http
GET http://clinic5.feegow.com.br/components/public/api/appoints/available-schedule
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
    "tipo": "P",
    "procedimento_id": 5,
    "unidade_id": 0,
    "data_start": "08-08-2018",
    "data_end": "10-08-2018"
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": {
        "profissional_id": {
            "1": {
                "local_id": [
                    {
                        "2018-08-10": [
                            "08:00:00",
                            "08:30:00",
                            "09:00:00",
                            "09:30:00",
                            "10:00:00",
                            "10:30:00",
                            "11:00:00",
                            "11:30:00",
                            "12:00:00"
                        ],
                        "2018-08-17": [
                            "08:00:00",
                            "08:30:00",
                            "09:00:00",
                            "09:30:00",
                            "10:00:00",
                            "10:30:00",
                            "11:00:00",
                            "11:30:00",
                            "12:00:00"
                        ],
                        "2018-08-24": [
                            "08:00:00",
                            "08:30:00",
                            "09:00:00",
                            "09:30:00",
                            "10:00:00",
                            "10:30:00",
                            "11:00:00",
                            "11:30:00",
                            "12:00:00"
                        ],
                        "2018-08-11": [
                            "09:00:00",
                            "09:30:00",
                            "10:00:00",
                            "10:30:00",
                            "11:00:00",
                            "11:30:00"
                        ],
                        "2018-08-18": [
                            "09:00:00",
                            "09:30:00",
                            "10:00:00",
                            "10:30:00",
                            "11:00:00",
                            "11:30:00"
                        ],
                        "2018-08-25": [
                            "09:00:00",
                            "09:30:00",
                            "10:00:00",
                            "10:30:00",
                            "11:00:00",
                            "11:30:00"
                        ]
                    }
                ]
            },
            "39": {
                "local_id": {
                    "0": {
                        "2018-08-17": [
                            "21:00:00",
                            "21:30:00",
                            "22:00:00"
                        ],
                        "2018-08-10": [
                            "15:00:00",
                            "15:30:00",
                            "16:00:00",
                            "16:30:00",
                            "17:00:00",
                            "17:30:00",
                            "18:00:00"
                        ],
                        "2018-08-24": [
                            "15:00:00",
                            "15:30:00",
                            "16:00:00",
                            "16:30:00",
                            "17:00:00",
                            "17:30:00",
                            "18:00:00"
                        ]
                    },
                    "15": {
                        "2018-08-11": [
                            "09:00:00",
                            "09:30:00",
                            "10:00:00",
                            "10:30:00",
                            "11:00:00"
                        ],
                        "2018-08-18": [
                            "09:00:00",
                            "09:30:00",
                            "10:00:00",
                            "10:30:00",
                            "11:00:00"
                        ],
                        "2018-08-25": [
                            "09:00:00",
                            "09:30:00",
                            "10:00:00",
                            "10:30:00",
                            "11:00:00"
                        ]
                    }
                }
            }
        }
    }
}
```

`GET /appoints/available-schedule`

Lista todos os horários disponíveis para uma especialidade ou procedimento.

Pode ser filtrado por unidade e profissional, possui um período de data para pesquisa.

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**tipo**|numeric|E = Especialidade <br> P = Procedimento|
|**especialidade_id** <br> *caso tipo = E*|numeric|Identificação da especialidade|
|**procedimento_id** <br> *caso tipo = P*|numeric|Identificação do procedimento|
|**data_start**|date|Listar a partir dessa data <br> *dd-mm-YYYY*|
|**data_end**|date|Limitar consulta até essa data <br> *dd-mm-YYYY*|
|**<a href="#listar-unidades">unidade_id</a>**|numeric|Identificação da unidade|
|**<a href="#professional">profissional_id</a>** <br> *(opcional)*|numeric|Identificação do profissional|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|


## Criar novo agendamento

> Exemplo Request
```http
POST http://clinic5.feegow.com.br/components/public/api/appoints/new-appoint
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
	"local_id": 0,
	"paciente_id": 5,
	"profissional_id": 10,
	"procedimento_id": 5,
	"especialidade_id": 95,
	"data": "08-08-2018",
	"horario": "15:00:00",
	"valor": 550,
	"plano": 1,
	"canal_id": 5
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": {
        "agendamento_id": 43
    }
}
```

`POST /appoints/new-appoint`

Cria um novo agendamento.

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**<a href="#patient">paciente_id</a>**|numeric|Identificação do paciente|
|**data**|date|Data do agendamento <br> *dd-mm-YYYY*|
|**hora**|hour|Horário do agendamento <br> *HH:MM:SS* - *Formato 24hrs*|
|**<a href="#listar-procedimentos">procedimento_id</a>**|numeric|Identificação do procedimento|
|**<a href="#listar-especialidades">especialidade_id</a>**|numeric|Identificação da especialidade|
|**<a href="#listar-locais">local_id</a>**|numeric|Identificação do local|
|**valor**|numeric|Valor do agendamento <br> *centavos*|
|**plano**|numeric|0 = Sem convênio <br> 1 = Com convênio|
|**<a href="#insurance">convenio_id</a>** <br> *(caso plano = 1)*|numeric|Identificação do convênio|
|**<a href="#professional">profissional_id</a>**|numeric|Identificação do profissional|
|**<a href="#listar-canais">canal_id</a>** <br> *(opcional)*|numeric|Identificação do profissional|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|
|409|erro|Paciente não encontrado <br> Horário ocupado|


## Cancelar agendamento

> Exemplo Request
```http
POST http://clinic5.feegow.com.br/components/public/api/appoints/cancel-appoint
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
	"agendamento_id": 41,
	"motivo_id": 1,
	"obs" : "Paciente tinha uma reunião marcada."
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": "Agendamento cancelado"
}
```

`POST /appoints/cancel-appoint`

Cancela um agendamento existente.

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**<a href="#appoints">agendamento_id</a>**|numeric|Identificação do paciente|
|**<a href="#lista-motivos">motivo_id</a>** <br>|numeric|ID Motivo do cancelamento|
|**obs** <br> *(opcional)*|string|Observação do cancelamento|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|
|409|erro|Agendamento não existe|

## Remarcar agendamento

> Exemplo Request
```http
POST http://clinic5.feegow.com.br/components/public/api/appoints/reschedule
Host: api.feegow.com.br
Content-Type: application/json
x-access-token: "SEUTOKEN"

```

> Parâmetros
```json
{
	"agendamento_id": 42,
	"motivo_id": 1,
	"data": "15-08-2018",
	"horario": "19:00:00",
	"obs": "Paciente tinha uma reunião marcada"
}

```

> Exemplo Resposta
```json
{
    "success": true,
    "content": "Agendamento cancelado"
}
```

`POST /appoints/reschedule`

Remarca um agendamento existente.

<h3 id="addPet-parameters">Parâmetros</h3>

|Parâmetro|Tipo|Descrição
|---|---|---|
|**<a href="#appoints">agendamento_id</a>**|numeric|Identificação do paciente|
|**<a href="#lista-motivos">motivo_id</a>**|numeric|ID Motivo reagendamento|
|**obs** <br> *(opcional)*|string|Observação do reagendamento|
|**horario**|hour|Novo horario do agendamento <br> *HH:MM:SS 24hrs*|
|**data**|date|Nova data do agendamento <br> *DD-MM-YYYY*|

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|200|sucesso|Operação bem sucedida|
|409|erro|Agendamento não existe|


<h1 id="errors">Erros</h1>

> Exemplo Error 409
```json
{
    "success": false,
    "content": "String do erro"
}
```
> Exemplo Error 422
```json
{
    "paciente_id": [
        "validation.required"
    ]
}
```

<h3 id="addPet-parameters">Respostas</h3>

|Código|Tipo|Descrição
|---|---|---|
|422|erro|Input inválido|
|409|erro|Conflito interno, específico para cada método|
|401|erro|Chave da API não está definida no header|
|403|erro|Chave da API inativa|

