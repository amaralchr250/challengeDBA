# challengeDBA

Desafio 1 - Encontrar na máquina virtual um script que retorna data no formato ANO.MES.DIA

alterar o script para gerar um arquivo cujo prefixo é configurado numa variável e o nome do arquivo é obtido de um argumento do script

Exemplo:

````
$ script_data.sh coleta_indicadores
$ Gerado arquivo 2021.01.01_coleta_indicadores.txt
````

R:

Desafio 2 - Criar um script que retorna o máximo de dados possível do sistema operacional ou documentar um guia com os comandos necessários

1. Quantidade de processadores
2. Memória livre
3. Tamanho e diretório dos volumes maiores
4. Qual interface de rede transmitiu mais bytes e quantos foram
5. Gerar uma chave SSH

R: 

````
#!/bin/bash

echo "Check-List"
echo "Name: $(hostname)"
echo "O.S: $(uname -a)"
echo "Threads: $(nproc)"
echo "Free memory ram: $(free -h | awk '/^Mem/{print $4}')"

echo -e "Ranking de volume maior com volume"
df -h | sort -rh | head -n 5


echo -e "\nNetwork transfer"
interface=$(ifconfig | awk '/^[a-zA-Z]/{interface=$1; next} /bytes/{print interface, $2, $6}')
echo "$interface"

echo -e "\n New SSH KEY"

ssh-keygen -t rsa -b 2048 -f ~/.ssh/id_rsa -N ""
````

Os itens abaixo representam alguns emails que você recebeu de algumas de nossas empresas clientes solicitando ajuda, e você precisa respondê-los com algum encaminhamento. Segue conteúdo dos emails recebidos:

Desafio 3 - Olá, não estou conseguindo conectar no servidor SRVXYX01, sempre que uso o comando: psql -h 10.1.1.1 -u postgres -p 5430 ele me retorna: psql: invalid option -- 'u'. Podem me ajudar? o que pode ser?

R:

A declaração com -u minusculo não existe na documentação do postgres e sim "-U" maisuculo para realizar a conexão:

````
 psql -h 10.1.1.1 -U postgres -p 5430 -d nome_do_banco
````


Desafio 4 - Recebo este erro ao tentar conectar no servidor: psql: error: could not connect to server: No such file or directory Is the server running locally and accepting connections on Unix domain socket "/var/run/postgresql/.s.PGSQL.5432"?

R:

Desafio 5 - Oi, meu banco tá lento desde domingo após uma migração de dados e um sistema para o nosso banco de dados. O que pode ser?

R:

# Na máquina virtual existe um script coletor.sh que vai retornar algumas informações sobre um banco de dados, ao executá-lo você encontrará o próximo problema.

Pode se usar comando "find" para encontrar se caso tiver alguma dificuldade de encontrar

Comand find:

````
find / -type f -name "coletor.sh"
````

Directory: 

````
cd /usr/local/bin/
````

Link: https://drive.google.com/file/d/141GA9FvHORSnyF2cVTbD_z6nv8kjVmfo/view?usp=sharing

Desafio 6 - Quais problemas você encontrou?

R:

Desafio 7 - Como você resolveu estes problemas?

R:

Desafio 8 - Na sua opinião, haveria outras formas de resolvê-los?

R:

Desafio 9 - O passo anterior gerou um relatório. Na sua opinião quais problemas este banco de dados enfrentará quando for colocado em produção?

R:

# No dia a dia de trabalho, alguns problemas podem necessitar de algum apoio de um segundo nível. Este desafio pode conter problemas com esta característica.

Desafio 10 - Caso você não tenha conseguido resolver algum problema, como você escalaria isso para um segundo nível? Quais abordagens você utilizaria para repassar o contexto para o segundo nível?

R:

Desafio 11 - Por fim, mas não menos importante, tenha você resolvido todos os desafios ou não, deixe suas considerações sobre o desafio e suas principais dificuldades

R:
