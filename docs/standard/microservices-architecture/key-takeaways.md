---
title: "points clés"
description: "Architecture de Microservices .NET pour les Applications .NET en conteneur | points clés"
keywords: Docker, microservices, ASP.NET, conteneur
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b557d0b641bfe95c025cadb13f82c3f8927f4bc8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="key-takeaways"></a><span data-ttu-id="8d754-104">Points clés</span><span class="sxs-lookup"><span data-stu-id="8d754-104">Key Takeaways</span></span>

<span data-ttu-id="8d754-105">En tant qu’un résumé et des points, voici les conclusions plus importantes à partir de ce guide.</span><span class="sxs-lookup"><span data-stu-id="8d754-105">As a summary and key takeaways, the following are the most important conclusions from this guide.</span></span>

<span data-ttu-id="8d754-106">**Avantages de l’utilisation de conteneurs.**</span><span class="sxs-lookup"><span data-stu-id="8d754-106">**Benefits of using containers.**</span></span> <span data-ttu-id="8d754-107">Solutions basées sur le conteneur offrent l’avantage important de réduction des coûts, car les conteneurs sont une solution aux problèmes de déploiement en raison du manque de dépendances dans les environnements de production.</span><span class="sxs-lookup"><span data-stu-id="8d754-107">Container-based solutions provide the important benefit of cost savings because containers are a solution to deployment problems caused by the lack of dependencies in production environments.</span></span> <span data-ttu-id="8d754-108">Conteneurs améliorer considérablement les opérations de production et de DevOps.</span><span class="sxs-lookup"><span data-stu-id="8d754-108">Containers significantly improve DevOps and production operations.</span></span>

<span data-ttu-id="8d754-109">**Conteneurs sera très répandues.**</span><span class="sxs-lookup"><span data-stu-id="8d754-109">**Containers will be ubiquitous.**</span></span> <span data-ttu-id="8d754-110">Conteneurs docker deviennent la norme du secteur de conteneur, pris en charge par les fournisseurs plus significatifs dans les écosystèmes Windows et Linux.</span><span class="sxs-lookup"><span data-stu-id="8d754-110">Docker-based containers are becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="8d754-111">Cela inclut Microsoft, Amazon AWS, Google et IBM.</span><span class="sxs-lookup"><span data-stu-id="8d754-111">This includes Microsoft, Amazon AWS, Google, and IBM.</span></span> <span data-ttu-id="8d754-112">Dans un futur proche, Docker sera probablement très répandue dans les centres de données à la fois locaux et cloud.</span><span class="sxs-lookup"><span data-stu-id="8d754-112">In the near future, Docker will probably be ubiquitous in both cloud and on-premises datacenters.</span></span>

<span data-ttu-id="8d754-113">**Conteneurs en tant qu’unité de déploiement.**</span><span class="sxs-lookup"><span data-stu-id="8d754-113">**Containers as a unit of deployment.**</span></span> <span data-ttu-id="8d754-114">Un conteneur Docker devient l’unité de déploiement pour toute application basée sur le serveur ou le service standard.</span><span class="sxs-lookup"><span data-stu-id="8d754-114">A Docker container is becoming the standard unit of deployment for any server-based application or service.</span></span>

<span data-ttu-id="8d754-115">**Microservices.**</span><span class="sxs-lookup"><span data-stu-id="8d754-115">**Microservices.**</span></span> <span data-ttu-id="8d754-116">L’architecture de microservices devient la meilleure approche pour les applications critiques en distribuée et volumineuse ou complexes selon plusieurs sous-systèmes indépendants sous la forme de services autonomes.</span><span class="sxs-lookup"><span data-stu-id="8d754-116">The microservices architecture is becoming the preferred approach for distributed and large or complex mission-critical applications based on multiple independent subsystems in the form of autonomous services.</span></span> <span data-ttu-id="8d754-117">Dans une architecture microservice, l’application est générée comme une collection de services qui peuvent être développés, testés, version, déployé et à l’échelle de manière indépendante ; Cela peut inclure une base de données autonome connexe.</span><span class="sxs-lookup"><span data-stu-id="8d754-117">In a microservice-based architecture, the application is built as a collection of services that can be developed, tested, versioned, deployed, and scaled independently; this can include any related autonomous database.</span></span>

<span data-ttu-id="8d754-118">**Conception domaine et SOA.**</span><span class="sxs-lookup"><span data-stu-id="8d754-118">**Domain-driven design and SOA.**</span></span> <span data-ttu-id="8d754-119">Les modèles d’architecture microservices dérivent de l’architecture orientée services (SOA) et de conception domaine (DDD).</span><span class="sxs-lookup"><span data-stu-id="8d754-119">The microservices architecture patterns derive from service-oriented architecture (SOA) and domain-driven design (DDD).</span></span> <span data-ttu-id="8d754-120">Lorsque vous concevez et développez des microservices pour les environnements à l’évolution des règles d’entreprise mise en forme d’un domaine particulier, il est important de prendre en compte DDD approches et les modèles.</span><span class="sxs-lookup"><span data-stu-id="8d754-120">When you design and develop microservices for environments with evolving business rules shaping a particular domain, it is important to take into account DDD approaches and patterns.</span></span>

<span data-ttu-id="8d754-121">**Microservices défis.**</span><span class="sxs-lookup"><span data-stu-id="8d754-121">**Microservices challenges.**</span></span> <span data-ttu-id="8d754-122">Microservices offrent de nombreuses fonctionnalités puissantes comme indépendant de déploiement des limites du sous-système fort et diversité de technologie.</span><span class="sxs-lookup"><span data-stu-id="8d754-122">Microservices offer many powerful capabilities, like independent deployment, strong subsystem boundaries, and technology diversity.</span></span> <span data-ttu-id="8d754-123">Toutefois, ils déclenchent également plusieurs nouveaux défis associés au développement d’applications distribuées, telles que fragmenté et modèles de données indépendant, communication résiliente entre microservices et la complexité opérationnelle qui résulte de la cohérence éventuelle agrégation des informations de journalisation et d’analyse à partir de plusieurs microservices.</span><span class="sxs-lookup"><span data-stu-id="8d754-123">However, they also raise many new challenges related to distributed application development, such as fragmented and independent data models, resilient communication between microservices, eventual consistency, and operational complexity that results from aggregating logging and monitoring information from multiple microservices.</span></span> <span data-ttu-id="8d754-124">Ces aspects présentent un niveau supérieur de complexité à une application monolithique traditionnelle.</span><span class="sxs-lookup"><span data-stu-id="8d754-124">These aspects introduce a higher level of complexity than a traditional monolithic application.</span></span> <span data-ttu-id="8d754-125">Par conséquent, des scénarios spécifiques conviennent pour les applications microservice.</span><span class="sxs-lookup"><span data-stu-id="8d754-125">As a result, only specific scenarios are suitable for microservice-based applications.</span></span> <span data-ttu-id="8d754-126">Ceux-ci incluent des applications volumineuses et complexes avec plusieurs sous-systèmes en constante évolution ; dans ces cas, il est investir dans une architecture de logiciel plus complexe, car elle fournit à long terme une meilleure souplesse et une maintenance de l’application.</span><span class="sxs-lookup"><span data-stu-id="8d754-126">These include large and complex applications with multiple evolving subsystems; in these cases, it is worth investing in a more complex software architecture, because it will provide better long-term agility and application maintenance.</span></span>

<span data-ttu-id="8d754-127">**Conteneurs pour n’importe quelle application.**</span><span class="sxs-lookup"><span data-stu-id="8d754-127">**Containers for any application.**</span></span> <span data-ttu-id="8d754-128">Conteneurs sont pratiques pour microservices, mais ne sont pas exclusifs pour eux.</span><span class="sxs-lookup"><span data-stu-id="8d754-128">Containers are convenient for microservices, but are not exclusive for them.</span></span> <span data-ttu-id="8d754-129">Conteneurs peuvent également servir aux applications monolithiques, y compris les applications héritées basé sur le .NET Framework traditionnelles et modernisé via les conteneurs Windows.</span><span class="sxs-lookup"><span data-stu-id="8d754-129">Containers can also be used with monolithic applications, including legacy applications based on the traditional .NET Framework and modernized through Windows Containers.</span></span> <span data-ttu-id="8d754-130">Les avantages de l’utilisation de Docker, telles que la résolution de nombreux problèmes de déploiement de production et en fournissant des environnements de développement et de Test de pointe, s’appliquent à différents types d’applications.</span><span class="sxs-lookup"><span data-stu-id="8d754-130">The benefits of using Docker, such as solving many deployment-to-production issues and providing state of the art Dev and Test environments, apply to many different types of applications.</span></span>

<span data-ttu-id="8d754-131">**CLI par rapport à l’IDE.**</span><span class="sxs-lookup"><span data-stu-id="8d754-131">**CLI versus IDE.**</span></span> <span data-ttu-id="8d754-132">Avec les outils de Microsoft, vous pouvez développer des applications .NET en conteneur à l’aide de votre approche par défaut.</span><span class="sxs-lookup"><span data-stu-id="8d754-132">With Microsoft tools, you can develop containerized .NET applications using your preferred approach.</span></span> <span data-ttu-id="8d754-133">Vous pouvez développer avec une interface CLI et un environnement basé sur l’éditeur à l’aide de l’interface CLI de Docker et d’un Code de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8d754-133">You can develop with a CLI and an editor-based environment by using the Docker CLI and Visual Studio Code.</span></span> <span data-ttu-id="8d754-134">Ou vous pouvez utiliser une approche axée sur l’IDE avec Visual Studio et ses fonctionnalités uniques pour Docker, telles que comme étant en mesure de déboguer des applications conteneur multi.</span><span class="sxs-lookup"><span data-stu-id="8d754-134">Or you can use an IDE-focused approach with Visual Studio and its unique features for Docker, such as like being able to debug multi-container applications.</span></span>

<span data-ttu-id="8d754-135">**Applications résilientes du cloud.**</span><span class="sxs-lookup"><span data-stu-id="8d754-135">**Resilient cloud applications.**</span></span> <span data-ttu-id="8d754-136">Dans les systèmes basés sur le cloud et de systèmes distribués, en général, il est toujours le risque de défaillance partielle.</span><span class="sxs-lookup"><span data-stu-id="8d754-136">In cloud-based systems and distributed systems in general, there is always the risk of partial failure.</span></span> <span data-ttu-id="8d754-137">Étant donné que les clients et services sont des processus distincts (conteneurs), un service n’est peut-être pas en mesure de répondre à une demande du client à un moment opportun.</span><span class="sxs-lookup"><span data-stu-id="8d754-137">Since clients and services are separate processes (containers), a service might not be able to respond in a timely way to a client’s request.</span></span> <span data-ttu-id="8d754-138">Par exemple, un service peut être vers le bas en raison d’une défaillance partielle ou de maintenance ; le service peut être surchargé et répondre extrêmement lent à la demande ; ou bien, il peut simplement être accessible pour une courte période en raison de problèmes de réseau.</span><span class="sxs-lookup"><span data-stu-id="8d754-138">For example, a service might be down because of a partial failure or for maintenance; the service might be overloaded and responding extremely slowly to requests; or it might simply not be accessible for a short time because of network issues.</span></span> <span data-ttu-id="8d754-139">Par conséquent, une application basée sur le cloud doit adopter ces défaillances et mettre en œuvre pour répondre à ces défaillances une stratégie.</span><span class="sxs-lookup"><span data-stu-id="8d754-139">Therefore, a cloud-based application must embrace those failures and have a strategy in place to respond to those failures.</span></span> <span data-ttu-id="8d754-140">Ces stratégies peuvent inclure des stratégies de nouvelle tentative (renvoi des messages ou une nouvelle tentative de demandes) et implémentation des modèles de disjoncteur afin d’éviter la valeur exponentielle de charge des requêtes répétées.</span><span class="sxs-lookup"><span data-stu-id="8d754-140">These strategies can include retry policies (resending messages or retrying requests) and implementing circuit-breaker patterns to avoid exponential load of repeated requests.</span></span> <span data-ttu-id="8d754-141">En fait, les applications cloud doivent avoir des mécanismes résilients — personnalisé celles, ou ceux basés sur une infrastructure cloud, tels que les infrastructures de haut niveau à partir d’orchestrators ou le bus de service.</span><span class="sxs-lookup"><span data-stu-id="8d754-141">Basically, cloud-based applications must have resilient mechanisms—either custom ones, or ones based on cloud infrastructure, such as high-level frameworks from orchestrators or service buses.</span></span>

<span data-ttu-id="8d754-142">**Sécurité.**</span><span class="sxs-lookup"><span data-stu-id="8d754-142">**Security.**</span></span> <span data-ttu-id="8d754-143">Notre monde moderne de conteneurs et microservices peut exposer de nouvelles vulnérabilités.</span><span class="sxs-lookup"><span data-stu-id="8d754-143">Our modern world of containers and microservices can expose new vulnerabilities.</span></span> <span data-ttu-id="8d754-144">Sécurité de l’application de base est basée sur l’authentification et d’autorisation ; Il existe plusieurs façons pour les implémenter.</span><span class="sxs-lookup"><span data-stu-id="8d754-144">Basic application security is based on authentication and authorization; multiple ways exist to implement these.</span></span> <span data-ttu-id="8d754-145">Toutefois, la sécurité de conteneur inclut les composants clés supplémentaires qui génèrent les applications intrinsèquement plus sûres.</span><span class="sxs-lookup"><span data-stu-id="8d754-145">However, container security includes additional key components that result in inherently safer applications.</span></span> <span data-ttu-id="8d754-146">Un élément essentiel de la création d’applications plus sûres rencontre un moyen sécurisé de communiquer avec d’autres applications et les systèmes, quelque chose requiert souvent des informations d’identification, les jetons, les mots de passe et autres types d’informations confidentielles, généralement appelées secrets de l’application.</span><span class="sxs-lookup"><span data-stu-id="8d754-146">A critical element of building safer apps is having a secure way of communicating with other apps and systems, something that often requires credentials, tokens, passwords, and other types of confidential information—usually referred to as application secrets.</span></span> <span data-ttu-id="8d754-147">Une solution sécurisée doit suivre les meilleures pratiques de sécurité, telles que le chiffrement des clés secrètes en cours de transit ; chiffrement des clés secrètes au repos ; et empêche que les secrets involontairement une fuite lorsque consommé par l’application finale.</span><span class="sxs-lookup"><span data-stu-id="8d754-147">Any secure solution must follow security best practices, such as encrypting secrets while in transit; encrypting secrets at rest; and preventing secrets from unintentionally leaking when consumed by the final application.</span></span> <span data-ttu-id="8d754-148">Ces clés secrètes doivent être stockées et protégées quelque part.</span><span class="sxs-lookup"><span data-stu-id="8d754-148">Those secrets need to be stored and kept safe somewhere.</span></span> <span data-ttu-id="8d754-149">Pour améliorer la sécurité, vous pouvez tirer parti de l’infrastructure de votre orchestrator choisi, ou de l’infrastructure de cloud comme Azure Key Vault et les méthodes qu’il fournit pour le code d’application pour l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="8d754-149">To help with security, you can take advantage of your chosen orchestrator’s infrastructure, or of cloud infrastructure like Azure Key Vault and the ways it provides for application code to use it.</span></span>

<span data-ttu-id="8d754-150">**Orchestrators.**</span><span class="sxs-lookup"><span data-stu-id="8d754-150">**Orchestrators.**</span></span> <span data-ttu-id="8d754-151">Basé sur le conteneur orchestrators telles que celles fournies dans le Service de conteneur Azure (Kubernetes Mesos DC/OS et Docker Swarm) et Azure Service Fabric sont indispensables pour n’importe quelle application prête à la production microservice et pour n’importe quel conteneur multiples application avec une complexité significative, les besoins de l’évolutivité et constante évolution.</span><span class="sxs-lookup"><span data-stu-id="8d754-151">Container-based orchestrators like the ones provided in Azure Container Service (Kubernetes, Mesos DC/OS, and Docker Swarm) and Azure Service Fabric are indispensable for any production-ready microservice-based application and for any multi-container application with significant complexity, scalability needs, and constant evolution.</span></span> <span data-ttu-id="8d754-152">Ce guide propose orchestrators et leur rôle dans les solutions basées sur le conteneur et microservice.</span><span class="sxs-lookup"><span data-stu-id="8d754-152">This guide has introduced orchestrators and their role in microservice-based and container-based solutions.</span></span> <span data-ttu-id="8d754-153">Si les besoins de votre application vous déplacez vers des applications en conteneur complexes, il sera utile rechercher des ressources supplémentaires pour en savoir plus sur orchestrators</span><span class="sxs-lookup"><span data-stu-id="8d754-153">If your application needs are moving you toward complex containerized apps, you will find it useful to seek out additional resources for learning more about orchestrators</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="8d754-154">[Précédente] (secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="8d754-154">[Previous] (secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)</span></span>