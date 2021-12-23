# papiro_docker
Estudo do Docker


Docker CLI
Interface de linha de comando (Manipulação de Objetos do Doker)


 Criar Container - {
       docker container create --name (nomeDaImagem) (imagemSO)
       docker container create --name teste alpine
       docker container create --name (nomeDaImagem) --it (i= Iniciar de forma interativa para receber comandos do hospedeiro | t= utilizar um terminal) alpine (imagemSO) sh (sh=shell)
       
       
       
       
       Obs: Pesquisar tipos de imagemSO
 } 
 
 Remover Container - {
        docker rm teste
        docker container rm (nomeDaImagem)
 }
 
 
 Ciclo de Vida - {
        - Inicializaçao: docker container
        - Status {
           UP: Ativo
           Exited: Parado       
          }
 }
     
 Inicializar Container {
        
        - docker container start (nomeDaImagem)               
        - docker container start teste2
        - docker container ls {
           * Visualiza as informações dos containers    
          } 
          
        - docker container start -ia teste2 {
            * Conexão com o container teste2 e acessa o terminal
          }
        - docker container run -it --name teste alpine sh {
            * Cria, Iniciar e Conecta ao Container
          }
 }
 
 Conexão com Container {
        - docker container attach (nome/identificacao)
        - docker container attach teste2
 }      
 
 Renomear Container {
        docker container rename (nome/id) (novoNome)
 }
 
 
 - Executar comandos dentro do container sem precisar acesse-ló de forma direta {
   docker container exec (nomeContainer) (comando)
   
 }
 
 
 - Copiar arquivos do Hospedeiro para o container {
          - Acessar Container
          - docker container cp (nomeDiretorioArquivo) (nomeContainer):/(local)
          - docker container cp testandoContainer teste01:/(raiz do SO)
  }
 
  - Copiar arquivos do container para o Hospedeiro {
   
          - docker container cp (nomeContainer):/(nomeDiretorioArquivoDoContainer) ~/(nomeDiretorioArquivoDoHospedeiro)
          - docker container cp teste01:/testandoContainer ~/

  }
 
 - Inspecionar Elemento do container | Retorno informações do container {
          - docker container inspect (nome)
          - docker container inspect teste01
  }
 
 
