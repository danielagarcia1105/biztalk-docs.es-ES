---
title: Creación y modificación de las aplicaciones de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], modifying
- managing [applications], creating
- applications, modifying
- applications, creating
- modifying, applications
- creating, applications
ms.assetid: d6c9ff3a-3903-40ec-bcaa-e46cbaf8a58d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5daa9630fb8ad742d34421478a19081ad5c83f50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238148"
---
# <a name="creating-and-modifying-biztalk-applications"></a><span data-ttu-id="54a92-102">Crear y modificar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="54a92-102">Creating and Modifying BizTalk Applications</span></span>
<span data-ttu-id="54a92-103">En esta sección se describe cómo usar la consola de administración de BizTalk Server o herramienta de línea de comandos BTSTask para crear, configurar y modificar aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="54a92-103">This section describes how to use the BizTalk Server Administration console or the BTSTask command-line tool to create, configure, and modify BizTalk applications.</span></span>  
  
 <span data-ttu-id="54a92-104">Para obtener información general acerca de cómo crear, administrar, implementar y actualizar aplicaciones de BizTalk, consulte [implementación de aplicación de BizTalk de descripción y administración](../core/understanding-biztalk-application-deployment-and-management.md).</span><span class="sxs-lookup"><span data-stu-id="54a92-104">For background information on creating, managing, deploying, and updating BizTalk applications, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="54a92-105">Para obtener información acerca de cómo administrar artefactos, incluida la edición de sus propiedades, vea [administrar artefactos](../core/managing-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="54a92-105">For information about managing artifacts, including editing their properties, see [Managing Artifacts](../core/managing-artifacts.md).</span></span> <span data-ttu-id="54a92-106">Para obtener instrucciones sobre cómo implementar aplicaciones de BizTalk, consulte [implementar aplicaciones de BizTalk](../core/deploying-biztalk-applications.md).</span><span class="sxs-lookup"><span data-stu-id="54a92-106">For instructions on deploying BizTalk applications, see [Deploying BizTalk Applications](../core/deploying-biztalk-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54a92-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="54a92-107">In This Section</span></span>  
  
-   [<span data-ttu-id="54a92-108">Cómo crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="54a92-108">How to Create an Application</span></span>](../core/how-to-create-an-application.md)  
  
-   [<span data-ttu-id="54a92-109">Cómo configurar una aplicación</span><span class="sxs-lookup"><span data-stu-id="54a92-109">How to Configure an Application</span></span>](../core/how-to-configure-an-application.md)  
  
-   [<span data-ttu-id="54a92-110">Cómo cambiar el nombre de una aplicación</span><span class="sxs-lookup"><span data-stu-id="54a92-110">How to Change the Name of an Application</span></span>](../core/how-to-change-the-name-of-an-application.md)  
  
-   [<span data-ttu-id="54a92-111">Cómo crear o agregar un artefacto</span><span class="sxs-lookup"><span data-stu-id="54a92-111">How to Create or Add an Artifact</span></span>](../core/how-to-create-or-add-an-artifact.md)  
  
-   [<span data-ttu-id="54a92-112">Cómo vincular a un archivo Léame</span><span class="sxs-lookup"><span data-stu-id="54a92-112">How to Link to a Readme File</span></span>](../core/how-to-link-to-a-readme-file.md)  
  
-   [<span data-ttu-id="54a92-113">Cómo agregar un artefacto de 64 bits a una aplicación</span><span class="sxs-lookup"><span data-stu-id="54a92-113">How to Add a 64-Bit Artifact to an Application</span></span>](../core/how-to-add-a-64-bit-artifact-to-an-application.md)  
  
-   [<span data-ttu-id="54a92-114">Cómo cambiar la aplicación predeterminada</span><span class="sxs-lookup"><span data-stu-id="54a92-114">How to Change the Default Application</span></span>](../core/how-to-change-the-default-application.md)  
  
-   [<span data-ttu-id="54a92-115">Cómo agregar una referencia a otra aplicación</span><span class="sxs-lookup"><span data-stu-id="54a92-115">How to Add a Reference to Another Application</span></span>](../core/how-to-add-a-reference-to-another-application.md)  
  
-   [<span data-ttu-id="54a92-116">Cómo ver las referencias de una aplicación</span><span class="sxs-lookup"><span data-stu-id="54a92-116">How to View the References of an Application</span></span>](../core/how-to-view-the-references-of-an-application.md)  
  
-   [<span data-ttu-id="54a92-117">Cómo quitar una referencia a otra aplicación</span><span class="sxs-lookup"><span data-stu-id="54a92-117">How to Remove a Reference to Another Application</span></span>](../core/how-to-remove-a-reference-to-another-application.md)  
  
-   [<span data-ttu-id="54a92-118">Cómo mover un artefacto a una aplicación diferente</span><span class="sxs-lookup"><span data-stu-id="54a92-118">How to Move an Artifact to a Different Application</span></span>](../core/how-to-move-an-artifact-to-a-different-application.md)  
  
-   [<span data-ttu-id="54a92-119">Cómo quitar un artefacto de una aplicación</span><span class="sxs-lookup"><span data-stu-id="54a92-119">How to Remove an Artifact from an Application</span></span>](../core/how-to-remove-an-artifact-from-an-application.md)