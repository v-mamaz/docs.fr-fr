---
title: Étapes du flux de travail DevOps boucle externe pour une application Docker
description: Découvrez les étapes pour la boucle « externe » du flux de travail DevOps
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: b75e9df1c31e8bcebcaa6d56336a6aa499d13e1d
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220937"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Étapes du flux de travail DevOps boucle externe pour une application Docker

Figure 5-1 présente une description de bout en bout des étapes comprenant le flux de travail DevOps boucle externe.

![](./media/image1.png)

Figure 5-1 : Flux de travail DevOps boucle externe pour les applications Docker avec les outils Microsoft

Maintenant, nous allons examiner chacune de ces étapes plus en détail.

## <a name="step-1-inner-loop-development-workflow"></a>Étape 1 : Flux de travail de développement de la boucle interne

Cette étape est expliquée en détail dans le chapitre 4, mais, pour résumer, voici où la boucle externe commence, le moment auquel un développeur transmet le code pour le système de gestion de contrôle de source (comme Git) initiation d’actions de pipeline CI.

## <a name="step-2-source-code-control-integration-and-management-with-azure-devops-services-and-git"></a>Étape 2 : Intégration de contrôle de Code source et la gestion avec Azure DevOps Services et Git

À ce stade, vous devez disposer d’un système de contrôle de version pour collecter une version consolidée de tout le code provenant des différents développeurs de l’équipe.

Même si le contrôle de code source (SCC) et de gestion de code source peuvent sembler seconde-nature à la plupart des développeurs, lors de la création d’applications Docker dans une vie DevOps cycle, il est essentiel de souligner que vous ne devez pas envoyer les images Docker avec l’application directement dans le Registre de Docker global (comme Azure Container Registry ou Docker Hub) à partir de l’ordinateur du développeur. En revanche, les images Docker être libéré et déployée dans les environnements de production doivent être créés uniquement sur le code source en cours d’intégration dans votre build global ou d’un pipeline CI en fonction de votre référentiel de code source (comme Git).

Les images locales générées par les développeurs eux-mêmes doivent être utilisés uniquement par les développeurs lors du test au sein de leurs propres ordinateurs. C’est pourquoi il est essentiel d’avoir votre pipeline DevOps activé à partir du code de contrôle de code source.

Azure DevOps Services et Team Foundation Server prend en charge Git et Team Foundation Version Control. Vous pouvez choisir entre eux et l’utiliser pour une expérience de Microsoft de bout en bout. Toutefois, vous pouvez également gérer votre code dans les dépôts externes (tels que GitHub, les référentiels Git en local ou Subversion) et toujours être en mesure de s’y connecter et obtenir le code comme point de départ pour votre pipeline DevOps CI.

## <a name="step-3-build-ci-integrate-and-test-with-azure-devops-services-and-docker"></a>Étape 3 : Générer, CI, intégrer et tester avec Azure DevOps Services et Docker

CI est devenu une norme pour le test de logiciels modernes et de remise. La solution Docker gère une séparation claire des responsabilités entre les équipes de développement et les opérations. L’immuabilité des images Docker garantit un déploiement reproductible entre ce qui a développé, testé via l’élément de configuration et exécuter en production. Moteur docker déployé sur les ordinateurs portables de développeur et infrastructure de test rend les conteneurs portable entre les environnements.

À ce stade, une fois que vous avez un système de contrôle de version avec le bon code soumis, vous avez besoin une *service de build* pour récupérer le code et exécuter la build global et les tests.

Le flux de travail interne pour cette étape (CI, build, test) est sur la construction d’un pipeline CI consistant à votre référentiel de code (Git, etc.), votre serveur de builds (Services de DevOps Azure), moteur Docker et un Registre Docker.

Vous pouvez utiliser Azure DevOps Services comme base pour la création de vos applications et en définissant votre pipeline CI et pour la publication « artefacts » générés pour un « référentiel d’artefacts, » qui est expliqué dans l’étape suivante.

Lors de l’utilisation de Docker pour le déploiement, les « artefacts finales » à être déployées sont des images Docker avec votre application ou les services intégrés à ceux-ci. Ces images sont transmises ou publiés sur un *Registre Docker* (un référentiel privé, comme ceux que vous pouvez avoir dans Azure Container Registry ou une publique comme registre Docker Hub, qui est couramment utilisé pour les images de base officiels).

Voici le concept de base : Le pipeline de CI sera déclenchée désactivé par une validation à un référentiel de contrôle de code source comme Git. La validation entraîne Azure DevOps Services exécuter une tâche de build dans un conteneur Docker et, en cas de réussite de ce travail, transférer une image Docker au Registre Docker, comme illustré dans la Figure 5-2.

![](./media/image2.png)

Figure 5-2 : Les étapes impliquées dans l’élément de configuration

Voici les étapes de flux de travail de base CI avec Docker et Azure DevOps Services :

1.  Le développeur exécute un push d’une validation à un référentiel de contrôle de code source (Git/Azure DevOps Services, GitHub, etc.).

2.  Si vous utilisez Azure DevOps Services ou Git, CI est intégrée, ce qui signifie qu’il est aussi simple que la sélection d’une case à cocher dans les Services Azure DevOps. Si vous utilisez un contrôle de code source externe (comme GitHub), un *webhook* Avertissez les Services de DevOps Azure de la mise à jour ou de push à Git/GitHub.

3.  Les Services Azure DevOps extrait le référentiel de contrôle de code source, y compris le fichier DockerFile décrivant l’image, ainsi que le code d’application et de test.

4.  Azure DevOps Services crée une image Docker et il les avec un numéro de build.

5.  Les Services Azure DevOps instancie le conteneur Docker dans l’hôte Docker approvisionné et exécute les tests appropriés.

6.  Si les tests réussissent, l’image est tout d’abord un nouveau libellé à un nom significatif afin que vous savez qu’il est « génération privilégiée » (comme « / 1.0.0 » ou n’importe quel autre étiquette) et puis envoyées à votre Registre Docker (Docker Hub, Azure Container Registry, DTR, etc.).

### <a name="implementing-the-ci-pipeline-with-azure-devops-services-and-the-docker-extension-for-azure-devops-services"></a>Mise en œuvre le pipeline CI avec Azure DevOps Services et l’extension Docker pour Azure DevOps Services

Le [extension Docker de Services Azure DevOps](https://aka.ms/vstsdockerextension) ajoute une tâche à votre pipeline CI avec lequel vous pouvez générer des images Docker, envoyer des images de Docker à un Registre Docker authentifié, exécuter des images Docker ou exécuter d’autres opérations offertes par le Docker INTERFACE CLI. Il ajoute également une tâche de Docker Compose que vous pouvez utiliser pour générer, transmettre et exécuter des applications à Docker ou exécuter d’autres opérations offertes par la CLI Docker Compose, comme illustré dans la Figure 5-3.

![](./media/image3.png)

Figure 5-3 : Le pipeline d’intégration continue Docker dans les Services Azure DevOps

L’extension de Docker peut utiliser des points de terminaison de service pour les ordinateurs hôtes de Docker et de conteneur ou de registres d’images. La valeur par défaut de tâches à l’aide d’un hôte Docker local s’il est disponible (cela actuellement nécessite un agent Azure DevOps Services personnalisé) ; Sinon, ils nécessitent que vous fournissiez une connexion d’hôte Docker. Actions qui dépendent d’authentifié avec un Registre Docker, telles qu’envoyer une image, nécessitent que vous fournissiez un Docker connexion au Registre.

L’extension Docker de Services Azure DevOps installe les composants suivants dans votre compte Azure DevOps Services :

-   Un point de terminaison de service pour se connecter à un Registre Docker

-   Un point de terminaison de service pour la connexion à un hôte de conteneur Docker

-   Une tâche de Docker pour effectuer les opérations suivantes :

-   Générer une image

-   Envoyez une image ou un référentiel vers un Registre

-   Exécuter une image dans un conteneur

-   Exécuter une commande Docker

-   Une tâche de Docker Compose pour exécuter une commande Docker Compose

Avec ces tâches Azure DevOps Services, une build/la machine virtuelle Linux Docker hôte configuré dans Azure et votre Registre Docker par défaut (Azure Container Registry, Docker Hub, DTR de Docker privé ou tout autre registre Docker), vous pouvez assembler votre pipeline CI de Docker dans un très façon cohérente.

***Configuration requise :***

-   Les Services Azure DevOps, ou pour les installations locales, Team Foundation Server 2015 Update 3 ou version ultérieure.

-   Agent Azure DevOps Services a les binaires Docker.

Un moyen facile de créer une d’elles consiste à utiliser Docker pour exécuter un conteneur basé sur l’image Docker de l’agent Azure DevOps Services.

**Plus d’informations** pour en savoir plus sur l’assemblage d’un élément de configuration de Azure DevOps Services Docker de pipeline et que vous pour afficher les procédures pas à pas, consultez les sites suivants :

Un agent Azure DevOps Services en cours d’exécution en tant que conteneur Docker : [ https://hub.docker.com/r/\ microsoft/vsts-agent /](https://hub.docker.com/r/microsoft/vsts-agent/)

Extension Azure Docker de Services DevOps : <https://aka.ms/vstsdockerextension>

Création d’images de Docker .NET Core Linux avec Azure DevOps Services : <https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/>

Création d’un ordinateur de build basé sur Linux Visual Studio Team Service avec prise en charge de Docker : <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multicontainer-docker-applications"></a>Intégrer, tester et valider des applications Docker

En règle générale, la plupart des applications Docker sont composées de plusieurs conteneurs plutôt qu’un seul conteneur. Un bon exemple est une application orientée sur les microservices pour lequel vous aurait un conteneur par microservice. Toutefois, même sans strictement suivant les modèles d’approche de microservices, il est très probable que votre application Docker est composée de plusieurs conteneurs ou services.

Par conséquent, après avoir généré les conteneurs d’application dans le pipeline CI, vous devez également déployer, intégrer et tester l’application dans son ensemble avec tous ses conteneurs au sein d’un hôte Docker d’intégration ou même dans un cluster de test auquel sont vos conteneurs distribué.

Si vous utilisez un seul hôte, vous pouvez utiliser les commandes Docker tels que docker-compose pour générer et déployer des conteneurs associés pour tester et valider l’environnement Docker dans une seule machine virtuelle. Toutefois, si vous travaillez avec un cluster orchestrateur DC/OS, Kubernetes ou Docker Swarm, vous devez déployer vos conteneurs via un mécanisme différent ou un orchestrateur, en fonction de votre cluster/planificateur sélectionné.

Voici plusieurs types de tests que vous pouvez exécuter sur des conteneurs Docker :

-   Tests unitaires pour les conteneurs Docker

-   Test des groupes d’applications liées entre elles ou microservices

-   Tester dans les versions de production et « canari »

Le point important est que lors de l’exécution de l’intégration et les tests fonctionnels, vous devez exécuter ces tests à partir d’en dehors des conteneurs. Tests ne doivent pas être définis et s’exécutent dans les conteneurs que vous déployez, car les conteneurs sont basées sur des images statiques qui doivent être exactement comme ceux que vous souhaitez déployer en production.

Une option très envisageable lorsque vous testez des scénarios plus avancés tels que le test de plusieurs clusters (tester le cluster, cluster intermédiaire et cluster de production) consiste à publier les images dans un Registre à tester dans des clusters différents.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Transmettre l’image de Docker d’application personnalisée à votre Registre Docker global

Une fois que les images Docker ont été testés et validés, vous souhaitez étiqueter et de les publier dans votre Registre Docker. Le Registre Docker est un élément essentiel dans le cycle de vie d’application Docker, car il est un emplacement central où vous stockez votre test personnalisé (également appelé « images privilégiés ») d’être déployés dans des environnements d’assurance qualité et de production.

Semblable à la façon dont le code d’application stocké dans votre référentiel de contrôle de code source (Git, etc.) est votre « source de vérité », le Registre Docker est votre « source de vérité » pour votre application binaire ou les bits à déployer sur les environnements de production ou d’assurance qualité.

En règle générale, vous souhaiterez peut-être avoir vos référentiels privés pour vos images personnalisées dans un référentiel privé dans Azure Container Registry ou, dans un Registre local comme Docker Trusted Registry ou dans un Registre de cloud public avec un accès restreint (par exemple Docker Hub), bien que dans ce dernier cas, si votre code n’est pas open source, vous devez approuver la sécurité du fournisseur. Dans les deux cas, la méthode par laquelle cela est assez similaire et finalement repose sur la commande push docker, comme illustré dans la Figure 5-4.

![](./media/image4.png)

Figure 5-4 : Publication des images personnalisées à un Registre Docker

Il existe plusieurs offres de registres Docker à partir de fournisseurs de cloud comme Azure Container Registry, Registre de conteneurs d’Amazon Web Services, Google Container Registry, quai de Registre et ainsi de suite.

À l’aide de l’extension Docker de Services Azure DevOps, vous pouvez transmettre un ensemble d’images de service défini par un fichier docker-compose.yml, avec plusieurs balises à un Registre Docker authentifié (comme Azure Container Registry), comme illustré dans la Figure 5-5.

![](./media/image5.png)

Figure 5-5 : À l’aide d’Azure DevOps Services pour la publication des images personnalisées dans un Registre Docker

**Plus d’informations** pour en savoir plus sur l’extension Docker pour Azure DevOps Services, accédez à <https://aka.ms/vstsdockerextension>. Pour en savoir plus sur Azure Container Registry, accédez à <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Étape 4 : CD, déployer

L’immuabilité des images Docker garantit un déploiement reproductible avec ce qui a développé, testé via l’élément de configuration et exécuter en production. Une fois que vous avez les images de Docker d’application publiées dans votre Registre Docker (privé ou public), vous pouvez les déployer sur les environnements de plusieurs dont vous disposez (production, assurance qualité, de mise en lots, etc.) à partir de votre pipeline de CD à l’aide des Services de DevOps Azure les tâches de pipeline ou Azure DevOps Services Release Management.

Toutefois, à ce stade il dépend de quel type d’application Docker que vous déployez. Déployant une simple application (à partir d’un point de vue composition et de déploiement) comme un monolithique application comprenant plusieurs conteneurs ou services et déployée vers plusieurs serveurs ou machines virtuelles est très différent de déploiement d’une application plus complexe, comme un application orientée sur les microservices avec les fonctionnalités de très grande échelle. Ces deux scénarios sont expliqués dans les sections suivantes.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Déploiement des applications de Docker à plusieurs environnements Docker composées

Regardons premièrement le scénario moins complexes : déploiement d’hôtes Docker simples (machines virtuelles ou serveurs) dans un environnement unique ou de plusieurs environnements (assurance qualité, intermédiaire et production). Dans ce scénario, en interne votre pipeline de CD peut utiliser docker-compose (à partir de vos tâches de déploiement Azure DevOps Services) pour déployer les applications Docker avec son ensemble de conteneurs ou services, comme illustré dans la Figure 5-6.

![](./media/image6.png)

Figure 5-6 : Déploiement de conteneurs de l’application sur simple Registre d’environnements l’hôte Docker

Figure 5-7 met en évidence la façon dont vous pouvez vous connecter votre élément de configuration de build aux environnements de test/AQ via des Services Azure DevOps en cliquant sur Docker Compose dans la boîte de dialogue Ajouter une tâche. Toutefois, lors du déploiement de l’environnement intermédiaire ou de production, généralement utilisez Gestion des environnements de plusieurs des fonctionnalités de Release Management (telles que questions et réponses, intermédiaire et production). Si vous effectuez un déploiement à des hôtes Docker uniques, il utilise les Services de DevOps Azure tâche « Docker Compose » (ce qui revient à appeler le docker-commande sous le capot compose up). Si vous déployez dans Azure Container Service, il utilise la tâche de déploiement de Docker, comme expliqué dans la section qui suit.

![](./media/image7.png)

Figure 5-7 : Ajout d’une tâche Docker Compose dans un pipeline Azure DevOps Services

Lorsque vous créez une version dans les Services Azure DevOps, il prend un ensemble d’artefacts d’entrée. Elles sont destinées à être immuable pendant la durée de vie de la version sur plusieurs environnements. Lorsque vous introduisez des conteneurs, les artefacts d’entrée identifient les images dans un Registre à déployer. Selon la façon dont ces tests sont identifiés, ils ne sont pas garanties reste identique pendant toute la durée de la version, le cas le plus évident en cours lorsque vous faites référence à « myimage:latest » à partir d’un fichier docker-compose.

L’extension Docker pour Azure DevOps Services vous donne la possibilité de générer des artefacts de build qui contient l’image de Registre spécifiques des résumés qui sont garanties pour identifier de façon unique la même image binaire. Il s’agit de ce que vous voulez vraiment utiliser comme entrée pour une mise en production.

### <a name="managing-releases-to-docker-environments-by-using-azure-devops-services-release-management"></a>Gestion des versions aux environnements Docker à l’aide d’Azure DevOps Services Release Management

Via les extensions Azure DevOps Services, vous pouvez créer une nouvelle image, publiez-le dans un Registre Docker, exécutez-le sur les hôtes Linux ou Windows et utiliser des commandes telles que docker-compose pour déployer plusieurs conteneurs comme une application entière, soutenue du DevOps Azure Services des fonctionnalités de gestion de version destinées à plusieurs environnements, comme illustré dans la Figure 5-8.

![](./media/image8.png)

Figure 5-8 : Configuration d’Azure DevOps Services Docker Compose de tâches à partir d’Azure DevOps Services Release Management

Toutefois, n’oubliez pas que le scénario illustré dans la Figure 5-6 et implémenté dans la Figure 5-8 est assez basique (qu’il déploie sur les hôtes Docker simples et des machines virtuelles, et il y aura un seul conteneur ou une instance par image) et probablement doit être utilisé uniquement pour le développement ou test sc Gestionnaire de scénarios. Dans la plupart des scénarios de production d’entreprise, vous pourriez avoir de haute disponibilité (HA) et facile à gérer l’évolutivité par un équilibrage de charge entre plusieurs nœuds, serveurs et les machines virtuelles, ainsi que « intelligents basculements » par conséquent, si un serveur ou un nœud échoue, ses services et conteneurs seront déplacés vers un autre serveur hôte ou une machine virtuelle. Dans ce cas, vous avez besoin des technologies plus avancées telles que les clusters de conteneurs, les orchestrateurs et les planificateurs. Par conséquent, la façon de déployer à ces clusters est précisément via les scénarios avancés, expliqués dans la section suivante.

### <a name="deploying-complex-docker-applications-to-docker-clusters-dcos-kubernetes-and-docker-swarm"></a>Déploiement d’applications Docker complexes à des clusters Docker (DC/OS, Kubernetes et Docker Swarm)

La nature des applications distribuées nécessite des ressources de calcul sont également distribués. Pour que les fonctionnalités à l’échelle de production, vous devez disposer de fonctionnalités qui fournissent une haute évolutivité de clustering et haute disponibilité basée sur les ressources mises en pool.

Vous pouvez déployer des conteneurs manuellement à ces clusters à partir d’un outil CLI telles que Docker Swarm (comme à l’aide de [de création du service de docker](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)) ou une interface utilisateur web comme [Mesosphere Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) pour DC/OS clusters, mais vous devez réserver qui uniquement pour le test de déploiement ponctuel à des fins de gestion telles que l’évolution horizontale ou à des fins de surveillance.

À partir d’un point de vue de CD et les Services Azure DevOps plus précisément, vous pouvez exécuter des tâches de déploiement spécialement effectuées à partir de vos environnements de gestion des versions de Services Azure DevOps qui vous allez déployer vos applications en conteneur pour les clusters répartis dans le conteneur Service, comme illustré dans la Figure 5-9.

![](./media/image9.png)

Figure 5-9 : Déploiement d’applications distribuées au Service de conteneur

Au départ, lorsque vous déployez à certains clusters ou les orchestrateurs, vous traditionnellement utiliseriez mécanismes par chaque orchestrateur (autrement dit, Mesosphere DC/OS ou Kubernetes disposent de mécanismes de déploiement différents à Docker et Docker et les scripts de déploiement spécifique Swarm) au lieu de la plus simple et facile à utiliser docker-composent outil basé sur le fichier de définition de docker-compose.YML. Toutefois, grâce à la tâche de déploiement de Microsoft Azure DevOps Services Docker, illustrée à la Figure 5-10, vous maintenant pouvez également déployer au contrôleur de domaine/système d’exploitation en utilisant simplement votre fichier familier docker-compose.yml étant donné que Microsoft effectue cette « traduction » pour vous (à partir de votre fichier docker-compose.yml dans d’autres formats requis par DC/OS).

![](./media/image10.png)

Figure 5-10 : Ajout de la tâche de déploiement Docker à votre gestionnaire de ressources d’environnement

Figure 5-11 montre comment vous pouvez modifier la tâche de déploiement de Docker et spécifier le Type de cible (Azure Container Service DC/OS, dans ce cas), votre fichier Docker Compose et la connexion au Registre de Docker (comme Azure Container Registry ou Docker Hub). Il s’agit de la tâche récupère où vos images Docker personnalisées de prêts à l’emploi pour être déployé en tant que conteneurs dans le cluster DC/OS.

![](./media/image11.png)

Figure 5-11 : Déploiement de docker déployer tâche définition du Service de conteneur DC/OS pour Azure

**Plus d’informations** pour en savoir plus sur le pipeline de CD avec Azure DevOps Services et Docker, visitez les sites suivants :

Extension des Services de DevOps Azure pour Docker et Azure Container Service : [ https://aka.ms/\ vstsdockerextension](https://aka.ms/vstsdockerextension)

Azure Container Service : <https://aka.ms/azurecontainerservice>

Mesosphere DC/OS : <https://mesosphere.com/product/>

## <a name="step-5-run-and-manage"></a>Étape 5 : Exécuter et gérer

Étant donné qu’en cours d’exécution et la gestion des applications en production de l’entreprise au niveau est un sujet majeur dans et de lui-même, en raison du type d’opérations et personnes travaillent à ce niveau (opérations informatiques), ainsi que l’étendue de grande taille de cette zone, nous avons consacré l’ensemble suivant chapitre à expliquer.

## <a name="step-6-monitor-and-diagnose"></a>Étape 6 : Surveiller et diagnostiquer

Cette rubrique également est couvert dans le chapitre suivant dans le cadre des tâches qui effectue des opérations informatiques dans les systèmes de production ; Toutefois, il est important de souligner que les informations obtenues lors de cette étape doivent flux à l’équipe de développement afin que l’application est améliorée en permanence. À partir de ce point de vue, il fait également partie de DevOps, bien que les tâches et les opérations sont généralement effectuées par informatique.

Uniquement lors de la surveillance et diagnostic est à 100 % dans le domaine du DevOps sont les processus de surveillance et les analytique effectuée par l’équipe de développement par rapport à des environnements de test ou de la version bêta. Pour cela en effectuant des tests de charge ou simplement en version bêta ou les environnements d’assurance qualité, où les bêta-testeurs essayez les nouvelles versions de surveillance.

>[!div class="step-by-step"]
>[Précédent](index.md)
>[Suivant](create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
