Aula 2
Sistemas de segurança
Wi-fi
HTTP
HTTPS
VPN
SSH
Portos
Malware
Antivírus
Resumindo
Sistemas de segurança
Esta é a Introdução à Segurança Cibernética do CS50.
Esta semana, vamos nos concentrar em redes e sistemas.
Na última vez, apresentamos a criptografia como uma forma de proteger informações.
Wi-fi
É bem provável que você já tenha percebido que existem redes seguras e não seguras.
Redes seguras utilizam criptografia para proteger os dados entre você e outros dispositivos.
O Wi-Fi Protected Access , ou WPA, é uma forma de criptografia utilizada para proteger redes.
HTTP
O Hypertext Transfer Protocol , ou HTTP , é uma forma não criptografada de transferir dados.
Ao utilizar o protocolo HTTP, o usuário fica vulnerável a ataques do tipo "homem no meio" (Man-in-the-Middle), nos quais um adversário pode injetar código HTML adicional nos arquivos que estão sendo baixados. Anúncios podem ser inseridos em todas as páginas da web acessadas via HTTP. Além disso, códigos maliciosos também podem ser inseridos.
De fato, existem outras ameaças também. A interceptação de pacotes é uma forma pela qual um adversário pode examinar os dados que estão sendo transferidos entre as partes. Imagine como um número de cartão de crédito inserido em um pacote não seguro poderia ser detectado e roubado por um adversário.
Cookies são pequenos arquivos que os sites colocam no seu computador. Os sites podem usar cookies para rastrear quem você é, exibir seus e-mails ou manter o controle do seu carrinho de compras. Os cookies tornam você vulnerável ao sequestro de sessão , em que um invasor pode injetar um supercookie para rastreá-lo.
Como alguém poderia se defender de tal ameaça?
HTTPS
HTTPS é um protocolo seguro para HTTP.
O tráfego entre as partes é criptografado.
Isso é conseguido através do TLS por meio de criptografia de chave pública.
Um site possui uma chave pública assinada por terceiros, chamada de certificado do tipo X.509 . Esses sites também possuem uma chave privada.
As autoridades certificadoras , ou ACs, são empresas terceirizadas confiáveis ​​que emitem certificados.
Quando você visita um site, seu navegador baixa o certificado desse site, o processa por meio de um algoritmo e cria um hash.
Em seguida, utiliza a chave pública do site e a assinatura desse certificado fornecidas a um algoritmo para verificar se ele cria o hash exato encontrado anteriormente.
Se essas informações coincidirem, o navegador da web considerará o site seguro.
Matematicamente, o HTTPS nos mantém seguros, mas existem exceções.
O SSL Stripping é um ataque no qual um adversário usa o protocolo HTTP em um site para redirecionar o tráfego para um site malicioso. O adversário pode até mesmo redirecionar o usuário para um domínio protegido por HTTPS que não seja o site pretendido.
Uma forma de mitigar essa ameaça é implementando o HSTS ou HTTP Strict Transport Security , em que o servidor instrui o navegador a direcionar todo o tráfego para uma conexão segura.
VPN
Uma VPN , ou rede privada virtual , estabelece um canal criptografado entre dois pontos.
Dentro de uma VPN, todo o tráfego é criptografado.
No entanto, existem alguns efeitos colaterais.
Como a comunicação entre duas partes resulta no recebimento de um endereço IP da segunda parte, os serviços em toda a web verão que seu endereço IP é o da segunda parte, e não o seu endereço IP original!
De fato, as pessoas frequentemente usam uma VPN para se fazerem passar por pessoas em outro país.
SSH
SSH é um protocolo seguro que permite executar comandos em um servidor remoto.
Se você deseja se comunicar com um computador remoto e executar comandos nele, pode usar um sshcomando SSH. O exemplo a seguir mostra como usar o comando SSH para se conectar a um servidor na Universidade de Stanford. Você ainda precisará das credenciais e permissões apropriadas para se conectar com sucesso.

ssh stanford.edu
Se alguém tiver os direitos de acesso apropriados, poderá executar comandos diretamente em um servidor remoto.
Portos
Os números de porta são usados ​​para direcionar o tráfego da web para serviços específicos em um servidor.
Por exemplo, a porta 80direciona para HTTP, 443para HTTPS e 22para SSH.
Os servidores escutam essas portas em busca de tráfego de entrada.
Assim, os adversários podem realizar varreduras de portas, nas quais todas as portas potenciais são testadas para verificar se estão aceitando tráfego.
O teste de penetração é uma atividade que um profissional pode realizar para verificar vulnerabilidades de segurança relacionadas a portas.
O hacking ético é a prática legal de testar essas vulnerabilidades.
Um firewall é um software que protege diversos serviços, bloqueando o acesso não autorizado, inclusive de serviços comprometidos em um dispositivo.
Os firewalls utilizam endereços IP , números únicos atribuídos a cada computador em uma rede, para impedir que pessoas não autorizadas participem do tráfego.
Os firewalls também podem usar inspeção profunda de pacotes , onde examinam os dados dentro dos pacotes em busca de material que possa ser de interesse para sua empresa. Isso pode ser usado para verificar se você está enviando e-mails para a imprensa ou outras partes que possam ser consideradas adversárias pela sua empresa.
A inspeção profunda de pacotes é utilizada por meio de um proxy , onde um dispositivo intermediário serve como caminho para o tráfego de entrada e saída da rede. É nesse proxy que sua escola ou empresa pode alterar URLs, registrar quais URLs você está tentando acessar e, idealmente, protegê-lo contra comportamentos potencialmente prejudiciais.
Malware
Malware é um software malicioso que danifica um computador ou compromete sua segurança.
Um vírus é um programa malicioso que se instala no seu computador. Uma vez instalado, ele pode fazer praticamente qualquer coisa!
Um worm é um software malicioso que pode se mover de um computador para outro através de falhas de segurança.
Uma botnet é um software malicioso que, uma vez instalado em seu computador, infecta outros computadores e pode ser usado por um adversário para enviar comandos a milhares de computadores infectados.
Computadores infectados por botnets podem ser usados ​​para lançar ataques de negação de serviço (DoS), nos quais uma grande quantidade de requisições é enviada a um servidor com o objetivo de torná-lo lento ou derrubá-lo. Como uma botnet envolve muitos computadores, esse tipo de ataque pode ser chamado de ataque distribuído de negação de serviço (DDoS) proveniente de milhares de endereços IP.
Antivírus
O software antivírus detecta vírus e, idealmente, consegue removê-los.
As atualizações automáticas devem estar ativadas para corrigir falhas de segurança em versões anteriores do software.
Ainda assim, existe a possibilidade de sermos vulneráveis ​​a ataques de dia zero , que exploram vulnerabilidades desconhecidas em softwares antes que a empresa de software tenha a chance de criar uma correção.
Resumindo
Nesta lição, você aprendeu sobre segurança de sistemas. Você aprendeu…

Como as redes são protegidas em redes sem fio;
Como protocolos seguros e não seguros podem ser usados ​​para enviar e receber dados em uma rede;
Como as redes privadas virtuais podem criptografar o tráfego de rede;
Sobre portas e as vulnerabilidades que os adversários usam para explorá-las;
Sobre malware de vários tipos;
Como o software antivírus pode ajudar a impedir a instalação de software malicioso no seu computador.
Até a próxima!