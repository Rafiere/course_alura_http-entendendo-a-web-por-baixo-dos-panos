HTTP - Entendendo a Web por Baixo dos Panos - Alura - Anotações


Capítulo 01 - O que é HTTP?

	O "HTTP" é um protocolo de comunicação. Um protocolo nada mais é do que um conjunto de regras. Ele estabelece regras de comunicação entre o cliente e o servidor.
	
	O modelo "cliente-servidor" não é o único modelo de comunicação na rede. Esse modelo tenta centralizar o trabalho no servidor, mas isso pode gerar gargalos. Se cada cliente pudesse ajudar o servidor no trabalho, ou seja, assumir um pouco da sua responsabilidade, os dados poderiam ser processados muito mais rapidamente. Essa é a ideia do protocolo P2P, por exemplo. Um aplicativo de Torrent utiliza o protocolo P2P, e não o protocolo HTTP.
	
	
Capítulo 02 - A Web Segura - HTTPS

	Quando trabalhamos com o modelo de "cliente-servidor", o cliente realiza uma requisição para o servidor, e ele pode enviar dados através dessa requisição.
	
	Uma requisição, ao sair do navegador, pode passar por vários roteadores, firewalls e etc, dessa forma, por padrão, o HTTP envia textos puros. Para isso, existe o HTTPS, que possui a camada de SSL/TLS, que é uma camada de segurança que é adicionada ao HTTP.
	

Capítulo 03 - Endereços Sob Seu Domínio

	Um domínio é um nome fácil de ser gravado, porém, internamente, eles são referenciados por endereços IPs. O "DNS", que é o "Domain Name System", é um servidor que, ao inserirmos uma URL, como "http://cursos.alura.com.br", ele recebe essa URL e converte ela para um IP numérico, e devolve esse IP numérico para o navegador, e, dessa forma, o navegador envia uma requisição para esse IP numérico que foi devolvido pelo servidor de DNS.
	
	Quando enviamos uma requisição HTTP, ela envia, por padrão, a requisição para a porta "80" para o servidor. Quando trabalhamos com o HTTPS, a porta padrão é a "443", e não a porta "80".
	
	A requisição "https://www.alura.com.br:443/course/introducao-html-css" possui as seguintes partes:
	
	- Protocolo: "https"
	- Domínio: "www.alura.com.br"
	- Porta: "443"
	- Recurso: "/course/introducao-html-css"


Capítulo 04 - O Cliente Pede e o Servidor Responde

	Os Cookies são formas do navegador guardar algumas informações necessárias, e em todas as requisições que o navegador realizar, as informações armazenadas nesse cookie serão enviadas, como um código de autenticação para provar que o usuário está logado, por exemplo.
	
	O HTTP é stateless, ou seja, ele não guarda informações entre as requisições.
	

Capítulo 05 - Depurando a Requisição HTTP

	O "status code" é o status que o servidor respondeu para uma determinada requisição.
	
	Ao acessarmos o site "www.alura.com.br", será retornada uma página HTML do site Alura, e, com base nessa página HTML, todos os outros recursos, como páginas CSS, vídeos, arquivos JavaScript e etc, serão retornados através de outras requisições que o cliente fará. Cada requisição retornará um arquivo.
	
	Existem os seguintes status codes:
	
	2XX - Successful Responses
	3XX - Redirection Messages
	4XX - Client Error Responses
	5XX - Server Error Responses


Capítulo 06 - Parâmetros da Requisição

	Uma requisição pode receber parâmetros pela URL, por exemplo, na URL "www.youtube.com/search?query_params=Teste", estamos enviando o parâmetro "query_params" com o valor "Teste" para o back-end do YouTube.
	
	O método "GET" serve para recebermos dados. Podemos enviar parâmetros pela URL.
	
	O método "POST" serve para enviarmos dados, esses dados serão enviados no corpo da requisição.
	
	O método "DELETE" serve para removermos um recurso.
	
	O método "PUT" serve para atualizarmos um recurso.


Capítulo 07 - Serviços na Web com REST

	Na internet, os dados entre duas aplicações são retornados principalmente nos formatos XML e JSON.
	
	O "REST" é, basicamente, trabalharmos com a web da forma que ela é especificada, assim, temos um recurso, que é uma URI, as operações, que são os verbos HTTP e a representação das informações, que podem serem fornecidas nos formatos JSON, XML e HTML, por exemplo.
	

Capítulo 08 - HTTP2 - Por uma Web Mais Eficiente

	No HTTP/2, o corpo da mensagem é comprimido através do algoritmo "gzip", enviando uma menor quantidade de dados. O padrão do HTTP/2 é o "gzip", porém, o HTTP/1.1 suporta a compressão em "gzip", porém, isso não é definido por padrão.
	
	No HTTP/2, os cabeçalhos da request e da response também são enviados no formato binário, de forma comprimida, com o objetivo de diminuir o tamanho das requisições.
	
	Por padrão, o HTTP/2 também criptografa as informações por padrão, assim, os dados, além de binários, são comprimidos pelo algoritmo HPack e são encriptados pelo TLS.
	
	No HTTP/2, o servidor é capaz de retornar todos os recursos que serão necessários para exibir uma página, assim, o cliente não precisa requisitar arquivo por arquivo.
	
	No HTTP/1.1, a cada requisição HTTP que é feita, uma conexão TCP deve ser estabelecida. O HTTP/1.1 possui o recurso "Keep-Alive", ou seja, ele mantém a conexão TCP viva enquanto um determinado número de requisições HTTP forem sendo efetuadas. Normalmente, cada cliente possui de 4 a 8 conexões TCP ativas, para que possa realizar requisições HTTP em paralelo.
	
	No HTTP/2, todas as requisições são feitas de forma paralela, assim, não precisamos esperar uma requisição ser finalizada para que outra requisição seja realizada. Esse conceito é chamado de "Multiplexing".
