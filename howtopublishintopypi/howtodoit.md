## Para publicar seu package dentro do Pypi.org basta seguir as seguintes instruções!

### 1a Etapa

Instale o setuptools

```
pip install setuptools
```

### 2a Etapa 

Preparar os arquivos de acordo com a árvore de arquivos abaixo:
![Files Tree](https://github.com/FortiHub/dnacrypt/blob/main/howtopublishintopypi/screensave.png)

* Siga o modelo de cada arquivo e sua repectiva localização dentro da árvore!


### 3a Etapa

Agora vamos gerar uma distribuição raiz, ou, tecnicamente, source distribution, também chamada de sdist, usando nosso arquivo setup.py.
Para isso use o comando:

```
python setup.py sdist
```

Após esse comando você verá que sua árvore agora ficou assim:
![Files Tree 2](https://github.com/FortiHub/dnacrypt/blob/main/howtopublishintopypi/screensave2.png)

Note que agora temos mais dois diretórios, dist e dnacrypt.egg-info, que contêm um arquivo compactado do projeto e informações para o PyPI, respectivamente.

### 4a Etapa

A maneira recomendada pelo tutorial oficial do Python é através do twine, que pode ser instalado pelo pip com o comando:

```
pip install twine
```

Agora que já temos nosso projeto pronto e empacotado, precisamos colocá-lo no repositório do PyPI. 

* Recomendo inicialmente fazer um UPLOAD para o TestPyPI.org na versão teste. [Clique aqui](https://test.pypi.org/account/register/) para fazer seu registro caso ainda não possua!

Após seu registro faça o UPLOAD da sua biblioteca para o TestPyPi.org usando o comando abaixo:

```
twine upload dist/* --repository-url https://test.pypi.org/legacy/
```

Recomendo fazer um teste prévio de usuabilidade da biblioteca antes de mandar para o repositório oficial do [PyPi.org](https://test.pypi.org/)

### 5a Etapa

Estando tudo certo com sua biblioteca. Faça seu registro no [PyPi.org](https://pypi.org/account/register/) e execute o seguinte comando:

```
twine upload dist/*
```

### OBS

Nota externa!!! (https://www.alura.com.br/artigos/como-publicar-seu-codigo-python-no-pypi?gclid=Cj0KCQjwjIKYBhC6ARIsAGEds-I6nYx5vkxLoAtora3oZkoR2n_OH759VhrV-J61YL9jpy_NJbh0Ph0aAowpEALw_wcB)

Podemos simplificar todo esse processo com um arquivo .pypirc, que deve ser armazenado na pasta HOME de nosso sistema:

[distutils]
index-servers=
    pypi
    testpypi

[pypi]
username: usuario
password: senha

[testpypi]
repository: https://test.pypi.org/legacy/
username: usuario
password: senha

Assim, apenas com o comando twine upload dist/* -r testpypi já daria certo!

Se não tivermos acesso ao pip, podemos usar o comando python setup.py sdist upload -r pypitest

Agora, e para o repositório oficial? O comando é mais simples ainda: twine upload dist/*, e pronto! Nosso projeto já está disponível!

Se não tivermos acesso ao pip, podemos usar o comando python setup.py sdist upload -r pypi

Assim, meus colegas poderão usar as funções de conversão que eu criei apenas instalando o pacote com o pip e importando-as nos seus próprios programas Python!








