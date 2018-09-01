As primeiras linhas são as "declarações dos parâmetros".

all,run e clean são diretivas padrão do make, porem não obrigatórias.

Depois de "declarado um parâmetro", é necessario um $(PARA_USA-LO)

%.o pega como entrada e usa em todas as rules a string antes do .o
$< O primeiro pré-requisito (geralmente o arquivo de origem)
$@ É o nome do arquivo que está sendo gerado

Todas as bibliotecas são por padrão chamadas de lib"alguma coisa", por isso a lib"db",(libdb) e
na hora de incluir as bibliotecas, é somente utilizado -ldb de -l de lib e db de libdb.

A linha "ar -rcs $(LIB)/libdb.a $(BUILD)/*.o" é utilizada para juntar os .o (objetos) das .h (headers)
onde são compilada as funções e a partir deste é comprenssado tudo num arquivo .a de (archive file), no caso tem
também o .so de (shared object) que por sua vez é melhor.

Bibliotecas de arquivo (.a) são vinculadas estaticamente, ou seja, quando você compila seu programa com a opção -c no gcc. Portanto, se houver alguma alteração na biblioteca, você precisará compilar e criar seu código novamente.

A vantagem do .so (objeto compartilhado) sobre a biblioteca .a é que eles são vinculados durante o tempo de execução, ou seja, após a criação da opção .o do arquivo -o no gcc. Portanto, se houver alguma alteração no arquivo .so, você não precisará recompilar o programa principal. Mas certifique-se de que seu programa principal esteja vinculado ao novo arquivo .so com o comando ln.