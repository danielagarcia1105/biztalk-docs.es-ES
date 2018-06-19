---
title: Almacenes de datos de informe de estado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6cd40ce8-1ac6-43b4-9cef-7cd045e8893c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da876f1151b641216cf9613f6830ed84049da83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278100"
---
# <a name="status-report-data-stores"></a><span data-ttu-id="76fd2-102">Almacenamientos de datos de informes de estado</span><span class="sxs-lookup"><span data-stu-id="76fd2-102">Status Report Data Stores</span></span>
<span data-ttu-id="76fd2-103">Los datos de seguimiento de informes de estado se almacenan en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="76fd2-103">Status reporting tracking data is stored in the BAM Primary Import database.</span></span> <span data-ttu-id="76fd2-104">Se usa una serie de tablas en esta base de datos para los datos de los mensajes EDI y AS2, incluidas las tablas que empiezan con dbo.bam_AS2, dbo.bam.batching, dbo.bam.InterchangeStatusActivity entre otras.</span><span class="sxs-lookup"><span data-stu-id="76fd2-104">A number of tables in this database are used for EDI and AS2 message data, including tables starting with dbo.bam_AS2, dbo.bam.batching, dbo.bam.InterchangeStatusActivity, and others.</span></span> <span data-ttu-id="76fd2-105">Los datos de estado se almacenan en la importación principal incluso si está deshabilitado el informe de EDI.</span><span class="sxs-lookup"><span data-stu-id="76fd2-105">Status data is stored in the Primary Import even if EDI reporting is disabled.</span></span> <span data-ttu-id="76fd2-106">Sólo tendrá que ver y consultar estos datos en la interfaz de usuario de los informes de estado si está activado el informe de estado</span><span class="sxs-lookup"><span data-stu-id="76fd2-106">You will only be to view and query this data in the status reporting UI if status reporting is activated.</span></span>  
  
 <span data-ttu-id="76fd2-107">Si habilita el almacenamiento de datos de mensaje para fines sin repudio, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] almacenará los datos EDI o AS2 en la tabla del contenido de mensaje EDI de la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="76fd2-107">If you enable storage of message data for non-repudiation purposes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store the EDI and/or AS2 data in the EDI Message Content table of the BizTalk tracking database (BizTalkDTADb).</span></span> <span data-ttu-id="76fd2-108">Si habilita el almacenamiento de contenido del mensaje para ver los detalles de la carga (seleccionando la **almacenar carga de mensaje para informes** propiedad de acuerdo en el **propiedades generales** página de la **General** pestaña en el **propiedades del acuerdo de** cuadro de diálogo), [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] también almacenará los conjuntos de transacciones en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="76fd2-108">If you enable storage of message contents for viewing details of the payload (by selecting the **Store message payload for reporting** agreement property in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box), [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also store the transaction sets in this table.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="76fd2-109"> archiva y purga los datos de las bases de datos de importación principal de BAM y BizTalkDTADb.</span><span class="sxs-lookup"><span data-stu-id="76fd2-109"> archives and purges data from the BAM Primary Import and BizTalkDTADb databases.</span></span> <span data-ttu-id="76fd2-110">Las tablas de las bases de datos se vacían de forma periódica.</span><span class="sxs-lookup"><span data-stu-id="76fd2-110">The tables in the databases are cleaned out according to a regular schedule.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76fd2-111">La importación principal de BAM y las bases de datos DTA DB pueden estar fuera de la sincronización si tienen un intervalo distinto para el archivado.</span><span class="sxs-lookup"><span data-stu-id="76fd2-111">The BAM Primary Import and DTA DB databases could be out of synch if each has a different interval for archiving.</span></span>  
  
 <span data-ttu-id="76fd2-112">Los informes de estado de EDI y AS2 pueden influir en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="76fd2-112">EDI and AS2 status reporting may have an impact upon performance.</span></span> <span data-ttu-id="76fd2-113">Para obtener más información, vea "Rendimiento consideraciones para EDI y AS2 informes de estado" en [problemas conocidos relacionados con EDI y AS2 rendimiento](../core/known-issues-with-edi-and-as2-performance.md).</span><span class="sxs-lookup"><span data-stu-id="76fd2-113">For more information, see "Performance Considerations for EDI and AS2 Status Reporting" in [Known Issues with EDI and AS2 Performance](../core/known-issues-with-edi-and-as2-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76fd2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="76fd2-114">See Also</span></span>  
 [<span data-ttu-id="76fd2-115">Cómo se almacenan los datos para informes de estado de AS2 y EDI</span><span class="sxs-lookup"><span data-stu-id="76fd2-115">How Data Is Stored for EDI and AS2 Status Reports</span></span>](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)