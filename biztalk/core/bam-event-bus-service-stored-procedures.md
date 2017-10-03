---
title: Procedimientos almacenados del servicio de Bus de eventos BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stored procedures, Even Bus Service [BAM]
- Event Bus Service [BAM], stored procedures
ms.assetid: 18a7bd40-50ce-44f2-88ae-45a2e3c8d3f4
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f44dce10113b8a3a85b7c1dd177f637933b582ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-event-bus-service-stored-procedures"></a>Procedimientos almacenados del servicio de bus de eventos BAM
Los siguientes procedimientos almacenados se utilizan para administrar el servicio de bus de eventos BAM:  
  
-   Para pausar el servicio de bus de eventos BAM, ejecute el procedimiento almacenado TDDS_BlockTDDS en una transacción de la base de datos de BAM (pero sin confirmar la transacción). Para reanudar el servicio de bus de eventos BAM, confirme la transacción TDDS_BlockTDDS.  
  
-   Para habilitar el servicio de bus de eventos BAM en varios equipos, determine los hosts que se van a utilizar en el proceso de seguimiento y, a continuación, una esos equipos al host de seguimiento.  
  
-   Para configurar un intervalo de latido y un tiempo de espera de sesión, utilice el procedimiento almacenado TDDS_UpdateSettings. solo los miembros del grupo BTS_ADMIN_USERS tienen permiso para ejecutar este procedimiento almacenado.  
  
     El procedimiento almacenado TDDS_UpdateSettings consta de los siguientes parámetros:  
  
    -   @RefreshIntervalint. Definido como superior a 60 segundos.  
  
    -   @SqlCommandTimeoutint. Definido como inferior a RefreshInterval.  
  
    -   @SessionTimeoutint. Definido como superior al doble de RefreshInterval.  
  
    -   @EventLoggingIntervalnvarchar(16). Definido como superior a 60 segundos.  
  
    -   @RetryCountint. Establece en mayor que 60 segundos  
  
    -   @ThreadPerSessionint. Este parámetro es obsoleto.  
  
## <a name="see-also"></a>Vea también  
 [Administración de BAM](../core/managing-bam.md)