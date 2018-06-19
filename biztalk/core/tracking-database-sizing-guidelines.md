---
title: Directrices de ajuste de tamaño de la base de datos de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, performance
- Tracking database, size
- Tracking Analysis Server database [BAM]
- performance, Tracking database
ms.assetid: 2188bee5-c0dd-4448-bd4a-4ffb2a0c79f1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c0293ff0a03583e51ee447ec1bd6283f1b02164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279700"
---
# <a name="tracking-database-sizing-guidelines"></a><span data-ttu-id="c3eed-102">Instrucciones para ajustar el tamaño de la base de datos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c3eed-102">Tracking Database Sizing Guidelines</span></span>
<span data-ttu-id="c3eed-103">Esta sección describen las consideraciones de tamaño de la base de datos de seguimiento de BizTalk (BizTalkDTADb) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3eed-103">This section describes sizing considerations for the BizTalk Tracking (BizTalkDTADb) database in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="c3eed-104">Explica cómo utilizar ecuaciones y variables de mensaje para determinar el tamaño que alcanzará la base de datos de seguimiento de BizTalk durante un determinado período de tiempo y proporciona ejemplos específicos sobre cómo aplicar las ecuaciones.</span><span class="sxs-lookup"><span data-stu-id="c3eed-104">It explains how to use equations and message variables to determine how large the BizTalk Tracking database will become over a given period of time, and provides specific examples of how to apply the equations.</span></span> <span data-ttu-id="c3eed-105">Esto proporciona la correlación aproximada entre los mensajes de BizTalk, la configuración de seguimiento y el tamaño de la base de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c3eed-105">This provides the rough co-relation between BizTalk messages, tracking settings and the tracking database size.</span></span> <span data-ttu-id="c3eed-106">No tiene en cuenta otros factores del servidor SQL Server como el tamaño del índice en las tablas de seguimiento; considere la posibilidad de utilizar multiplicadores razonables para contabilizar dichos factores.</span><span class="sxs-lookup"><span data-stu-id="c3eed-106">It does not take into account other SQL Server factors such as index size in the tracking tables; you may want to consider reasonable multipliers to account for those factors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3eed-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c3eed-107">In This Section</span></span>  
  
-   [<span data-ttu-id="c3eed-108">Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c3eed-108">Using Message Variables to Size the Tracking Database</span></span>](../core/using-message-variables-to-size-the-tracking-database.md)  
  
-   [<span data-ttu-id="c3eed-109">Ajustar el tamaño de la base de datos de seguimiento para realizar el seguimiento de cuerpos de mensaje</span><span class="sxs-lookup"><span data-stu-id="c3eed-109">Sizing the Tracking Database to Track Message Bodies</span></span>](../core/sizing-the-tracking-database-to-track-message-bodies.md)  
  
-   [<span data-ttu-id="c3eed-110">Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c3eed-110">Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages</span></span>](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)  
  
-   [<span data-ttu-id="c3eed-111">Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="c3eed-111">Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations</span></span>](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)  
  
-   [<span data-ttu-id="c3eed-112">Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución</span><span class="sxs-lookup"><span data-stu-id="c3eed-112">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)  
  
-   [<span data-ttu-id="c3eed-113">Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes</span><span class="sxs-lookup"><span data-stu-id="c3eed-113">Scenario 4: Sizing the Tracking Database for all Messages</span></span>](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)  
  
## <a name="see-also"></a><span data-ttu-id="c3eed-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3eed-114">See Also</span></span>  
 <span data-ttu-id="c3eed-115">[Tamaño del registro en las bases de datos de seguimiento](../core/record-size-in-tracking-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c3eed-115">[Record Size in Tracking Databases](../core/record-size-in-tracking-databases.md) </span></span>  
 [<span data-ttu-id="c3eed-116">Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c3eed-116">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)