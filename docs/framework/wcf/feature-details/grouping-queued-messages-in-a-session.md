---
title: Regroupement de messages mis en file d'attente dans une session
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- queues [WCF]. grouping messages
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
ms.openlocfilehash: 260e8b38f110ffc2c2fdc5e2768db8c95fb01860
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564121"
---
# <a name="grouping-queued-messages-in-a-session"></a>Regroupement de messages mis en file d'attente dans une session
Windows Communication Foundation (WCF) fournit une session qui vous permet de regrouper un ensemble de messages connexes à traiter par une application réceptrice unique. Les messages qui font partie d’une session doivent faire partie de la même transaction. Étant donné que tous les messages font partie de la même transaction, si un message n’est pas traité, la session entière est restaurée. Les sessions ont des comportements semblables en ce qui concerne les files d'attente de lettres mortes et les files d'attente de messages incohérents. La propriété Durée de vie (Time to Live ou TTL) définie sur une liaison mise en file d’attente configurée pour les sessions est appliquée à la session dans son ensemble. Si seulement quelques-uns des messages de la session sont envoyés avant l'expiration de la durée de vie, la session entière est placée dans la file d'attente de lettres mortes. De même, lorsque les messages d'une session ne parviennent pas à être envoyés à une application depuis la file d'attente de l'application, la session entière est placée dans la file d'attente de messages incohérents (si disponible).  
  
## <a name="message-grouping-example"></a>Exemple de regroupement de messages  
 Où le regroupement de messages est utile par exemple, lors de l’implémentation d’une application de traitement des commandes en tant qu’un service WCF. Par exemple, un client soumet à cette application une commande qui contient plusieurs éléments. Pour chaque élément, le client passe un appel au service, ce qui provoque l'envoi d'un message séparé. Il est possible que le serveur A reçoive le premier élément et que le serveur B reçoive le deuxième élément. Chaque fois qu'un élément est ajouté, le serveur qui traite cet élément doit rechercher la commande appropriée et lui ajouter l'élément, ce qui est peu efficace. Vous rencontrez également de telles inefficacités avec un seul serveur gérant toutes les demandes, parce que le serveur doit faire le suivi de toutes les commandes en cours de traitement et déterminer à quelle commande le nouvel élément appartient. Le regroupement de toutes les demandes pour une commande unique simplifie grandement l'implémentation d'une telle application. L'application cliente envoie tous les éléments d'une commande unique dans une session, donc lorsque le service traite la commande, il traite la session entière en une fois. \  
  
## <a name="procedures"></a>Procédures  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a>Pour paramétrer un contrat de service pour qu'il utilise des sessions  
  
1.  Définissez un contrat de service qui requiert une session. Faites ceci avec l'attribut <xref:System.ServiceModel.OperationContractAttribute> et en spécifiant :  
  
    ```  
    SessionMode=SessionMode.Required  
    ```  
  
2.  Marquez les opérations du contrat comme étant unidirectionnelles, parce que ces méthodes ne retournent rien. Faites ceci avec l'attribut <xref:System.ServiceModel.OperationContractAttribute> et en spécifiant :  
  
    ```  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3.  Implémentez le contrat de service et spécifiez un `InstanceContextMode` de `PerSession`. Cela instancie le service une seule fois pour chaque session.  
  
    ```  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4.  Chaque opération de service requiert une transaction. Spécifiez ceci avec l'attribut <xref:System.ServiceModel.OperationBehaviorAttribute>. L'opération qui complète la transaction doit également affecter à `TransactionAutoComplete` la valeur `true`.  
  
    ```  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]   
    ```  
  
5.  Configurez un point de terminaison qui utilise la liaison `NetMsmqBinding` fournie par le système.  
  
6.  Créez une file d’attente transactionnelle en utilisant <xref:System.Messaging>. Vous pouvez également créer la file d'attente en utilisant Message Queuing (MSMQ) ou MMC. Dans ce cas, créez une file d'attente transactionnelle.  
  
7.  Créez un hôte de service pour le service en utilisant <xref:System.ServiceModel.ServiceHost>.  
  
8.  Ouvrez l'hôte de service pour rendre le service disponible.  
  
9. Fermez l'hôte de service.  
  
#### <a name="to-set-up-a-client"></a>Pour installer un client  
  
1.  Créez une étendue de transaction pour écrire dans la file d’attente transactionnelle.  
  
2.  Créer le client WCF à l’aide de la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) outil.  
  
3.  Passez la commande.  
  
4.  Fermez le client WCF.  
  
## <a name="example"></a>Exemple  
  
### <a name="description"></a>Description  
 L'exemple suivant fournit le code pour le service `IProcessOrder` et pour un client qui utilise ce service. Il montre la manière dont WCF utilise les sessions en file d’attente pour fournir le comportement de regroupement.  
  
### <a name="code-for-the-service"></a>Code du service  
 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  
  
  
  
### <a name="code-for-the-client"></a>Code du client  
 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  
  
  
  
## <a name="see-also"></a>Voir aussi
- [Sessions et files d’attente](../../../../docs/framework/wcf/samples/sessions-and-queues.md)
- [Vue d’ensemble des files d’attente](../../../../docs/framework/wcf/feature-details/queues-overview.md)
