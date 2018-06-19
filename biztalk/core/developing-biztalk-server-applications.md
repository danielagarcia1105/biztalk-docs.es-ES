---
title: Desarrollar aplicaciones de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99b56f86-d8e4-4f4a-9ce9-9f476ba88ea8
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c71782556d896d0697b73b83e2966f304b77a3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239604"
---
# <a name="developing-biztalk-server-applications"></a><span data-ttu-id="bca06-102">Desarrollar aplicaciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bca06-102">Developing BizTalk Server Applications</span></span>
<span data-ttu-id="bca06-103">Esta sección contiene información para programadores cuya misión es crear proyectos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bca06-103">This section contains information for developers who are tasked with creating BizTalk projects.</span></span> <span data-ttu-id="bca06-104">Los proyectos se crean utilizando el entorno de diseño del sistema del proyecto de BizTalk, que permite diseñar, organizar y generar varios elementos de aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bca06-104">Projects are created using the BizTalk project System Design Environment, which allows you to design, organize, and build the various elements of BizTalk applications.</span></span> <span data-ttu-id="bca06-105">En las siguientes secciones se describe el proceso detalladamente.</span><span class="sxs-lookup"><span data-stu-id="bca06-105">The following sections describe this process in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bca06-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bca06-106">In This Section</span></span>  
  
-   [<span data-ttu-id="bca06-107">Herramientas de desarrollo</span><span class="sxs-lookup"><span data-stu-id="bca06-107">Developer Tools</span></span>](../core/developer-tools.md)  
  
-   [<span data-ttu-id="bca06-108">Usar el motor de mensajería de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bca06-108">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)  
  
-   [<span data-ttu-id="bca06-109">Crear esquemas con el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bca06-109">Creating Schemas Using BizTalk Editor</span></span>](../core/creating-schemas-using-biztalk-editor.md)  
  
-   [<span data-ttu-id="bca06-110">Crear asignaciones usando al asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bca06-110">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)  
  
-   [<span data-ttu-id="bca06-111">Crear canalizaciones mediante el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="bca06-111">Creating Pipelines Using Pipeline Designer</span></span>](../core/creating-pipelines-using-pipeline-designer.md)  
  
-   [<span data-ttu-id="bca06-112">Crear orquestaciones mediante el Diseñador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="bca06-112">Creating Orchestrations Using Orchestration Designer</span></span>](../core/creating-orchestrations-using-orchestration-designer.md)  
  
-   [<span data-ttu-id="bca06-113">Crear y usar las reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="bca06-113">Creating and Using Business Rules</span></span>](../core/creating-and-using-business-rules.md)  
  
-   [<span data-ttu-id="bca06-114">Con los servicios Web</span><span class="sxs-lookup"><span data-stu-id="bca06-114">Using Web Services</span></span>](../core/using-web-services.md)  
  
-   [<span data-ttu-id="bca06-115">Uso de servicios WCF</span><span class="sxs-lookup"><span data-stu-id="bca06-115">Using WCF Services</span></span>](../core/using-wcf-services.md)  
  
-   [<span data-ttu-id="bca06-116">Consideraciones internacionales para diseñar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bca06-116">International Considerations for Designing BizTalk Applications</span></span>](../core/international-considerations-for-designing-biztalk-applications.md)  
  
-   [<span data-ttu-id="bca06-117">Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bca06-117">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)  
  
-   [<span data-ttu-id="bca06-118">Crear una aplicación de inicio de sesión única</span><span class="sxs-lookup"><span data-stu-id="bca06-118">Creating a Single Sign-On Application</span></span>](../core/creating-a-single-sign-on-application.md)  
  
-   [<span data-ttu-id="bca06-119">Ver ensamblados con el Visor de ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bca06-119">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)  
  
-   [<span data-ttu-id="bca06-120">Implementación de la seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="bca06-120">Implementing Message Security</span></span>](../core/implementing-message-security.md)  
  
## <a name="see-also"></a><span data-ttu-id="bca06-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bca06-121">See Also</span></span>  
 <span data-ttu-id="bca06-122">[Descripción de la implementación de aplicaciones de BizTalk y administración](../core/understanding-biztalk-application-deployment-and-management.md) </span><span class="sxs-lookup"><span data-stu-id="bca06-122">[Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md) </span></span>  
 <span data-ttu-id="bca06-123">[Implementación de aplicaciones de BizTalk y listas de comprobación de administración](../core/biztalk-application-deployment-and-management-checklists.md) </span><span class="sxs-lookup"><span data-stu-id="bca06-123">[BizTalk Application Deployment and Management Checklists](../core/biztalk-application-deployment-and-management-checklists.md) </span></span>  
 [<span data-ttu-id="bca06-124">Implementación de aplicaciones de BizTalk y los tutoriales de administración</span><span class="sxs-lookup"><span data-stu-id="bca06-124">BizTalk Application Deployment and Management Walkthroughs</span></span>](http://msdn.microsoft.com/library/5321f8e0-1e2a-4ac4-a4a2-fc244071bc5b)