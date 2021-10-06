## Introdução ao Sistemas de Base de dados: 🧐😁

	Sistemas de Armazemento de Dados
O primeiro sistema de armazemento automático de dados foi o sistema de ficheiros **que usou o mesmo modelo que os sistemas de ficheiros manuais existentes**.

### Problemas:💩
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


### Sistemas de Base de Dados:🎲💪
Existe uma diferença entre a forma como os dados são precebidos pelos programas e a forma que eles são armazenados fisicamente. *Isto acontece para tentar baixar os custo de manutenção.* Se houver alguma alteração na base dados efetuada por algum programa, então é criada uma nova **Base de Dados**, utilizando um software de batabase manager. Outros programas que usem a Base de dados não necessitam de alterações.

**Os programas referem-se a registos lógicos e não a registos físicos**

Os dados passam a estar integrados num único conjunto, sende este gerido por um Sistema de Gestão de Bases de Dados ou database manage ou SGBD.

#### SGBD (database manager):
Aplicações que permite aramazenar e manipular dados, fornecendo as aplicações e ao utlizador os dados que pediram.

	Independência dos dados:
Como as aplicações apenas se comunicam com o *database manage*, podem abstrair-se da forma como os dados são guardados.

	Ao contrario dos sistemas de ficheiros, é possível:
Uma aplicação possa ser modificada, alterando a forma de utilização ou acesso à informação, sem que isso implique alterações nos restantes programas que compartilham a informação.


### Níveis de abstração:👾

	Nível interno:
	- atribuição (alocação) de espaço de armazenamento para dados e índices;🎲
	- descrição dos resgistos para armazenamento (incluindo tamanhos dos itens de dados);📄
	- armazenamento de registo;💿
	- técnicas de compresão e cifragem de dados.🗜
**Internal level -> The physical representation of the database of the database on the computer. This level describes _how_ the data is stored in the database. _(Representação física do banco de dados no computador. Este nível descreve como os dados são armazenados no banco de dados)_**
<p>Por baixo do nível interno, existe o nível físico que pode ser gerido pelo sistema operativo sob a direção do database manager. Contudo, as funções do database manager e do sistema operativo no nível físico não estão claramente estabelecidas e variam de sistema para sistema. Alguns SGBDs tiram partido dos vários métodos de acesso do sistema operativo, enquanto outros usam somente os mais básicos e criam as suas próprias organizações de ficheiros.

	Nível conceptual:
	- todas as entidandes, e seus atributos e relacionamentos;👻
	- as restrições dos dados;🔗
	- informação semântica sobre os dados;
	- informações de segunrança e integridade.🔐
**Conceptual level  -> The community view of the database. This level describes _what_ data is stored in the database and the relartionships among the data. _(Na visão da comunidade de bancos de dados. Este nível descreve quais dados são armazenados no banco de dados e os relacionamente entre os dados.)_**
<p>O nível conceptual dá suporte às visões externas, na medida em que quaisquer dados disponíveis para qualquer utlizador devem estar presentes no nível conceptual, ou set deriváveis a partir deste. No entanto, este nível não deve conter pormenores dependentes do armazenamento. Por exemplo, a descrição de uma entidade deve conter apenas os tipos de dados dos atributos (por exemplo, integer, real,ou char), mas não quaiquer considerações de armazenamento, como o número de bytes ocupados.

	Nível de visualização ("views" ou nível externo):
	- Define um número de visões simplificadas do domínio específico.
	- Descreve apenas parte de bancos de dados. 
	- Este nível é usado pelos usuários.
**External level -> The user´s view of the database. This level describe that part of the database that is relevant to each user. _(A visão que os usuários tem do banco de dados. Este nível descreve a parte do banco de dados que é relevante para cada usuário.)_**

### Independência de dados

	Independência física de dados:
	- Alteração das estruturas de armazenamento (ficheiros);📂
	- Criação de índices para otimizar o acesso aos dados;📄
Devido a questão de otimização do desempenho ou de segurança, é possível alterar aspetos relativos à implementação físicada base de dados, sem que se altere o seu esquema conceptual, isto é, manter os dados e as associações entre eles inalterado.

	Independência lógica de dados:
Durante o período de vida da base de dados pode ser necessário alterar o modelo conceptual, por exemplo, adicionar atributos a entidades já existenets ou criando entidades. Muitas alterações podem ser feitas sem afetar vistas ("_views_") já existentes.
