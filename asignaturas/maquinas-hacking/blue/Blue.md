# Nmap

Haremos un escaneo a la máquina para ver que puertos tiene abiertos: 

![b7d45b0990d3e8381eb40e6d5f78be05.png](img/b7d45b0990d3e8381eb40e6d5f78be05.png)

Ya hemos visto que puertos tiene abiertos. Ahora vamos a hacer un escaneo de las versiones y detectar vulnerabilidades. Esto lo haremos con `nmap -sV --script vuln "IP"`
Con -**sV** detectamos las versiones de los puertos abiertos y con **--script vuln** le ejecutamos un script de vulnerabilidades de nmap conocidas. 

![d881735a481d5c935408b6e86708bd57.png](img/d881735a481d5c935408b6e86708bd57.png)

Una vez acaba de ejecutarse al final nos da un resumen de los resultados que ha encontrado. Aqui nos dice que ha encontrado una vulnerabilidad relacionada con SMB y nos da su CVE y su ms. 

![019625765eba04138efd587a5ba96657.png](img/019625765eba04138efd587a5ba96657.png)

Iniciamos metaexploit y buscamos la vulnerabilidad encontrada. Con este comando nos dará la ruta del exploit. 

![1f958ee104611e268e6aefa35e9c17f8.png](img/1f958ee104611e268e6aefa35e9c17f8.png)

Seleccionaremos el exploit 
![c00cdfc85a6d5f2446a9c2754bf93231.png](img/c00cdfc85a6d5f2446a9c2754bf93231.png)

Con `show options` podemos ver que opciones nos deja configurar el exploit. 

![f98efc1960e8d2159c63b5b387d0a861.png](img/f98efc1960e8d2159c63b5b387d0a861.png)

Aquí podemos ver los diferentes parámetros que podemos editar para ejecutar el exploit. Nosotros tendremos que configurar **RHOST** (IP del objetivo), **RPOT** (Puerto del objetivo, dejaremos el que tiene por defecto), **LHOST** (IP atacante) y **LPORT** (puerto del atacante, dejaremos el predeterminado). 

Editamos los parametros y vemos que se hayan configurado.
![30408bf5d8fdfa736c215fb945e5991a.png](img/30408bf5d8fdfa736c215fb945e5991a.png)

Y agregamos un payload de shell reverse.
![4c08df8b1acc28d535a5153cf7b4c838.png](img/4c08df8b1acc28d535a5153cf7b4c838.png)

Una vez configurado todo ejecutamos el exploit con `exploit`.

![2bcc4a5cfd40d4fdd1885f178d7f3e73.png](img/2bcc4a5cfd40d4fdd1885f178d7f3e73.png)

Si funciona correctamente nos meterá en la consola del sistema.
![357fb96ce9b8979040842bc64323bdc5.png](img/357fb96ce9b8979040842bc64323bdc5.png)

Nos dicen que dejemos 
![6405bb59614749dad16dd068290572db.png](img/6405bb59614749dad16dd068290572db.png)

Nos piden que investiguemos como convertir un shell en un shell de meterpreter en metaexploir. 

En esta página nos explican como convertir la shell para meterpreter: [Enlace guía](https://docs.metasploit.com/docs/pentesting/metasploit-guide-upgrading-shells-to-meterpreter.html)

Miramos las sessiones.

![a02d4eff343c3e35069f741ceaba518f.png](img/a02d4eff343c3e35069f741ceaba518f.png)

Nos dicen que usemos `use multi/manage/shell_to_meterpreter` donde podremos ver la ruta del exploit (post/multi/manage/shell_to_meterpreter).

![8e1754333b2c8cf7b7b29ea81cc425aa.png](img/8e1754333b2c8cf7b7b29ea81cc425aa.png)

Vemos las opciones que nos deja seleccionar.

![5e2c8ad1377c833422f432f7701ca0a4.png](img/5e2c8ad1377c833422f432f7701ca0a4.png)

Editaremos LHOST (nuestra IP) y SESSION (id de la session que vimos antes), ya que LPORT lo dejaremos el que está por defecto. 

![62e07a377f2609fb8b0a8f64025b28ff.png](img/62e07a377f2609fb8b0a8f64025b28ff.png)

Y ejecutamos el exploit. 

![7cf0c8f73385d8301ca4a4a08c2c715a.png](img/7cf0c8f73385d8301ca4a4a08c2c715a.png)

Nos dice que se ha creado el meterpreter en la session 2 por lo que vamos a comprobarlo. 

![cdb61c9c51607ea403393509b5cc9bc8.png](img/cdb61c9c51607ea403393509b5cc9bc8.png). 

Nos conectaremos a la sessions creada. 
![429e4726c3811ec376dcf3d8af42eb79.png](img/429e4726c3811ec376dcf3d8af42eb79.png)

Una vez conectados dice que ejecutemos el comando `getsystem` y comporbemos que hemos escalado a SYSTEM.
![c48e3b014ce12e0d2190ba1af283910a.png](img/c48e3b014ce12e0d2190ba1af283910a.png)
Nos dicen que ejecutemos una shell y ejecutemos whoami para ver si somos el sistema. 
![95c366bc0bf932b57bb5768c41a1da39.png](img/95c366bc0bf932b57bb5768c41a1da39.png)

Una vez ejecutado dejamos eso en segundo plano y nos dice que listemos los procesos con `ps` y elijamos uno de los del final que esten ejecutandose por nuestro usuario  NT AUTHORITY\SYSTEM. 

![dafc9f8ab1cacd1d8656ff16791d984b.png](img/dafc9f8ab1cacd1d8656ff16791d984b.png)

Nosotros hemos escogido este proceso ` 2664  692   SearchIndexer.exe     x64   0        NT AUTHORITY\SYSTEM
`
![31d500c31b3192086a431f0821d6d02d.png](img/31d500c31b3192086a431f0821d6d02d.png)

![bcf3f49bba92789ffa7bcc07d7934181.png](img/bcf3f49bba92789ffa7bcc07d7934181.png)

![36d5a20590303be23519a4bb9aa1c03f.png](img/36d5a20590303be23519a4bb9aa1c03f.png)


![42dd70cc333735dd6f7b56040b291873.png](img/42dd70cc333735dd6f7b56040b291873.png)

![2f412fa79376d3a08708a573ae5b6530.png](img/2f412fa79376d3a08708a573ae5b6530.png)

![7883652fb2821a4bc7c8b3fb220d1c28.png](img/7883652fb2821a4bc7c8b3fb220d1c28.png)

![f17896d7822e478519704d76cfc04008.png](img/f17896d7822e478519704d76cfc04008.png)


![4c6bb213e3fc60441922e111a1a7a9f8.png](img/4c6bb213e3fc60441922e111a1a7a9f8.png)
![63166f4f009099274a3281e371037ec5.png](img/63166f4f009099274a3281e371037ec5.png)


![e408dec05601a955d3ead174d76bcc34.png](img/e408dec05601a955d3ead174d76bcc34.png)
![4e76901c5a1afc08ae45533b2063d7a4.png](img/4e76901c5a1afc08ae45533b2063d7a4.png)

![79221162a03808ec152532d870a27a7c.png](img/79221162a03808ec152532d870a27a7c.png)
![e10a07190ab60cfa5fcaf0c5ea429645.png](img/e10a07190ab60cfa5fcaf0c5ea429645.png)
![6441ed9c47df7f55e15abdc9eb61e62d.png](img/6441ed9c47df7f55e15abdc9eb61e62d.png)
flag{access_the_machine}
flag{sam_database_elevated_access}
flag{admin_documents_can_be_valuable}