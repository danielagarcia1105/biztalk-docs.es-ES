---
title: "Creación de la solución de Contoso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: private process tutorial, creating solutions
ms.assetid: 02f5326a-68bd-418a-af81-684a73056e2c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e09928a724d99822d652b12daa959a7f7f380bc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-contoso-solution"></a><span data-ttu-id="b9b18-102">Creación de la solución de Contoso</span><span class="sxs-lookup"><span data-stu-id="b9b18-102">Creating the Contoso Solution</span></span>
<span data-ttu-id="b9b18-103">En esta sección se detalla los pasos que debe seguir para la organización de Contoso.</span><span class="sxs-lookup"><span data-stu-id="b9b18-103">This section details the steps that you have to follow for the Contoso organization.</span></span> <span data-ttu-id="b9b18-104">El primer paso consiste en agregar los contratos de asociado y de información de contacto para las dos organizaciones que utilizan el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="b9b18-104">The first step is to add the contact information and partner agreements for the two organizations using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="b9b18-105">A continuación, crear esquemas de línea de negocio (LOB) y crear una asignación entre dichos esquemas y sus respectivos esquemas de proceso de interfaz de socio (PIP) basados en RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="b9b18-105">You then create line-of-business (LOB) schemas, and construct a mapping between those schemas and their respective RosettaNet-based Partner Interface Process (PIP) schemas.</span></span> <span data-ttu-id="b9b18-106">A continuación, configure la información de puerto mediante el adaptador de SQL para comunicarse con el sistema ERP y el adaptador de HTTP para enviar información a Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="b9b18-106">Next, you configure port information using the SQL adapter for communicating with the ERP system, and the HTTP adapter for sending information to Fabrikam.</span></span> <span data-ttu-id="b9b18-107">El último paso consiste en Personalizar la orquestación de procesos privados para usar el motor de reglas de negocios (BRE) en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9b18-107">The last step is to customize the private process orchestration to use the Business Rule Engine (BRE) in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b9b18-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b9b18-108">In This Section</span></span>  
  
-   [<span data-ttu-id="b9b18-109">Creación de organizaciones y comerciales de acuerdo con el socio para Contoso</span><span class="sxs-lookup"><span data-stu-id="b9b18-109">Creating Organizations and Trading Partner Agreement for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-organizations-and-trading-partner-agreement-for-contoso.md)  
  
-   [<span data-ttu-id="b9b18-110">Crear los esquemas LOB de Contoso y asignaciones</span><span class="sxs-lookup"><span data-stu-id="b9b18-110">Creating the Contoso LOB Schemas and Maps</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-lob-schemas-and-maps.md)  
  
-   [<span data-ttu-id="b9b18-111">Crear y configurar puertos de BizTalk para Contoso</span><span class="sxs-lookup"><span data-stu-id="b9b18-111">Creating and Configuring BizTalk Ports for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)  
  
-   [<span data-ttu-id="b9b18-112">Crear y modificar el proceso privado de Contoso</span><span class="sxs-lookup"><span data-stu-id="b9b18-112">Creating and Modifying the Private Process for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-modifying-the-private-process-for-contoso.md)