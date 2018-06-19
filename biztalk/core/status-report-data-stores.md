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
# <a name="status-report-data-stores"></a>Almacenamientos de datos de informes de estado
Los datos de seguimiento de informes de estado se almacenan en la base de datos de importación principal de BAM. Se usa una serie de tablas en esta base de datos para los datos de los mensajes EDI y AS2, incluidas las tablas que empiezan con dbo.bam_AS2, dbo.bam.batching, dbo.bam.InterchangeStatusActivity entre otras. Los datos de estado se almacenan en la importación principal incluso si está deshabilitado el informe de EDI. Sólo tendrá que ver y consultar estos datos en la interfaz de usuario de los informes de estado si está activado el informe de estado  
  
 Si habilita el almacenamiento de datos de mensaje para fines sin repudio, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] almacenará los datos EDI o AS2 en la tabla del contenido de mensaje EDI de la base de datos de seguimiento de BizTalk (BizTalkDTADb). Si habilita el almacenamiento de contenido del mensaje para ver los detalles de la carga (seleccionando la **almacenar carga de mensaje para informes** propiedad de acuerdo en el **propiedades generales** página de la **General** pestaña en el **propiedades del acuerdo de** cuadro de diálogo), [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] también almacenará los conjuntos de transacciones en esta tabla.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archiva y purga los datos de las bases de datos de importación principal de BAM y BizTalkDTADb. Las tablas de las bases de datos se vacían de forma periódica.  
  
> [!NOTE]
>  La importación principal de BAM y las bases de datos DTA DB pueden estar fuera de la sincronización si tienen un intervalo distinto para el archivado.  
  
 Los informes de estado de EDI y AS2 pueden influir en el rendimiento. Para obtener más información, vea "Rendimiento consideraciones para EDI y AS2 informes de estado" en [problemas conocidos relacionados con EDI y AS2 rendimiento](../core/known-issues-with-edi-and-as2-performance.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo se almacenan los datos para informes de estado de AS2 y EDI](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)