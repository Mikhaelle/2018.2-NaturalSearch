# Documentação da API swagger client.
Essa é a documentação da API do NaturalSearch.  NaturalSearch é um sistema que reúne dados a respeito de propostas de projetos e proponentes culturais a serem incentivados pelo Ministério da Cultura [MINC](http://www.cultura.gov.br/) por meio da [lei Rouanet](http://rouanet.cultura.gov.br/o-que-e/). Nele é possivel realizar uma pesquisa sobre as informações dos projetos e proponentes e visualizar o resultado em forma de grafo e suas conexões.  Você pode encontrar mais sobre o NaturalSearch em [https://fga-eps-mds.github.io/2018.2-NaturalSearch/](https://fga-eps-mds.github.io/2018.2-NaturalSearch/).


- API version: 1.0.0
- Package version: 1.0.0
- Host: *http://68.183.107.229:8000* or *0.0.0.0:8000*

## Requerimentos.

Python 2.7 and 3.4+, Docker, docker-compose.

## Instalação e Uso

1- Crie um fork ou clone o repositório.

```sh
git clone https://github.com/fga-eps-mds/2018.2-NaturalSearch.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com//.git`)

2- Caso queira alterar algo crie uma branch seguindo a política de branchs deste projeto. 

3- Dentro da pasta que contem o Dockerfile execute o comando use (sudo se necessário):
```sh
docker-compose up --build
```
4- Após a execução e instalação de todos os pacotes necessários, se existirem pendências cancele a sessão e execute:

```sh
docker-compose run web bash

```
5- Dentro do container execute:
```sh
root@cf461053cf90:/code# python manage.py makemigrations
```
6- Em seguida:
```sh
root@cf461053cf90:/code# python manage.py migrate

```
7- Crie o um usuário e senha para acessar o db.

```sh
root@cf461053cf90:/code# python manage.py createsuperuser
```

8- Em outra instância do terminal fora do container execute:
```sh
docker-compose up
```

9- O servidor estará ativo e poderá ser acessado na porta: 

0.0.0.0:8000

Para acessar o db da API acesse essas portas e use o login e senha criados anteriormente:

0.0.0.0:8000/projeto

0.0.0.0:8000/proposta

Para acessar a documentação execute esse link:

0.0.0.0:8000/doc

### Setuptools

Instalação via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(ou `sudo python setup.py install` para instalar o pacote para todos os usuários)

Então importe o package:
```python
import swagger_client
```

## Getting Started

Por favor execute o [procedimento de instalação](#installation--usage) :

Example:

```python
from __future__ import print_function
import time
import swagger_client
from swagger_client.rest import ApiException
from pprint import pprint
# create an instance of the API class
api_instance = swagger_client.ProjetosDadosRelativosAProjetosApi()
projeto_id = 'projeto_id_example' # str | id do projeto
format = 'format_example' # str | Formato de retorno (JSON ou curl)

try:
    # Busca projetos e todos seus atributos dado um id
    api_response = api_instance.projeto_list(projeto_id, format=format)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjetosDadosRelativosAProjetosApi->projeto_list: %s\n" % e)

```

## Documentation for API Endpoints

All URIs are relative to *http://68.183.107.229:8000* or *0.0.0.0:8000*

Classe | Métodos | HTTP request | Descrição
------------ | ------------- | ------------- | -------------
*ProjetosDadosRelativosAProjetosApi* | [**projeto_list**](https://github.com/fga-eps-mds/2018.2-NaturalSearch/blob/gh-pages/docs/Documenta%C3%A7%C3%A3o%20API/DadosRelativosAProjetosApi.md#projeto_list) | **GET** /projeto/{projeto_id} | Busca projetos e todos seus atributos dado um id
*ProponentesDadosRelativosAProponentesApi* | [**proponente_detail**](https://github.com/fga-eps-mds/2018.2-NaturalSearch/blob/gh-pages/docs/Documenta%C3%A7%C3%A3o%20API/DadosRelativosAProponentesApi.md#proponente_detail) | **GET** /proponente/{proponente_id} | Busca proponentes dado um id fornecido


<br>


![swaggerAPI](/docs/images/swaggerAPI.png)

[ver imagem em tamanho original](https://fga-eps-mds.github.io/2018.2-NaturalSearch/docs/images/swaggerAPI.png)

<br>


## Documentação para as Models


 - [Projeto](https://github.com/fga-eps-mds/2018.2-NaturalSearch/blob/gh-pages/docs/Documenta%C3%A7%C3%A3o%20API/Projeto.md)
 - [Proponente](https://github.com/fga-eps-mds/2018.2-NaturalSearch/blob/gh-pages/docs/Documenta%C3%A7%C3%A3o%20API/Proponente.md)
 - [Error](https://github.com/fga-eps-mds/2018.2-NaturalSearch/blob/gh-pages/docs/Documenta%C3%A7%C3%A3o%20API/Error.md)


## Autorizações

Todos os endpoints não requerem autorização para consulta entretanto para adicionar, deletar ou modificar dados é necessário o login como administrador.


## Autores

equipe.naturalsearch@gmail.com

