Aula 1
Protegendo os dados
Senhas
Hashing
Salga
Funções de hash unidirecionais
Códigos
Cifras
Chaves
Criptoanálise
Criptografia de chave pública
Troca de chaves
Assinaturas digitais
Senhas
Criptografia em trânsito
Eliminação
Criptografia de disco completo
Computação Quântica
Resumindo
Protegendo os dados
Esta é a Introdução à Segurança Cibernética do CS50.
Na semana passada, como vocês devem se lembrar, nos concentramos nas contas.
Senhas
Nos concentramos em nossa responsabilidade de manter nossos dados seguros.
No entanto, uma terceira parte está sempre envolvida no armazenamento dos nossos dados.
Você pode imaginar como um sistema pode armazenar nomes de usuário e senhas em um arquivo de texto.
Você também pode imaginar como um adversário poderia obter acesso a um arquivo de texto desse tipo.
Será que poderíamos minimizar o risco de armazenar senhas em texto simples?
Hashing
O hashing é um método pelo qual convertemos um texto simples e o exibimos como um valor hash, que é menos legível.
Portanto, uma função hash cria um valor hash. Uma senha é fornecida a uma função hash e, em seguida, o resultado é um valor hash.
Sem acesso à função hash precisa, um adversário não consegue gerar a senha correta.
Geralmente, queremos que a função hash produza algo muito enigmático e sem padrão. Dessa forma, os adversários não conseguem adivinhar o que o algoritmo está fazendo.
Com os nomes de usuário e valores de hash armazenados no servidor, um adversário não consegue acessar facilmente as contas nesse servidor.
Quando um usuário insere sua senha para fazer login, a senha é passada novamente para o algoritmo de hash, que compara o valor de hash criado com o valor de hash armazenado.
Consequentemente, aumentamos o custo, o tempo e os recursos necessários para que um adversário acesse dados protegidos.
Ainda assim, um ataque de dicionário poderia inserir um valor após o outro de um dicionário em uma função hash como forma de quebrá-la.
Além disso, um ataque de força bruta poderia tentar inserir sequencialmente um caractere após o outro para tentar quebrar a senha.
Hipoteticamente, as tabelas arco-íris representam outra ameaça, em que o adversário possui uma tabela com todos os valores hash possíveis em uma tabela hash. Isso, no entanto, exigiria terabytes, senão petabytes, de capacidade de armazenamento para ser implementado.
Por fim, surge um problema quando os usuários utilizam a mesma senha e o valor hash dessas senhas é exatamente o mesmo. Como podemos resolver esse problema?
Salga
O "salting" é um processo pelo qual um valor adicional é "salpicado" na função hash, de forma que o valor do hash seja alterado.
A utilização de um valor de salt praticamente garante que os valores de hash fornecidos pelos usuários, mesmo aqueles que possuem as mesmas senhas, receberão uma senha criptografada diferente.
Portanto, mais uma vez, o custo para os adversários quebrarem essas senhas é bastante elevado.
O NIST recomenda que segredos memorizados sejam criptografados e salgados.
Funções de hash unidirecionais
As funções hash unidirecionais são escritas em código e recebem uma string de comprimento arbitrário, retornando um hash de comprimento fixo.
Utilizando essa função, quem detém o valor hash e a função hash jamais saberá a senha original.
De fato, em alguns sistemas que utilizam uma função hash unidirecional, certas senhas podem ser mapeadas para o mesmo valor hash.
Códigos
Criptografia é o estudo da transmissão segura de dados de uma parte para outra.
Uma forma de proteger dados é através de códigos.
Os códigos convertem as palavras que queremos dizer em uma sequência de palavras menos compreensível.
A codificação envolve pegar um texto simples e convertê-lo em texto codificado.
A decodificação é o processo inverso, convertendo o texto codificado em texto plano.
Cifras
A criptografia envolve pegar um texto simples e decifrá- lo para obter um texto cifrado.
Esse processo de cifragem é chamado de criptografia . O processo de decifrá-los é chamado de descriptografia .
Chaves
As chaves são, na verdade, grandes sequências de caracteres. Essas chaves são usadas na criptografia e na descriptografia.
A criptografia de chave secreta envolve a passagem de uma chave e um texto simples para um algoritmo de criptografia, onde o texto cifrado é produzido como resultado.
Nesse cenário, tanto o remetente quanto o destinatário compartilham um segredo, pois ambos têm acesso ao algoritmo de criptografia e descriptografia.
Criptoanálise
Criptoanálise é o campo de estudo e prática onde os indivíduos estudam como criptografar e descriptografar dados.
Ao participar deste curso, você também pode ter interesse em criptoanálise.
Criptografia de chave pública
Imagine um cenário em que o remetente e o destinatário de dados confidenciais nunca tenham se encontrado pessoalmente. Como estabelecer um segredo compartilhado entre duas partes nessas condições?
A criptografia de chave pública ou a criptografia de chave assimétrica resolvem esse problema.
Primeiro, o remetente usa uma chave pública e um texto simples e os insere em um algoritmo. Isso resulta em um texto cifrado.
Em segundo lugar, o destinatário usa sua chave secreta, inserindo tanto essa chave secreta quanto o texto cifrado no algoritmo. Isso resulta no texto decifrado.
RSA é um padrão de criptografia que descreve esse processo.
Troca de chaves
Um algoritmo alternativo é chamado Diffie-Hellman , cujo objetivo é a troca de chaves.
Utiliza-se um valor previamente acordado ge um valor primo p.
A Parte A e a Parte B têm um valor secreto em comum chamado s.
Tanto a Parte A quanto a Parte B possuem suas próprias chaves privadas.
Assinaturas digitais
Utilizando os elementos básicos de chaves públicas e chaves privadas, você pode usá-los para assinar documentos.
É possível assinar um documento através de um processo de duas etapas.
Primeiro, uma mensagem, o conteúdo de um documento, é passada para uma função hash, resultando em um valor hash.
Em segundo lugar, uma chave privada e um hash são passados ​​para um algoritmo de assinatura digital, o que resulta em uma assinatura digital.
O destinatário consegue verificar sua assinatura digital enviando a mensagem, ou seja, o conteúdo do documento, para a função hash e recebendo um hash. Em seguida, o destinatário envia a chave pública e a assinatura fornecida para o algoritmo de descriptografia, resultando em um valor hash que deve corresponder ao valor hash calculado anteriormente.
Senhas
As chaves de acesso ou WebAuthn são tecnologias cada vez mais disponíveis.
Em breve, nomes de usuário e senhas se tornarão menos frequentes.
As chaves de acesso serão específicas para cada dispositivo. Por exemplo, ao visitar um site no seu celular que solicita a criação de uma conta, seu celular gerará uma chave pública e uma chave privada.
Em seguida, você enviará sua chave pública para o site.
A partir desse momento, para acessar o site usando esse dispositivo ou um serviço que sincroniza suas senhas entre dispositivos, você fornecerá uma chave privada combinada com um valor de desafio. Um algoritmo gerará uma assinatura.
Criptografia em trânsito
A criptografia em trânsito refere-se à segurança dos dados enquanto eles são transferidos entre redes de dados.
Imagine um cenário em que duas partes desejam se comunicar uma com a outra.
Queremos impedir que terceiros interceptem dados durante esse processo.
Serviços de terceiros – como provedores de e-mail – que funcionam como intermediários podem, de fato, estar lendo seus e-mails ou visualizando suas mensagens.
A criptografia de ponta a ponta é uma forma pela qual os usuários podem garantir que nenhum terceiro intermediário consiga ler os dados.
Eliminação
Vamos agora considerar um cenário bastante corriqueiro, como apagar um arquivo.
Após a exclusão de arquivos em um computador, uma "impressão digital" desses arquivos excluídos pode permanecer no seu computador.
Os sistemas operacionais frequentemente excluem arquivos simplesmente por esquecerem onde eles estavam. Portanto, o computador pode sobrescrever arquivos antigos com novos.
No entanto, não há garantia de que o espaço livre no seu disco rígido seja completamente limpo, livre de vestígios de arquivos antigos.
A exclusão segura é um processo pelo qual todos os vestígios de arquivos excluídos são alterados para zeros, uns ou uma sequência aleatória de zeros e uns.
Criptografia de disco completo
A criptografia de disco completo ou criptografia em repouso criptografa totalmente o conteúdo do seu disco rígido.
Se o seu dispositivo for roubado ou se você o vender, ninguém terá acesso aos seus dados criptografados.
No entanto, uma desvantagem é que, se você perder sua senha ou se sua aparência mudar o suficiente, você não terá mais acesso aos seus dados.
Outra desvantagem é que os hackers podem usar esse mesmo tipo de tecnologia por meio de ransomware para criptografar seu disco rígido e mantê-lo como refém.
Computação Quântica
A computação quântica é uma tecnologia emergente que pode fornecer poder computacional exponencial aos adversários.
Essa tecnologia pode ser usada por adversários para reduzir o tempo necessário para adivinhar senhas e quebrar a criptografia.
Esperamos ter acesso a esse poder computacional antes que os agentes mal-intencionados o façam.
Resumindo
Nesta lição, você aprendeu sobre segurança de dados. Você aprendeu…

Como sites e serviços armazenam senhas;
Como os valores de texto podem ser criptografados para garantir o sigilo;
Sobre o papel do salting, funções hash unidirecionais, chaves, criptografia e descriptografia no armazenamento seguro de dados;
Sobre chaves públicas e privadas;
Como as tecnologias utilizam chaves públicas e privadas para manter os dados seguros;
Como proteger seu próprio hardware;
Benefícios e ameaças emergentes da computação quântica.
Até a próxima!