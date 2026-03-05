Aula 0
Garantindo a segurança das contas
Segurança
Defendendo-se contra ataques
Instituto Nacional de Padrões e Tecnologia (NIST)
Autenticação de dois fatores (2FA) ou autenticação multifatorial (MFA)
Senha de uso único (OTP)
Registro de teclas
Inserção de credenciais
Engenharia Social
Phishing
Ataques do tipo "máquina no meio"
Autenticação única (SSO)
Gerenciadores de senhas
Senhas
Resumindo
Garantindo a segurança das contas
Esta é a introdução à cibersegurança do CS50.
Hoje, vamos nos concentrar na segurança das suas contas.
Vamos começar falando sobre segurança em si.
Segurança
Podemos imaginar a segurança no mundo real como uma chave para uma fechadura física.
No mundo digital, existem inúmeros elementos fundamentais para a segurança.
A autorização é o ato de verificar se você é, de fato, a pessoa que deve ter acesso a esta conta.
Os nomes de usuário são uma forma de comprovar que você deve ter acesso a uma conta.
As senhas são outra forma de comprovar que você deve ter acesso a uma conta.
A ideia é que, teoricamente, somente você deveria ser capaz de fornecer um nome de usuário e uma senha válidos.
Ataques de dicionário são uma das maneiras pelas quais criminosos virtuais tentam adivinhar sua senha. De fato, hackers podem usar um "ataque de força bruta", testando longas listas de senhas possíveis para tentar descobrir a sua. Portanto, é crucial que você se proteja contra esses ataques criando uma senha muito forte.
Ao considerar a segurança, é preciso levar em conta o equilíbrio entre usabilidade e segurança. Um serviço altamente seguro pode se tornar menos utilizável. Portanto, ao avaliar suas opções para manter a segurança, pense no que faz mais sentido para o seu caso de uso.
Defendendo-se contra ataques
Considere quantas combinações numéricas possíveis você teria se sua senha (do celular ou de qualquer outro dispositivo) fosse protegida por apenas quatro dígitos. Existem 10.000 dígitos possíveis. De forma geral, podemos considerar as possibilidades da seguinte maneira:

10 x 10 x 10 x 10
Note que, no pior cenário, os criminosos precisariam tentar 10.000 senhas possíveis.

Poderíamos tentar representar isso em código. O VS Code é um ambiente de desenvolvimento onde podemos escrever e executar código.
Considere a seguinte representação em código do problema acima:

from string import digits

for i in digits:
    for j in digits:
        for k in digits:
            for l in digits:
                print(i, j, k, l)
Observe que este código, escrito em Python, itera por cada combinação possível de números.

Executando crack.pyem uma janela de terminal (onde podemos enviar comandos ao nosso computador), podemos ver que os adversários levam apenas alguns milissegundos para gerar todas as senhas possíveis.
O que aconteceria se pedíssemos uma senha de quatro letras?
Se considerarmos as versões maiúsculas e minúsculas de 26 letras, poderíamos representar isso matematicamente como:

52 x 52 x 52 x 52
Observe que temos mais de 7.000.000 de possibilidades.

Podemos modificar nosso código da seguinte forma:

from string import ascii_letters
 
for i in ascii_letters:
    for j in ascii_letters:
        for k in ascii_letters:
            for l in ascii_letters:
                print(i, j, k, l)
Observe que invocamos a função `__let__` ascii_letters, que inclui as versões maiúsculas e minúsculas de cada letra. De forma semelhante ao nosso programa anterior, este programa itera por todas as combinações possíveis.

Ao executar esse código, descobrimos que ainda não é preciso muito esforço para um hacker descobrir todas as senhas possíveis.
O que aconteceria se pedíssemos uma senha composta por quatro letras, números ou pontuação? Teríamos mais de 78.000.000 de possibilidades!
Podemos modificar nosso código da seguinte forma:

from string import ascii_letters, digits, punctuation

for i in ascii_letters + digits + punctuation:
    for j in ascii_letters + digits + punctuation:
        for k in ascii_letters + digits + punctuation:
            for l in ascii_letters + digits + punctuation:
                print(i, j, k, l)
Ao executar esse código, percebemos que, no pior caso, leva muito mais tempo para descobrir todas as senhas possíveis.
A principal conclusão do que foi dito acima é que, quanto mais dificultarmos o trabalho do adversário em termos de tempo, menor será a probabilidade de ele conseguir quebrar sua senha. No entanto, a dificuldade para o usuário reside no fato de que senhas mais longas e complexas exigem mais tempo para serem digitadas e são mais difíceis de memorizar. Portanto, existe um equilíbrio a ser encontrado entre segurança e usabilidade.
Instituto Nacional de Padrões e Tecnologia (NIST)
O NIST emite recomendações sobre como proteger suas contas de forma mais eficaz.
Você pode usar as recomendações e boas práticas deles em seu próprio trabalho e, talvez, em seu local de trabalho ou empresa. Algumas das recomendações incluem o seguinte em relação a senhas (parafraseadas para maior brevidade):
Os segredos memorizados devem ter pelo menos oito caracteres.
Os verificadores devem permitir todos os caracteres ASCII impressos e símbolos Unicode com até 64 caracteres de comprimento.
Os verificadores devem comparar os segredos potenciais com palavras disponíveis em dicionários, sequências repetidas, listas de senhas vazadas e palavras específicas do contexto.
Os verificadores não devem permitir que requerentes não autenticados acessem dicas de senha.
Os verificadores não devem exigir alterações periódicas de senhas.
Os verificadores devem limitar o número de tentativas de autenticação falhas e bloquear potenciais adversários.
Autenticação de dois fatores (2FA) ou autenticação multifatorial (MFA)
A autenticação multifator possui três componentes.
Conhecimento: Algo que só você sabe.
Posse: Um item ou dispositivo que pertence exclusivamente a um usuário autorizado.
Inerência: Apenas um fator que você poderia obter, como sua impressão digital, rosto ou outros dados biométricos.
Senha de uso único (OTP)
Seria possível obter um chaveiro ou dispositivo especial que fornecesse senhas de uso único.
Frequentemente, os códigos OTP são obtidos de um dispositivo ou aplicativo.
Alguns desses métodos de autenticação de senha única (OTP) são mais seguros do que outros.
Os códigos OTP (senha de uso único) enviados por SMS podem ser facilmente burlados por meio da troca de SIM, técnica na qual um invasor obtém e clona um cartão SIM e passa a ter acesso às suas mensagens de texto.
Mais seguros são os códigos OTP obtidos por meio de um aplicativo em um dispositivo seguro, como um aplicativo de autenticação no seu celular.
Registro de teclas
Nomes de usuário, senhas e códigos OTP são vulneráveis ​​a ataques que permitem que adversários registrem suas teclas digitadas.
O registro de teclas digitadas (keylogging) é realizado através da instalação de software malicioso em um computador.
O ideal é garantir que você só faça login em dispositivos aos quais somente você tem acesso.
Inserção de credenciais
Outro tipo de ataque, o credential stuffing, envolve o uso de uma lista de nomes de usuário e senhas obtida de um site comprometido em outro site.
Se você usa a mesma senha em vários sites, o melhor é alterá-las para senhas exclusivas.
Engenharia Social
Ao contrário de um ataque tecnológico, um ataque de engenharia social envolve o uso de pressão social e confiança para comprometer suas credenciais.
Uma pessoa pode se passar por alguém de confiança para obter suas credenciais ou detalhes sobre sua vida.
Além disso, adversários podem tentar descobrir detalhes sobre sua vida, como o nome do seu animal de estimação, etc.
Phishing
O phishing utiliza engenharia social de forma tecnológica para obter suas credenciais e dados, fingindo ser um site confiável.
Por exemplo, você pode ser direcionado para algo que parece uma página de login do Google, mas que, na verdade, é uma página de um adversário.
Nunca confie cegamente em links fornecidos em e-mails. Considere acessar um navegador da web e digitar diretamente um URL confiável.
Ataques do tipo "máquina no meio"
Dispositivos entre você e a fonte dos dados que você está baixando, como roteadores e switches, podem ser comprometidos por atacantes muito sofisticados.
Autenticação única (SSO)
Como muitos serviços diferentes exigem senhas muito distintas e considerando a recomendação anterior de nunca usar a mesma senha para serviços diferentes, existem muitas maneiras de reforçar sua segurança.
O SSO permite que você use seus logins do Google ou do Facebook para acessar serviços não fornecidos pelo Google ou pelo Facebook.
Portanto, você tem a possibilidade de acessar outros serviços com mais facilidade, menos atrito e maior segurança.
Gerenciadores de senhas
Um gerenciador de senhas é um software que pode gerenciar senhas complexas e salvá-las para você.
Isso permite que você não precise memorizar a senha.
Além disso, muitos gerenciadores de senhas reconhecem sites de phishing.
Diferentemente do salvamento de senhas em navegadores, que já existe há anos, os gerenciadores de senhas são softwares independentes que podem armazenar suas senhas em diversos serviços.
A desvantagem é que, na prática, você estará "colocando todos os seus ovos na mesma cesta". Você precisará se lembrar de uma senha para acessar todas as outras.
Senhas
Uma tecnologia emergente, as chaves de acesso são senhas geradas automaticamente que utilizam criptografia.
As chaves de acesso envolvem uma chave pública e uma chave privada. A chave pública é armazenada por um serviço (como um site), enquanto a chave privada é armazenada pelo seu dispositivo.
As chaves de acesso permitirão que você faça login sem precisar digitar uma senha.
No entanto, para entendermos melhor essa tecnologia, precisaremos aprender mais sobre criptografia.
Resumindo
Nesta lição, você aprendeu sobre o equilíbrio entre segurança e conveniência. Você também aprendeu sobre vários ataques que podem tornar você e outras pessoas vulneráveis. Por fim, você aprendeu algumas maneiras de proteger suas credenciais de login. Especificamente, você aprendeu…

Há um equilíbrio a ser feito entre segurança e conveniência.
Em geral, seus comportamentos e sua consciência são o que o tornam mais seguro contra adversários digitais.
O NIST fornece diretrizes relacionadas à segurança.
A autenticação de dois fatores (2FA), a autenticação multifator (MFA) e as senhas de uso único (OTP) são algumas maneiras de aumentar a sua segurança.
Os ataques mais comuns incluem keylogging, phishing, credential stuffing e engenharia social.
Você pode desfrutar de maior segurança utilizando SSO ou gerenciadores de senhas.
No futuro, as chaves de acesso oferecerão ainda mais segurança.
Até a próxima!