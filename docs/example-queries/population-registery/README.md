
# Rahvastikuregister (RR) services 
This documentation outlines the services available under the Rahvastikuregister (RR) API for querying personal data related to elections, usage history, residence, and voting rights. These services can be triggered via the Bürokratt Chatbot or standalone API calls.

### Trigger the service via Bürokratt Chatbot
```
#to be added
```
### General parameters
NB! Required DSL parameters for all services
```
|Parameter |Input                     |Type   |Description                                |
|----------|--------------------------|-------|-------------------------------------------|
|chatId:   |incoming.params.chatId    |String |Unique identifier for the chat session     |
|authorId: |incoming.params.authorId  |String |Identifier for the user making the request |
|id_code:  |incoming.params.input     |String |ID code of the person being queried        |

```

### Endpoints
```
population-register/election-information
population-register/findUsage
population-register/residence-information
population-register/right-to-vote
```

# * election-information
Description: Fetches election details for the queried person, including their voting address and district information.
```
curl localhost:8080/population-register/election-information
```
Expected outcome
```
{
    "result": "Valimiste liigi nimetus: KOHALIKU OMAVALITSUSE VOLIKOGUDE\nIsiku valimiste aadress: Tartu linn,  Tartu linn\nKohaliku omavalitsuse nimetus: Tartu linn\nRingkonna number: 1\nRingkonna nimetus: Valimisringkond nr 1 - Tartu linn"
}
```

# * findUsage
Description: Lists the last ten inquiries about the queried person's data, including the time, action performed, and the requester.
```
curl localhost:8080/population-register/findUsage
```
Expected outcome
```
{
    "result": "Kümme viimast andmepäringut:\nAndmete töötlemise aeg: 2025-01-27T11:55:22\n Tegevus: Isiku valimiste info pärimine\nSooritaja: Riigiportaal: 61101010012\n\nAndmete töötlemise aeg: 2025-01-27T11:10:10\n Tegevus: Isiku valimiste info pärimine\nSooritaja: Riigiportaal: 61101010012\n\nAndmete töötlemise aeg: 2025-01-27T11:06:42\n Tegevus: Isiku valimiste info pärimine\nSooritaja: Riigiportaal: 61101010012\n\n
    ..."
}
```

# * residence-information
Description: Retrieves the current registered residence of the queried person.
```
curl localhost:8080/population-register/residence-information
```
Expected outcome
```
{
    "result": "Isiku registreeritud elukoht on Eesti, Harju maakond, Viimsi vald, Kelnase küla, Silla, 74006"
}
```

# * right-to-vote
Description: Verifies whether the queried person has voting rights and provides details about the elections they are eligible for.

```
curl localhost:8080/population-register/right-to-vote
```
Expected outcome
```
{
    "result": "Isikul on hääleõigus KOV_2024_5 valimistel. Kuupäev: 2025-03-01"
}
```