# singleton-cdi Carlos Amorim

- Como o atributo config é um atributo injetado o seu ciclo de vida é controlado pelo CDI, diferentemente do parâmetro newConfig. 
E ao simplemente atribuir o newConfig a config, perde-se o sentido do Singleton de ter apenas uma única instancia.
- Para testar tal evento, criei uma nova classe chamada RelatorioResource como uma cópia de ConfigResource, apenas alterando o 
@Path("/relatorio"). E ao executar notei que o Singleton deixou de funcionar. O Swagger estava funcionando normalmente a classe 
RelatorioResource, mas ao executar o GET foi criado um novo objeto com os parâmetros iniciais. Assim, não funcionando o Singleton
e retornando um código HTTP 204 que significa que o servidor atendeu à solicitação com êxito mas não há conteúdo adicional a ser enviado no corpo da carga de resposta
