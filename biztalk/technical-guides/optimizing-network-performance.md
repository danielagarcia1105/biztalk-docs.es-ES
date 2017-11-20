---
title: Optimizar el rendimiento de red | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6c3985a-48b3-489b-8fe3-3b7bfd0515f9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8225bd082140ac1347bc99a91ea209f9d79a8bab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-network-performance"></a><span data-ttu-id="afd01-102">Optimizar el rendimiento de red</span><span class="sxs-lookup"><span data-stu-id="afd01-102">Optimizing Network Performance</span></span>
<span data-ttu-id="afd01-103">En un entorno de BizTalk Server donde el equipo de BizTalk Server es independiente del equipo de SQL Server, cada mensaje procesado por el servidor BizTalk Server requiere comunicación a través de la red.</span><span class="sxs-lookup"><span data-stu-id="afd01-103">In a BizTalk Server environment where the BizTalk Server computer is separate from the SQL Server computer, each and every message processed by BizTalk Server requires communication over the network.</span></span> <span data-ttu-id="afd01-104">Esta comunicación incluye el tráfico considerable entre el equipo de BizTalk Server y la base de datos de BizTalk MessageBox, la base de datos de administración de BizTalk, las bases de datos BAM y otras bases de datos.</span><span class="sxs-lookup"><span data-stu-id="afd01-104">This communication includes considerable traffic between the BizTalk Server computer and the BizTalk MessageBox database, the BizTalk Management database, the BAM databases, and other databases.</span></span> <span data-ttu-id="afd01-105">En escenarios de carga elevada, esta comunicación, puede dar lugar a que el tráfico de red considerable y puede convertirse en un cuello de botella, especialmente cuando no se han optimizado configuración de red, no hay suficientes tarjetas de interfaz de red se instalan o no hay suficiente ancho de banda es está disponible.</span><span class="sxs-lookup"><span data-stu-id="afd01-105">In high-load scenarios, this communication can result in considerable network traffic and can become a bottleneck, especially when network settings have not been optimized, not enough network interface cards are installed, or insufficient network bandwidth is available.</span></span>  
  
 <span data-ttu-id="afd01-106">En esta sección se ofrece algunas recomendaciones generales para mejorar el rendimiento de la red y describe varias entradas del registro que pueden modificarse para optimizar la pila de red para mitigar la aparición de cuellos de botella en la red.</span><span class="sxs-lookup"><span data-stu-id="afd01-106">This section provides some general recommendations for improving network performance and describes several registry entries that can be modified to optimize the network stack to mitigate the occurrence of bottlenecks on the network.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="afd01-107">Algunas de las recomendaciones de esta sección requieren modificaciones en el registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="afd01-107">Some of the recommendations in this section require modifications to the Windows registry.</span></span> <span data-ttu-id="afd01-108">El uso incorrecto del Editor del Registro podría ocasionar problemas que hicieran necesaria una reinstalación del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="afd01-108">Incorrect use of Registry Editor may cause problems requiring you to reinstall your operating system.</span></span> <span data-ttu-id="afd01-109">Utilice el Editor del Registro bajo su propia responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="afd01-109">Use Registry Editor at your own risk.</span></span> <span data-ttu-id="afd01-110">Para obtener más información acerca de cómo realizar copias de, restaurar y modificar el registro, vea el artículo de Microsoft Knowledge Base [256896, "Windows información del registro para los usuarios avanzados"](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729).</span><span class="sxs-lookup"><span data-stu-id="afd01-110">For more information about how to back up, restore, and modify the registry, see the Microsoft Knowledge Base article [256896, "Windows registry information for advanced users"](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="afd01-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="afd01-111">In This Section</span></span>  
  
-   [<span data-ttu-id="afd01-112">Directrices generales para mejorar el rendimiento de red</span><span class="sxs-lookup"><span data-stu-id="afd01-112">General Guidelines for Improving Network Performance</span></span>](../technical-guides/general-guidelines-for-improving-network-performance.md)  
  
-   [<span data-ttu-id="afd01-113">Configuración que puede modificarse para mejorar el rendimiento de red</span><span class="sxs-lookup"><span data-stu-id="afd01-113">Settings that can be Modified to Improve Network Performance</span></span>](../technical-guides/settings-that-can-be-modified-to-improve-network-performance.md)  
  
## <a name="see-also"></a><span data-ttu-id="afd01-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="afd01-114">See Also</span></span>  
 [<span data-ttu-id="afd01-115">Optimizar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="afd01-115">Optimizing Performance</span></span>](../technical-guides/optimizing-performance.md)