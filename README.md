# Programação para Banco de Dados  

## **Preparando o Ambiente:**

### Instalação do python:

Download da última versão em https://www.python.org/    
    
Criar um diretório para para a instação (em um pen drive ou na sua própria máquina).    
Nome do diretório: prog_db    
### Em Customize installation:     
Instalar: documentation, pip, tcl/tk e python test suite.    
Desmarque: py launcher e for all users.    
### Advanced Options:     
Desmarque todas as opções e clique em browser para selecionar o local de instalação: selecione    
prog_db e crie uma nova pasta python e instale nesse caminho.    

## **Criando o ambiente virtual:**   
Prática é deixar a instalação do ambiente python isolada e fazer a instalação do ambiente virtual separada.    

### **Parar criar o ambiente na pasta jupyter dentro de prog_db:**    
*python\python.exe -m venv jupyter* (-m = é a forma de chamar o módulo.)    
*C:\Users\nomeUser\prog_db>python\python.exe -m venv jupyter*    

# **Para ativar o ambiente (jupyter):**
*(O que fizer é válido para a instalação mas não para o restante do sistema)*         
Entrar na pasta *jupyter\Scripts\active.bat*    
*C:\Users\nomeUser\prog_db\jupyter\Scripts>activate.bat*    
Para saber se está no ambiente virtual, basta verificar se possuí **(jupyter)**.    
**(jupyter) C:\Users\nomeUser\prog_db\jupyter\Scripts>**    
____________________________________________________________
## **Instalação do jupyter lab:** *pip install jupyterlab*    
(entre tantas instalações, uma delas é o pandas completo)    
*(jupyter) C:\Users\nomeUser\prog_db\jupyter\Scripts>pip install jupyterlab*    

### **Abrir o jupyter lab:** *jupyter-lab.exe*    
*(jupyter) C:\Users\nomeUser\prog_db\jupyter\Scripts>jupyter-lab.exe*    

### **Criar pasta arquivos (em prog_db) no mesmo nível da pasta jupyter e python, dentro do ambiente jupyter.**     
Todos os arquivos de aula manteremos nesse local.    
*(jupyter) C:\Users\nomeUser\prog_db>mkdir arquivos*    
Executar o jupyter lab dentro de arquivos:     
*(jupyter) C:\Users\nomeUser\prog_db\arquivos>jupyter-lab.exe*    
Irá abrir no browser.    
Ou use: *(jupyter) C:\Users\nomeUser\prog_db>python jupyter\Lib\site-packages\jupyterlab*  

## **Conceitos básico da linguagem**
Tudo em python é objeto, todas as variáveis são criadas como objetos, ou seja ele muda os tipos conforme o conteúdo.
### **Tipos básicos mais comuns de objetos da linguagem são:**
str -> tipo textual - sequencias de caracteres.
int, flot, complex -> tipos numéricos inteiro, flutuante e para números complexos.
bool -> boleanos com valor true ou false.
bytes -> tipos binários.
### **Tipos para armazenar mais de um item, são os tipos para sequencias, mapas ou conjuntos de itens:**
list, tuple, range -> Sequências
dict -> dicionário ou mapas
set, frozenset -> conjuntos
### **Variáveis - tudo é referência a um objeto**
As variáveis no python são criadas no momento que atribuímos uma referência à um valor para elas. Não é necessário declará-las no início de nossos programas e não há um comando para isso:
x = 5
x = '5'
x = 5.0
As 3 atribuições podem ser executadas em sequencia e o interpretador irá mudar o tipo da variável, de acordo com a atribuição:
Pode fazer pelo terminal através do *python*: *(jupyter) C:\Users\nomeUser\prog_db>python*
Ou abrir no browser: *prog_db>python jupyter\Lib\site-packages\jupyterlab*

```
>>> x=5
>>> type(x)
<class 'int'>
>>> x='5'
>>> type(x)
<class 'str'>
>>> x=5.0
>>> type(x)
<class 'float'>
>>>
```
É possível fazer a conversão quando não são compatíveis, exemplo:
**y= x + 'teste'** = vai dar erro, pois é um int e uma string.
Pode fazer o x se tranformar em uma string através do **cast**.
```
>>> x=3
>>> y=str(x) + 'teste'
>>> y
'3teste'
>>>
```
### **Inteiros em Python:**
De acordo com o padrão de declaração das variáveis de valor inteiro, você codifica um tipo diferente de valor:
Binários: 0b
Octal: prefixados com 0o
Hexadecimal: prefixados com 0x
Exemplo:
*(jupyter) C:\Users\nomeUser\prog_db>python*
```
>>> x=42
>>> y=0o10
>>> z=y+x
>>> print(z)
50
>>> print(bin(z))
0b110010
>>>
```

### **Decimais**
Números não inteiros representam um problema para a maioria das linguagens:
Exemplo:
```
>>> 0.1+0.1+0.1
0.30000000000000004
>>>
```
#### **IEE 754**
Realizar o import do módulo decimal para encontrar o valor real que está sendo utilizado.
*(jupyter) C:\Users\nomeUser\prog_db>python*
*import decimal*
```
>>> decimal.Decimal(0.1+0.1+0.1)
Decimal('0.3000000000000000444089209850062616169452667236328125')
>>>
```

### **Strings em Python**
A criação de String é feita com o uso de aspas simples ou duplas:
```
>>> x='Olá Mundo!'
>>> print(x)
Olá Mundo!
>>> x="Olá Mundo!"
>>> print(x)
Olá Mundo!
>>>
```
Para criar uma string com mais de uma linha, use aspas triplas:
```
>>> x='''Olá Mundo!
... Como vocês
... Estão Hoje?'''
>>> print(x)
Olá Mundo!
Como vocês
Estão Hoje?
>>>
```
#### **Funções das Strings**
Strings são arrays de caracteres e pode-se acessar qualquer elemento utilizando a sintaxe das listas (list), que inicia
a contagem na posição 0:
```
>>> a='Olá Mundo!'
>>> print(a[2])
á
>>>
```
Imprimir pedaços da strings:
```
>>> for i in a: print (i)
...
O
l
á

M
u
n
d
o
!
>>>
```
Imprimir trechos de strings:
```
>>> a='Olá Mundo!'[0:3]
>>> print(a)
Olá
```
Imprimir a partir do final das strings:
```
>>> a='Olá Mundo!'[-6:]
>>> print(a)
Mundo!
```
### **Os tipos sequenciais: lista ordenada imutável (tuple)**
Tupla usa-se parenteses para abrir e fechar ().
A cada posição, iniciando a partir do zero, está associando um objeto. Depois de criada, ela não muda.
```
>>> a=('ave', 8, 'casa', 290, 8)
>>> type(a)
<class 'tuple'>
```
#### **Percorrendo listas**
Listas usa-se cochetes para abrir e fechar []
```
>>> a=['ave', 8, 'casa', 290, 8]
>>> for i in a: print(str(i)+ ' é um valor do tipo ' + str(type(i)))
...
ave é um valor do tipo <class 'str'>
8 é um valor do tipo <class 'int'>
casa é um valor do tipo <class 'str'>
290 é um valor do tipo <class 'int'>
8 é um valor do tipo <class 'int'>
```
Na lista é possível fazer uma cópia de outra variável sem alterar o valor da "original".
Exemplo: se alterar o b não vai interferir no valor de a.
```
>>> b=a.copy()
>>> b
['ave', 8, 'casa', 290, 8]
>>>
```
*Se apenas atribuir "a" a "b", o b irá apontar para a, sendo assim se alterar o b vai alterar também o a.*

### **Blocos de código em python: indentação**
Não faz uso de marcadores de começo e fim de bloco: isso é feito pelo indentação dos blocos.
Tudo que tiver com a mesma identação representa um bloco de código que deverá ser executado.
O jupyter-lab já faz essa identação do código.

### **Comentários em Python:**
Quando não quiser que um código seja executado basta comentá-lo, inserindo # na frente.




