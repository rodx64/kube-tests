# Componentes do Kubernetes e suas funções básicas: 

## Api Server
- Atua como a interface que permite a comunicação entre todos os outros componentes do cluster
- Ponto de entrada para solicitações externas. 
- Por meio dele, você pode consultar e alterar o estado de outros componentes.

## Cloud Controller Manager (Opcional)
- Possui controladores específicos para cada nuvem (Azure, GCP, Aws..)
- Vincula o cluster ao provedor, permitindo separar componentes

## Kube Controller Manager (Obrigatório)
- Responsável por alterar o estado atual do cluster para outro mais adequado;

## Etcd (Banco tipo chave:valor)
- Banco de dados independente que foi adotado pelo Kubernetes para gerenciamento de dados e estados;
- Todos os seus dados necessitam de backup
- Pode ser executado no mesmo node do cluster, ou separadamente

## Kube Proxy
- Implementação de um proxy de rede que roda dentro dos nodes
- Viabiliza a comunicação de rede dentro e fora do cluster

## Node
- Um node é uma instância de servidor que executa outros componentes de nível superior no Kubernetes.


      Componentes dos Nodes:

          - Pods "Cápsulas":
              - Contém um conjunto de containeres dentro de sí. 
                Containeres = (Aplicações Web, DB's, S.O's., etc..)
    
          - Kubelets: 
              Agentes que executam dentro dos Nodes observando as Pods e seus containeres (Local ou Remoto):  
              Atuam como um "fiscal" que garante que nenhum container seja executado incorretamente dentro dos Pods, 
              para isso utilizam as PodSpecs
        
  
## Kube Scheduler
- Observa os Pods criados sem Nodes atribuidos, selecionando o Node que deve ser executado e qual agenda deve ser seguida
  - e.g. Pod A vai para o Node 1, Pod B vai para o Node 3, Pod C...
- Considera os recursos como hardwares, softwares, permissões, cargas , etc. 
  - Evitando sobrecargas, falta de disponibilidade, etc.

## CRI - Container Runtime Interface
-  runtimes de execução de containers (como o Docker e o RKT), que são de fato quem executam os containeres. 
(Não é o kubernetes que executa)



