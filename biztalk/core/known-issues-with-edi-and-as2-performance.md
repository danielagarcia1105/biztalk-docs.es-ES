---
title: Problemas conocidos con EDI y AS2 rendimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c47294f9-f728-4b6b-abe1-578434eb54df
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e034cf228ee92157c4b29c36660111bb1856c358
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261764"
---
# <a name="known-issues-with-edi-and-as2-performance"></a><span data-ttu-id="c7ef9-102">Problemas conocidos de rendimiento de EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="c7ef9-102">Known Issues with EDI and AS2 Performance</span></span>
<span data-ttu-id="c7ef9-103">Este tema describe problemas conocidos con el rendimiento de las soluciones EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7ef9-103">This topic describes known issues with the performance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 solutions.</span></span>  
  
## <a name="performance-considerations-for-edi-and-as2-status-reporting"></a><span data-ttu-id="c7ef9-104">Consideraciones de rendimiento relacionadas con informes de estado de EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="c7ef9-104">Performance Considerations for EDI and AS2 Status Reporting</span></span>  
 <span data-ttu-id="c7ef9-105">Al activar los informes de estado de EDI o AS2, el rendimiento del sistema puede verse afectado por el número de mensajes que generan los informes de estado.</span><span class="sxs-lookup"><span data-stu-id="c7ef9-105">When you activate EDI or AS2 status reporting, the performance of your system may be affected by the number of messages that status reporting is performed for.</span></span> <span data-ttu-id="c7ef9-106">Al seleccionar la propiedad "Almacenar carga y conjunto de transacciones para el informe" para el procesamiento de EDI o AS2, el tamaño de los mensajes que generan los informes de estado puede afectar al rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="c7ef9-106">When you select the "Store transaction set/payload for reporting" property for either EDI or AS2 processing, the performance of your system may be affected by the size of the messages that status reporting is performed for.</span></span>  
  
 <span data-ttu-id="c7ef9-107">Las tablas usadas en la base de datos BAMPrimaryImport para los informes de estado de EDI o AS2 se optimizan.</span><span class="sxs-lookup"><span data-stu-id="c7ef9-107">The tables used in the BAMPrimaryImport database for EDI or AS2 status reporting are optimized.</span></span> <span data-ttu-id="c7ef9-108">No es necesaria ninguna optimización adicional.</span><span class="sxs-lookup"><span data-stu-id="c7ef9-108">No further optimization is required.</span></span> <span data-ttu-id="c7ef9-109">Sin embargo, puede aumentar la velocidad a la que se archivan los datos de la base de datos de importación principal BAM cambiando el intervalo correspondiente a los datos de instancia de actividad de archivo en la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="c7ef9-109">You can, however, increase the rate at which data from the BAM primary import database is archived by changing the time window for archiving activity instance data in the BAMPrimaryImport database.</span></span> <span data-ttu-id="c7ef9-110">Para obtener más información, consulte "Archivar datos de la base de datos de importación principal" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7ef9-110">For more information, see "Archiving Primary Import Database Data" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="c7ef9-111">Los datos del conjunto de transacciones y la carga se almacenan en la base de datos BizTalkDTADb.</span><span class="sxs-lookup"><span data-stu-id="c7ef9-111">Transaction set/payload data is stored in the BizTalkDTADb database.</span></span> <span data-ttu-id="c7ef9-112">Para obtener más información sobre el rendimiento de esta base de datos, consulte "Comprender el comportamiento del rendimiento de seguimiento de DTA" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7ef9-112">For more information about the performance of this database, see "Understanding DTA Tracking Performance Behavior" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="c7ef9-113">El rendimiento del sistema también puede verse afectado por el nivel de los informes de estado habilitado en la configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="c7ef9-113">Performance of your system may also be affected by the degree of status reporting enabled in the configuration of your system.</span></span> <span data-ttu-id="c7ef9-114">Para mejorar el rendimiento, es posible deshabilitar un tipo específico de informes de estado.</span><span class="sxs-lookup"><span data-stu-id="c7ef9-114">You may be able to improve performance by disabling a specific type of status reporting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ef9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7ef9-115">See Also</span></span>  
 [<span data-ttu-id="c7ef9-116">Solución de problemas de soluciones EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="c7ef9-116">Troubleshooting EDI and AS2 Solutions</span></span>](../core/troubleshooting-edi-and-as2-solutions.md)