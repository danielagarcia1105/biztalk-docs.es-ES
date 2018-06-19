---
title: Solución de problemas de migración de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6eddc0a-2403-4bcd-9327-23f51ce7d57b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ddb6d9780a86183de5a09791de44adda5d57dab
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006061"
---
# <a name="troubleshooting-biztalk-server-migration"></a><span data-ttu-id="737bd-102">Solución de problemas de migración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="737bd-102">Troubleshooting BizTalk Server Migration</span></span>
<span data-ttu-id="737bd-103">Esta sección proporciona una ubicación centralizada para obtener información sobre los problemas comunes al migrar aplicaciones de BizTalk de [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] o [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="737bd-103">This section provides a centralized location for information about common problems encountered while migrating BizTalk applications from [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 to BizTalk Server.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="737bd-104">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="737bd-104">Known Issues</span></span>  
  
#### <a name="custom-applications-might-not-work-while-upgrading"></a><span data-ttu-id="737bd-105">Las aplicaciones personalizadas no funcionan durante la actualización</span><span class="sxs-lookup"><span data-stu-id="737bd-105">Custom applications might not work while upgrading</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="737bd-106">Problema</span><span class="sxs-lookup"><span data-stu-id="737bd-106">Problem</span></span>  
 <span data-ttu-id="737bd-107">Al actualizar desde [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] o [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 a BizTalk Server, algunas aplicaciones personalizadas no funcionen.</span><span class="sxs-lookup"><span data-stu-id="737bd-107">While upgrading from [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 to BizTalk Server, some custom applications might not work.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="737bd-108">Causa</span><span class="sxs-lookup"><span data-stu-id="737bd-108">Cause</span></span>  
 <span data-ttu-id="737bd-109">Todos los componentes de código administrado de BizTalk se ejecutan en CLR 4.0.</span><span class="sxs-lookup"><span data-stu-id="737bd-109">All the BizTalk managed code components run on CLR 4.0.</span></span> <span data-ttu-id="737bd-110">Dado que estos componentes se compilan con [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)], necesitan un archivo de configuración para ejecutarse en CLR 4.0.</span><span class="sxs-lookup"><span data-stu-id="737bd-110">As these components are compiled against [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)], they need a config file to run in CLR 4.0.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="737bd-111">Solución</span><span class="sxs-lookup"><span data-stu-id="737bd-111">Solution</span></span>  
 <span data-ttu-id="737bd-112">Para resolver este problema, actualice el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="737bd-112">To resolve this issue, update the config file.</span></span>  
  
```  
<configuration>  
<startup useLegacyV2RuntimeActivationPolicy="true">  
<supportedRuntime version="v4.0" />  
</startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="737bd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="737bd-113">See Also</span></span>  
 [<span data-ttu-id="737bd-114">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="737bd-114">Troubleshooting</span></span>](../core/troubleshooting.md)