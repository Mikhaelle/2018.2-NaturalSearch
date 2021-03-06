# Dados Relativos A Proponentes Api

All URIs are relative to *http://68.183.107.229:8000* or *0.0.0.0:8000*

Método | HTTP request | Descrição
------------- | ------------- | -------------
[**proponente_detail**](https://github.com/fga-eps-mds/2018.2-NaturalSearch/blob/gh-pages/docs/Documenta%C3%A7%C3%A3o%20API/DadosRelativosAProponentesApi.md#proponente_detail) | **GET** /proponente/{proponente_id} | Busca proponentes dado um id fornecido


# **proponente_detail**
> Proponente proponente_detail(proponente_id, format=format)

Busca proponentes dado um id fornecido

### Exemplo
```python
from __future__ import print_function
import time
import swagger_client
from swagger_client.rest import ApiException
from pprint import pprint

# create an instance of the API class
api_instance = swagger_client.ProponentesDadosRelativosAProponentesApi()
proponente_id = 'proponente_id_example' # str | id do proponente
format = 'format_example' # str | Formato de retorno Json or curl
try:
    # Busca proponentes dado um id fornecido
    api_response = api_instance.proponente_detail(proponente_id, format=format)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProponentesDadosRelativosAProponentesApi->proponente_detail: %s\n" % e)
```

### Parâmetros

Nome | Tipo | Descrição  | Notas
------------- | ------------- | ------------- | -------------
 **proponente_id** | **str**| id do proponente | 
 **format** | **str**| Formato de retorno | Json ou curl 

### Return type

[**Classe Proponente**](Proponente.md)

### Autorização

Não é necessária autorização para executar consultas ao banco da API, entretanto para adicionar, deletar e modificar dados é preciso efetuar login com poderes de administrador.

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#)
