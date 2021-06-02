# Apache Drill

- [1. Descrição](#link1)
- [2. Instalação](#link2)
- [3. Plugins](#link3)
- [4. Comandos básicos](#link4)
- [5. Links](#link5)

<a id="link1"></a>
## 1. Descrição

O Apache Drill é um mecanismo de pesquisa (query engine) para rodar consultas Sql em big data.</br>

Apache Drill pode trabalhar com uma grande variedade de dados não relacional como Hadoop, NoSQL databases (MongoDB, HBase) e armazenamento em nuvem como Amazon S3, Azure Blob Storage, etc.

Apache Drill pode se integrar com uma série de armazenamentos de dados, relacionais ou não.

Integração com sistemas de arquivos:

- Sistemas de arquivos tradicionais: Local ou NAS
- Hadoop: HDFS e MAPR-FS (MAPR-File System)
- Nuvem: Amazon S3, Google Cloud Storage, Azure Blob Storage

Integração com NoSQL Databases
- MongoDB
- HBase
- HIVE
- MapR-DB

![Screenshot](/images/d00.jpg)

## DrQL
DrQL (Drill Query Language) é a libguagem de consulta. DrQL é uma linguagem de consulta no estilo SQL.

## Formatos de arquivos
Drill suporta vários tipos de arquivos como CSV, TSV, PSV, JSON e Parquet.

## Clientes
Os seguintes clientes podem se conectar ao Apache Drill

- Interfaces JDBC, ODBC, C++ API, REST usando JSON
- Drill shell
- Drill web console porta 8047 (default)
- Ferramentas BI como Tableau, MicroStrategy, etc.
- Excel

<a id="link2"></a>
## 2. Instalação

O Apache Drill pode ser instalado de duas formas:

- Local</br>
Instalação em um nó (local).

- Distribuido</br>
Instalação em um ambiente distribuído.</br>
Permitindo conectar e realizar consultas no Hive, HBase ou qualquer fonte distribuída.</br>
Para isso é necessário a instalação do ZooKeeper.</br>

## Instalação Local

#java</br>
O Apache Drill precisa do java instalado

![Screenshot](/images/d01.jpg)

#download</br>
```wget https://downloads.apache.org/drill/drill-1.18.0/apache-drill-1.18.0.tar.gz```

#extract</br>
```tar xvzf tar xvzf apache-drill-1.18.0.tar.gz```

#mover para a pasta destino e permissões para o usuário padrão</br>
```sudo mv apache-drill-1.18.0 /usr/local/drill```</br>
```sudo chown -R hduser /usr/local/drill```</br>

![Screenshot](/images/d02.jpg)

## Configuração

#editar bashrc</br>
```nano ~/.bashrc```</br>
```export DRILL_HOME=/usr/local/drill```</br>
```export PATH=$PATH:$DRILL_HOME/bin```</br>
```source ~/.bashrc```</br>

![Screenshot](/images/d03.jpg)

- Start</br>
```drill-embedded```</br>

![Screenshot](/images/d04.jpg)

- Interface Web</br>

![Screenshot](/images/d05.jpg)

![Screenshot](/images/d06.jpg)

![Screenshot](/images/d07.jpg)

![Screenshot](/images/d08.jpg)

<a id="link3"></a>
## 3. Descrição


<a id="link4"></a>
## 4. Plugins

Storage Plugins são softwares que permitem ao Drill conectar aos armzenamentos de dados, como databases (Hive, ,HBase) ou sistemas de arquivos local ou distrinuídos.

- cp</br>
Aponta para arquivos JAR dentro do classpath do Drill</br>
- dfs</br>
Aponta para o sistema de arquivos local, mas pode ser configurado para um sistema distribuído como Hadoop ou S3.</br>
- hbase</br>
Conexão para o HBase.</br>
- hive</br>
Conexão para o Hive.</br>
- mongo</br>
Conexão para o MongoDB.</br>
- kafka</br>
Conexão para o Kafka.</br>
- kudu</br>
Conexão para o Kudu.</br>
- opentsdb</br>
Conexão para o OpenTSDB.</br>

Exemplo: Consultar o arquivo employee.json usando o plugin cp.</br>

```SELECT employee_id, full_name FROM cp.`employee.json` LIMIT 10;```</br>

![Screenshot](/images/d09.jpg)

Exemplo: Consultar o arquivo region.parquet usando o plugin dfs.</br>

```SELECT * FROM dfs.`/usr/local/drill/sample-data/region.parquet`;```

![Screenshot](/images/d10.jpg)


<a id="link5"></a>
## 5. Links

Apache Drill</br>
https://drill.apache.org/</br>

Documentação</br>
http://drill.apache.org/docs/
