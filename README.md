## Introdução ao Sistemas de Base de dados:

	Sistemas de Armazemento de Dados
O primeiro sistema de armazemento automático de dados foi o sistema de ficheiros **que usou o mesmo modelo que os sistemas de ficheiros manuais existentes**.

### Problemas:
	Alto nível de redundância:
Os mesmos dados podem ser guardados simultaneamente em múltiplo locais.
A aplição não tem conhecimento que os dados estão guardados noutro local.

	Inconsistência da Informação:
As diferentes versão não estão igualmente atulizadas.

	Inflexibilidade:
O pedido de dados de diferentes locais pode não acontecer em tempo util.
Mesmo que os dados existam pode não ser possivel construir a informação.

	Acesso concorrente:
*Diversas aplicações podem partilha o acesso (leitura/escrita) aos ficheiros necessários para a sua execução*
Caso as aplicações não contenham mecanismos de sicronização entre elas, pode ser disponibilizada *informação errada*.

	Isolamento e integridade dos dados:
Os dados encontram-se em diferentes ficheiros, cada um com a estrutura e a organização que interessa à aplicação que o crioui.
A eliminação ou alteração de dados por uma aplicação pode conduzir a perda da infromação.

	Elevados custos de manutenção:
Uma simples alteração nesse ficheiro *pode propagar a necessidade de alteração de todas as aplicações* que acedem ou registam informação nesse ficheiro.


### Sistemas de Base de Dados:
Existe uma diferença entre a forma como os dados são precebidos pelos programas e a forma que eles são armazenados fisicamente. *Isto acontece para tentar baixar os custo de manutenção.* Se houver alguma alteração na base dados efetuada por algum programa, então é criada uma nova **Base de Dados**, utilizando um software de batabase manage. Outros programas que usem a Base de dados não necessitam de alterações.

**Os programas referem-se a registos lógicos e não a registos físicos**

Os dados passam a estar integrados num único conjunto, sende este gerido por um Sistema de Gestão de Bases de Dados ou database manage ou SGBD.

#### SGBD:
Aplicações que permite aramazenar e manipular dados, fornecendo as aplicações e ao utlizador os dados que pediram.

	Independência dos dados:
Como as aplicações apenas se comunicam com o *database manage*, podem abstrair-se da forma como os dados são guardados.

	Ao contrario dos sistemas de ficheiros, é possível:
Uma aplicação possa ser modificada, alterando a forma de utilização ou acesso à informação, sem que isso implique alterações nos restantes programas que compartilham a informação.


### Níveis de abstração:
	Nível interno:
-> Descrição do armazenamento físico da informação numa base de dados.
<p>-> Desfinição das estruturas físicas que permitam obter um nível de desempanho, segunrança e consistência satisfatório.
<p>-> Defenição das políticas de armazenamento de informação, de acordo com o número, exigência e necessidades de casa cliente específico.

**Internal level -> The physical representation of the database of the database on the computer. This level describes _how_ the data is stored in the database**
