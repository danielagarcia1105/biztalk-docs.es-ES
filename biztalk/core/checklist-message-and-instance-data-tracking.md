---
title: 'Lista de comprobación: Del mensaje y seguimiento de datos de la instancia | Microsoft Docs'
description: Procedimientos recomendados al realizar el seguimiento de mensajes, las instancias y los artefactos de BizTalk Server
ms.custom: ''
ms.date: 02/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4b5b614-23e5-4895-9c66-417b55dee43c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 353f3669f79bb7481dd5588105dab59e83b011ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984957"
---
# <a name="checklist-message-and-instance-data-tracking"></a>Lista de comprobación: Mensaje y seguimiento de datos de instancia

|Paso|Referencia|  
|----------|---------------|  
|Revise los datos de instancia de mensaje y servicio de seguimiento de las consideraciones de seguridad|[Consideraciones de seguridad para el seguimiento de datos de instancias y mensajes](../core/security-considerations-for-message-and-instance-data-tracking.md)|  
|Revise los datos de instancia de mensaje y servicio de seguimiento de los procedimientos recomendados|[Procedimientos recomendados para el seguimiento de datos de instancias y mensajes](../core/best-practices-for-message-and-instance-data-tracking.md)|  
|Asegúrese de que el servicio Agente SQL Server se ejecuta en todas las bases de datos de cuadro de mensajes.|El Agente SQL Server hace que los cuerpos de mensaje estén disponibles para el seguimiento y WMI, y permite ejecutar trabajos para limpiar las bases de datos de cuadro de mensajes.<br /><br /> Para obtener más información acerca del Agente SQL Server y del servicio Agente SQL Server, vea los Libros en pantalla de SQL Server.|  
|Configurar el seguimiento de los artefactos en la consola de administración de BizTalk Server|[El seguimiento de orquestaciones](how-to-configure-tracking-for-an-orchestration.md)<br/>[Seguimiento del puerto de envío](how-to-configure-tracking-for-a-send-port.md)<br/>[Seguimiento del puerto de recepción](how-to-configure-tracking-for-a-receive-port.md)<br/>[Directiva de seguimiento](how-to-configure-tracking-for-a-policy.md)<br/>[Esquema de seguimiento](how-to-configure-tracking-for-a-schema.md)<br/>[Seguimiento de canalizaciones](how-to-configure-tracking-for-a-pipeline.md)|  

## <a name="see-also"></a>Vea también  
 [Procedimientos recomendados para el seguimiento de datos de instancias y mensajes](../core/best-practices-for-message-and-instance-data-tracking.md)
