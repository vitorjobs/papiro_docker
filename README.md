# papiro_docker
Estudo do Docker


Docker CLI
Interface de linha de comando (Manipulação de Objetos do Doker)

 Listar Containers - {
      - Docker container ps -a (Listar todos os containers)

 }

 Criar Container - {
       - docker container create --name (nomeDaImagem) (imagemSO)
       
       - docker container create --name teste alpine
       
       - docker container create --name (nomeDaImagem) --it (i= Iniciar de forma interativa para receber comandos do hospedeiro | t= utilizar um terminal) alpine (imagemSO) sh (sh=shell)
       
       
       
       
       Obs: Pesquisar tipos de imagemSO
 } 
 
 Remover Container - {
        - docker rm teste
        
        - docker container rm (nomeDaImagem)
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
 
 - Renomear Container {
        - docker container rename (nome/id) (novoNome)
 }
 
 
 - Executar comandos dentro do container sem precisar acesse-ló de forma direta {
        - docker container exec (nomeContainer) (comando)
   
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
 
 
- Mapear portas dos containers instalando um servidor 
 {
   docker container run -p 8080:80 nginx
   8080: Porta que será exposta pelo container
   80: porta externa (será usada para acessar a porta 8080)
 }

- 25. Mapeamento de volumes {
  - Mapear diretórios para o container (Host -> Container)
  - docker container run -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx
  - obs: pwd = diretório atual

  }

- 26. Rodar um serviço web em background {
  - docker container run -d --name ex-daemon-basic -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx
  - verificar o container rodando em background: docker container ps
  - parar container executando em backdround: docker container stop ex-daemon-basic

}

- 27. Gerenciar o container em background {
  - Iniciar container: docker container start ex-daemon-basic
  - Reinicar container: docker container restart ex-daemon-basic 
  - Para container: docker container stop ex-daemon-basic
  - 

}

- 28. Manipulação de containers em modo daemon {
  - Acessar logs de um container: docker container logs ex-daemon-basic
  - Acessar logs de um container em formato JSOS: docker container inspect ex-daemon-basic
  - Verificar tipo de sistema operacional do container: docker container exec ex-daemon-basic uname -or

}

- 29. Nova sintaxe do Docker Client - Para containers | imagens | Volumes {
  - docker image
  - docker container 
  - docker volumes

}

- Construção de imagens personalizadas do docker {
  - Alterar imagens padrão
  - Alterar versões
  - Instalar pacotes
  -

}

- 33. Comandos básicos no gerenciamento de imagens {
  - docker image ls - listar
  - docker imgae rm: remover imagem
  - docker image pull:  baixar imagem do docker hub
  - docker image push: enviar - enviar imagem para sua conta do docker hub
  - docker image inspect: Inspecionar (detalhar) uma imagem em formato JSON.
  - docker image tag: 
  - docker image build: Pegar arquivo descritor e construir uma imagem

}

- {

}