---
title: Desarrollar componentes personalizados | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12b7d99d-ac3c-427d-b6b6-286233fde541
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b61144b2acaf787d56468c23c04835b5ad79324
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="developing-custom-components"></a><span data-ttu-id="bfce9-102">Desarrollar componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="bfce9-102">Developing Custom Components</span></span>
<span data-ttu-id="bfce9-103">Los componentes personalizados se desarrollan y utilizan en BizTalk Server para modificar o extender algunos elementos de infraestructura de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="bfce9-103">Custom components in BizTalk Server are developed and used to modify or extend certain infrastructure elements of BizTalk Server.</span></span>  <span data-ttu-id="bfce9-104">Principalmente, esto incluye elementos tales como: enviar o recibir componentes del adaptador que se basan en el marco de trabajo y se usa para controlar los protocolos de transporte específicos; componentes de canalización usados en cualquiera de envío o recepción etapas de canalización; y functoids usados en las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="bfce9-104">Primarily, this includes such things as:  send or receive adapter components which are based on the Adapter Framework and used to handle specific transport protocols; pipeline components used in any of the send or receive pipeline stages; and functoids used in maps.</span></span>  <span data-ttu-id="bfce9-105">Puede extender [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con código personalizado de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="bfce9-105">You can extend [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with custom code in several ways.</span></span> <span data-ttu-id="bfce9-106">En los temas siguientes se describe cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="bfce9-106">The following topics describe how to do this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bfce9-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bfce9-107">In This Section</span></span>  
  
-   [<span data-ttu-id="bfce9-108">Desarrollar adaptadores personalizados</span><span class="sxs-lookup"><span data-stu-id="bfce9-108">Developing Custom Adapters</span></span>](../core/developing-custom-adapters.md)  
  
-   [<span data-ttu-id="bfce9-109">Desarrollar componentes de canalización personalizado</span><span class="sxs-lookup"><span data-stu-id="bfce9-109">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)  
  
-   [<span data-ttu-id="bfce9-110">Desarrollar Functoids personalizados</span><span class="sxs-lookup"><span data-stu-id="bfce9-110">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)