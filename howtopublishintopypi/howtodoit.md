## Para publicar seu package dentro do Pypi.org basta seguir as seguintes instruções!

### 1a Etapa

Instale o setuptools

```
pip install setuptools
```

### 2a Etapa 

Preparar os arquivos de acordo com a árvore de arquivos abaixo:
![Files Tree](https://github.com/FortiHub/dnacrypt/blob/main/howtopublishintopypi/screensave.png))

* Siga o modelo de cada arquivo e sua repectiva localização dentro da árvore!


### 3a Etapa

Agora vamos gerar uma distribuição raiz, ou, tecnicamente, source distribution, também chamada de sdist, usando nosso arquivo setup.py.
Para isso use o comando:

```
python setup.py sdist
```







