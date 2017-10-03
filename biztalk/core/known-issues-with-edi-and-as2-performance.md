---
title: Problemas conocidos con EDI y AS2 rendimiento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c47294f9-f728-4b6b-abe1-578434eb54df
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e034cf228ee92157c4b29c36660111bb1856c358
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-and-as2-performance"></a>Problemas conocidos de rendimiento de EDI y AS2
Este tema describe problemas conocidos con el rendimiento de las soluciones EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="performance-considerations-for-edi-and-as2-status-reporting"></a>Consideraciones de rendimiento relacionadas con informes de estado de EDI y AS2  
 Al activar los informes de estado de EDI o AS2, el rendimiento del sistema puede verse afectado por el número de mensajes que generan los informes de estado. Al seleccionar la propiedad "Almacenar carga y conjunto de transacciones para el informe" para el procesamiento de EDI o AS2, el tamaño de los mensajes que generan los informes de estado puede afectar al rendimiento del sistema.  
  
 Las tablas usadas en la base de datos BAMPrimaryImport para los informes de estado de EDI o AS2 se optimizan. No es necesaria ninguna optimización adicional. Sin embargo, puede aumentar la velocidad a la que se archivan los datos de la base de datos de importación principal BAM cambiando el intervalo correspondiente a los datos de instancia de actividad de archivo en la base de datos BAMPrimaryImport. Para obtener más información, consulte "Archivar datos de la base de datos de importación principal" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Los datos del conjunto de transacciones y la carga se almacenan en la base de datos BizTalkDTADb. Para obtener más información sobre el rendimiento de esta base de datos, consulte "Comprender el comportamiento del rendimiento de seguimiento de DTA" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 El rendimiento del sistema también puede verse afectado por el nivel de los informes de estado habilitado en la configuración del sistema. Para mejorar el rendimiento, es posible deshabilitar un tipo específico de informes de estado.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de soluciones EDI y AS2](../core/troubleshooting-edi-and-as2-solutions.md)