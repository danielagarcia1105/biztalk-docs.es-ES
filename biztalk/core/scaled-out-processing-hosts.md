---
title: Hosts de procesamiento escalado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- high availability
- hosts, processing
- hosts, high availability
- scaling, hosts
- hosts, planning
- hosts, scaling
- clustering
ms.assetid: c72ce8fc-7593-4700-8398-23d1a20515c3
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ee36777a5c64713fd31e86fe6ef2a1886b3348
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269332"
---
# <a name="scaled-out-processing-hosts"></a>Hosts de procesamiento escalados horizontalmente
Un host de procesamiento escalado horizontalmente mejora el rendimiento y proporciona alta disponibilidad aislando la funcionalidad de orquestación en dos o más equipos host. Este aislamiento permite agregar varios equipos a un host de procesamiento para obtener redundancia. Un host de procesamiento en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecuta uno o más host instancias que coordenadas procesos empresariales distintos y crea una instancia de objetos de programación para orquestaciones.  
  
 La siguiente ilustración muestra una implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que proporciona alta disponibilidad para el host de procesamiento a través de dos equipos que ejecutan instancias del host de procesamiento. Tenga en cuenta que, en esta ilustración, los hosts de envío y recepción no tienen una alta disponibilidad.  
  
 ![Host de procesamiento ampliado](../core/media/tdi-ha-scaleprocess.gif "TDI_HA_ScaleProcess")  
  
 En esta configuración, el trabajo de procesamiento de orquestaciones tiene una carga equilibrada entre dos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos que tienen instancias del host de procesamiento y ejecutan independientemente entre sí. Si un equipo encuentra errores o deja de funcionar, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza automáticamente la instancia de host en el otro equipo para procesar las orquestaciones restantes.  
  
## <a name="maintaining-orchestration-state"></a>Mantener el estado de las orquestaciones  
 BizTalk Server mantiene el estado de la orquestación forma centralizada en Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]y no de forma local en cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo. Al guardar el estado en la base de datos de cuadro de mensajes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] supera la limitación de basarse en una instancia de host único procesamiento para procesar la orquestación y permite que cualquier instancia de host de procesamiento procese la orquestación. Si se produce un error mientras [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa una orquestación, otra instancia del mismo host de procesamiento puede completar la orquestación desde el último estado persistente.  
  
## <a name="see-also"></a>Vea también  
 [Proporcionar alta disponibilidad a hosts de BizTalk](../core/providing-high-availability-for-biztalk-hosts.md)