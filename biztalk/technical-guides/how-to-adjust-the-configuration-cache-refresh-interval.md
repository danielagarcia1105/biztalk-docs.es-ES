---
title: Cómo ajustar el intervalo de actualización de caché de configuración | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63c6c998-e9c0-48f1-a36a-f1fcb916321b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad9459fadd65af220982ab31ae0e464cb7f1986e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297884"
---
# <a name="how-to-adjust-the-configuration-cache-refresh-interval"></a><span data-ttu-id="40a4b-102">Cómo ajustar el intervalo de actualización de caché de configuración</span><span class="sxs-lookup"><span data-stu-id="40a4b-102">How to Adjust the Configuration Cache Refresh Interval</span></span>
<span data-ttu-id="40a4b-103">El intervalo de actualización de caché de configuración define el período de tiempo en el que BizTalk Server actualiza la configuración de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="40a4b-103">The configuration cache refresh interval defines the time period in which BizTalk Server updates the configuration of the endpoints.</span></span> <span data-ttu-id="40a4b-104">Cuando se inicia el servidor BizTalk Server, todos los elementos de administración de BizTalk Server, como bases de datos de cuadro de mensajes, propiedades del servidor, adaptadores y conexiones a la base de datos de seguimiento se almacenan en la caché de configuración.</span><span class="sxs-lookup"><span data-stu-id="40a4b-104">When you start BizTalk Server, all items in BizTalk Server administration, such as MessageBox databases, server properties, adapters, and connections to the Tracking database, are stored in the configuration cache.</span></span> <span data-ttu-id="40a4b-105">Se actualizan todos los elementos de la memoria caché por el intervalo de actualización de configuración.</span><span class="sxs-lookup"><span data-stu-id="40a4b-105">All items in the cache are refreshed by the configuration refresh interval.</span></span> <span data-ttu-id="40a4b-106">De forma predeterminada, esto es cada 60 segundos, excepto para las conexiones de base de datos de servidor y las propiedades del servidor.</span><span class="sxs-lookup"><span data-stu-id="40a4b-106">By default this is every 60 seconds, except for the server database connections and server properties.</span></span> <span data-ttu-id="40a4b-107">Esto significa que si cambia las propiedades generales de un grupo de BizTalk, como el host de SMTP, los cambios se recogen en 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="40a4b-107">This means that if you change the general properties for a BizTalk group, such as the SMTP host, the changes are picked up within 60 seconds.</span></span> <span data-ttu-id="40a4b-108">No se reflejan los cambios realizados fuera de la instancia abierta actualmente de la consola de administración de BizTalk Server en el sistema hasta que los actualice.</span><span class="sxs-lookup"><span data-stu-id="40a4b-108">System changes made outside the currently open instance of the BizTalk Server Administration console are not reflected until you refresh it.</span></span>  
  
 <span data-ttu-id="40a4b-109">El intervalo de actualización de caché de configuración es parte de las propiedades del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="40a4b-109">The configuration cache refresh interval is part of the BizTalk group properties.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="40a4b-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="40a4b-110">Prerequisites</span></span>  
 <span data-ttu-id="40a4b-111">Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="40a4b-111">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-adjust-the-cache-refresh-interval"></a><span data-ttu-id="40a4b-112">Para ajustar el intervalo de actualización de caché</span><span class="sxs-lookup"><span data-stu-id="40a4b-112">To adjust the cache refresh interval</span></span>  
  
1.  <span data-ttu-id="40a4b-113">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="40a4b-113">Click **Start**, click **All Programs**, click **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="40a4b-114">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="40a4b-114">In the console tree, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
3.  <span data-ttu-id="40a4b-115">En el **panel de configuración de BizTalk** cuadro de diálogo, seleccione la **General** ficha. Para el **intervalo de actualización de configuración** propiedad, escriba o seleccione el tiempo (en segundos) que todos los elementos de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] caché de administración debe esperar entre actualizaciones de la caché de configuración y, a continuación, haga clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="40a4b-115">In the **BizTalk Settings Dashboard** dialog box, select the **General** tab. For the **Configuration refresh interval** property, type or select the time (in seconds) that all items in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administration cache must wait between configuration cache refreshes, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="40a4b-116">Entre los elementos que participan en la actualización se incluyen las bases de datos de cuadro de mensajes, las propiedades del servidor, los adaptadores y las conexiones a la base de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="40a4b-116">Items involved in the refresh include the MessageBox databases, server properties, adapters, and connections to the Tracking database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="40a4b-117">De forma predeterminada, todos los objetos en la caché de configuración se actualizarán cada 60 segundos, excepto para las conexiones de base de datos de servidor y las propiedades del servidor.</span><span class="sxs-lookup"><span data-stu-id="40a4b-117">By default, all objects in the configuration cache are refreshed every 60 seconds, except for the server database connections and server properties.</span></span>