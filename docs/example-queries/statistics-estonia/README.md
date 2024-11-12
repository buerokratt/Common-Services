# Statistics-Estonia API Documentation GET


### Trigger the service via Bürokratt Chatbot
```
Unemployment Rate:
    Mis on töötuse määr Eestis?
    Mis on töötuse määr aastal 2021 Eestis?

Estimated Subsistence Minimum:
    Arvestuslik elatusmiinimum

Consumer Price Index:
    Mis on tarbija indeks?
    Mis on tarbija indeks 2021?
    Mis on tarbija indeks 2021 jaanuaris?
```


### Trigger the service as a stand-alone
NB! Required DSL parameters for all services
```
chatId: "${incoming.params.chatId}"
authorId: "${incoming.params.authorId}"
```

Endpoints
```
statistics-estonia/consumer-price-index              #Consumer Price Index Query  # input: input
statistics-estonia/estimated-subsistence-minimum     #
statistics-estonia/unemployment-rate
```


## * (service file name)
```
# example curl request
```
Expected outcome
```
{
    "result": "needed information, already formatted - end result"
}
```