---
title: "Lista de comprobación: Realización de comprobaciones de mantenimiento diario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1abae6fb-abce-4f23-a07d-b32ba58cd070
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 281f33f0d880fdd217f3cac303526d7cfc0802f7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="checklist-performing-daily-maintenance-checks"></a>Lista de comprobación: Realización de comprobaciones de mantenimiento diario
En este tema se describe algunos de los elementos que se deben comprobar diariamente para ayudar a supervisar el estado de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema. Debe realizar la mayor parte de estas comprobaciones de forma coherente y archivar los resultados durante un período de tiempo para obtener la mayor ventaja. Se recomienda que automaticen las comprobaciones de mantenimiento rutinarias siempre que sea posible.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Compruebe si los discos con errores en el hardware de RAID (comprobación de confiabilidad).|[Administrar discos](http://go.microsoft.com/fwlink/?LinkId=158666) (http://go.microsoft.com/fwlink/?LinkId=158666).|  
|Comprobar si hay mensajes que requieren intervención manual como mensajes suspendidos (comprobación de confiabilidad).|Para obtener información acerca de cómo comprobar manualmente los mensajes suspendidos, consulte [investigando orquestación, puerto y errores de mensaje](http://go.microsoft.com/fwlink/?LinkId=154512) (http://go.microsoft.com/fwlink/?LinkId=154512).|  
|Busque los errores o problemas con las distintas bases de datos asociados con BizTalk Server, especialmente la base de datos de cuadro de mensajes.|Ejecutar la herramienta de BizTalk MsgBoxViewer disponible en [BizTalk MsgBoxViewer - aquí descargar la versión más reciente de la herramienta](http://go.microsoft.com/fwlink/?LinkId=151930) (http://go.microsoft.com/fwlink/?LinkId=151930). Esta herramienta analiza BizTalk MessageBox y otras bases de datos y genera un informe HTML que contiene advertencias, si existe y otra información relacionada con las bases de datos. **Sugerencia:** también puede guardar los informes para su uso posterior. Estos informes pueden ser útiles al solucionar problemas relacionados con la aplicación de BizTalk. **Nota:** no se admite el uso de esta herramienta por Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.|  
|Resolver los problemas, si existe, identificado por la herramienta de BizTalk MsgBoxViewer.|Ejecutar la herramienta de terminador disponible en [terminador](http://go.microsoft.com/fwlink/?LinkId=151931) (http://go.microsoft.com/fwlink/?LinkId=151931). Esta herramienta permite a los usuarios a resolver fácilmente los problemas identificados por la herramienta de BizTalk MsgBoxViewer. Para obtener más información acerca de cómo la herramienta de terminador se integra con la herramienta de BizTalk MsgBoxViewer, consulte [utilizando el terminador de BizTalk para resolver los problemas identificados por BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932). **Nota:** no se admite el uso de esta herramienta por Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.|  
|Compruebe los registros de eventos de errores y advertencias (comprobación de administración).|Eventos de advertencia y errores de BizTalk Server se guardan en el registro de aplicación. El origen del evento es "BizTalk Server".|  
  
## <a name="see-also"></a>Vea también  
 [Mantenimiento de la confiabilidad](../technical-guides/maintaining-reliability.md)   
 [Supervisión de BizTalk Server2](../technical-guides/monitoring-biztalk-server2.md)