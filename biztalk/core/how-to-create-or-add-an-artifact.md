---
title: Cómo crear o agregar un artefacto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, creating
- applications, artifacts
ms.assetid: fea7487c-b5fa-457f-8c74-a20ea3a6df85
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b231cdf6a25c4ca316c9620ee789e6e3a715fd6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249492"
---
# <a name="how-to-create-or-add-an-artifact"></a><span data-ttu-id="306c2-102">Cómo crear o agregar un artefacto</span><span class="sxs-lookup"><span data-stu-id="306c2-102">How to Create or Add an Artifact</span></span>
<span data-ttu-id="306c2-103">Tras crear una aplicación de BizTalk, puede agregar artefactos basados en archivo (por ejemplo, ensamblados de BizTalk, ensamblados de .NET, secuencias de comandos y certificados) desde el sistema de archivos o agregar directivas desde la base de datos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="306c2-103">After you create a BizTalk application, you can add file-based artifacts (for example BizTalk assemblies, .NET assemblies, scripts, and certificates) from the file system or add policies from the Rule Engine database.</span></span> <span data-ttu-id="306c2-104">También puede crear puertos de envío, grupos de puertos de envío, ubicaciones de recepción y puertos de recepción desde la aplicación.</span><span class="sxs-lookup"><span data-stu-id="306c2-104">You can also create send ports, send port groups, receive locations, and receive ports within the application.</span></span> <span data-ttu-id="306c2-105">Al crear o agregar artefactos, estos se agregan a la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="306c2-105">Creating or adding artifacts adds them to the BizTalk Management database.</span></span> <span data-ttu-id="306c2-106">Puede implementar la aplicación y sus artefactos como una sola entidad, como se describe en [implementar aplicaciones de BizTalk](../core/deploying-biztalk-applications.md).</span><span class="sxs-lookup"><span data-stu-id="306c2-106">You can then deploy the application and its artifacts as a single entity, as described in [Deploying BizTalk Applications](../core/deploying-biztalk-applications.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="306c2-107">Ciertos tipos de artefactos deben ser únicos en una aplicación de BizTalk o un grupo.</span><span class="sxs-lookup"><span data-stu-id="306c2-107">Certain types of artifacts must be unique in a BizTalk application or group.</span></span> <span data-ttu-id="306c2-108">Para obtener más información, consulte [artefactos que deben ser únicos en una aplicación o un grupo de](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span><span class="sxs-lookup"><span data-stu-id="306c2-108">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span>  
  
 <span data-ttu-id="306c2-109">Para consultar los procesos para agregar o crear cada tipo de artefacto, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="306c2-109">For procedures on adding or creating each artifact type, see the following topics:</span></span>  
  
-   [<span data-ttu-id="306c2-110">Cómo crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="306c2-110">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)  
  
-   [<span data-ttu-id="306c2-111">Cómo crear un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="306c2-111">How to Create a Send Port Group</span></span>](../core/how-to-create-a-send-port-group.md)  
  
-   [<span data-ttu-id="306c2-112">Cómo crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="306c2-112">How to Create a Receive Port</span></span>](../core/how-to-create-a-receive-port.md)  
  
-   [<span data-ttu-id="306c2-113">Cómo crear una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="306c2-113">How to Create a Receive Location</span></span>](../core/how-to-create-a-receive-location.md)  
  
-   [<span data-ttu-id="306c2-114">Cómo agregar una directiva a una aplicación</span><span class="sxs-lookup"><span data-stu-id="306c2-114">How to Add a Policy to an Application</span></span>](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [<span data-ttu-id="306c2-115">Cómo agregar un ensamblado de BizTalk a una aplicación</span><span class="sxs-lookup"><span data-stu-id="306c2-115">How to Add a BizTalk Assembly to an Application</span></span>](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="306c2-116">Cómo agregar una secuencia de comandos previa y posteriores al procesamiento a una aplicación</span><span class="sxs-lookup"><span data-stu-id="306c2-116">How to Add a Pre- or Post-processing Script to an Application</span></span>](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [<span data-ttu-id="306c2-117">Cómo agregar un archivo a una aplicación</span><span class="sxs-lookup"><span data-stu-id="306c2-117">How to Add a File to an Application</span></span>](../core/how-to-add-a-file-to-an-application.md)  
  
-   [<span data-ttu-id="306c2-118">Cómo agregar un certificado a una aplicación</span><span class="sxs-lookup"><span data-stu-id="306c2-118">How to Add a Certificate to an Application</span></span>](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [<span data-ttu-id="306c2-119">Cómo agregar un componente COM a una aplicación</span><span class="sxs-lookup"><span data-stu-id="306c2-119">How to Add a COM Component to an Application</span></span>](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [<span data-ttu-id="306c2-120">Cómo agregar un ensamblado de .NET a una aplicación</span><span class="sxs-lookup"><span data-stu-id="306c2-120">How to Add a .NET Assembly to an Application</span></span>](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="306c2-121">Cómo agregar un artefacto de BAM a una aplicación</span><span class="sxs-lookup"><span data-stu-id="306c2-121">How to Add a BAM Artifact to an Application</span></span>](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [<span data-ttu-id="306c2-122">Cómo agregar un archivo de enlace a una aplicación</span><span class="sxs-lookup"><span data-stu-id="306c2-122">How to Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
> [!NOTE]
>  <span data-ttu-id="306c2-123">Si el artefacto que está agregando tiene un nombre de ruta de acceso muy largo (por ejemplo, el nombre de archivo y de ruta de acceso), se producirá un error en la operación de agregar el artefacto a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="306c2-123">If the artifact you are adding has a very long path (e.g., the path and file name), the operation to add the artifact to an application may fail.</span></span> <span data-ttu-id="306c2-124">Una ruta de acceso no puede tener más de 260 caracteres.</span><span class="sxs-lookup"><span data-stu-id="306c2-124">A path can't exceed 260 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306c2-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="306c2-125">See Also</span></span>  
 <span data-ttu-id="306c2-126">[Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="306c2-126">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="306c2-127">Cómo agregar un artefacto de 64 bits a una aplicación</span><span class="sxs-lookup"><span data-stu-id="306c2-127">How to Add a 64-Bit Artifact to an Application</span></span>](../core/how-to-add-a-64-bit-artifact-to-an-application.md)