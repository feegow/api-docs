## Listagem de agendamentos para URA

**Endpoint:**
*https://api.feegow.com.br/api/appoints/ura-appoints*

**Headers:**
*x-access-token:* **chave da api**

**Body de resposta:**
```json
{
  "success": true,
  "content": [
    {
      "Nome": "TESTE DA SILVA",
      "Especialidade": "OTORRINOLARINGOLOGIA",
      "Data_Hora": "16/02/2019 10:00:00",
      "ID_Agendamento": "3493660",
      "Telefone1": "21997621209",
      "Telefone2": "21997621209"
    },
    {
      "Nome": "TESTE DA SILVA 2",
      "Especialidade": "GINECOLOGIA",
      "Data_Hora": "16/02/2019 08:00:00",
      "ID_Agendamento": "3497482",
      "Telefone1": "21997621209",
      "Telefone2": null
    }
  ]
}
```


***


## Recebimento de respostas

**Endpoint:**
*https://api.feegow.com.br/api/appoints/update-appoint-status*

**Headers:**
*x-access-token:* **chave da api**

**Body do request:**
```json
{
    "ID_Agendamento": "3487247",
    "Status": "confirmado"
}
```

**Possiveis status:**
“confirmado” = *Confirma o agendamento*
“cancelado” = *Desmarca o agendamento*
“remarcado” = *Aberto para empresa URA (Ex: Transfere a ligação)*
