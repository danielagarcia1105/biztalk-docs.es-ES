---
title: 'Lista de comprobación: Supervisión de disponibilidad operativa | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef77ccc2-1d39-4e78-8fea-5c17d05c8174
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfd8b5ead6ceea7154e7f035d16f3c0fba7be1d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021946"
---
# <a name="checklist-monitoring-operational-readiness"></a>Lista de comprobación: Supervisión de preparación operativa
En este tema se enumera los pasos que debe seguir al supervisar una producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  


|                                                                                                                                                                      Pasos                                                                                                                                                                       |                                                                                                  Referencia                                                                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                           Seleccionar e implementar una estrategia de supervisión para la infraestructura y aplicaciones de BizTalk.                                                                                                                           |                                                [Supervisión del entorno de BizTalk Server](../technical-guides/monitoring-the-biztalk-server-environment.md)                                                 |
|                                                                                                                                                            Supervisar el uso de espacio en disco.                                                                                                                                                             |                                                              [Supervisión del uso del espacio en disco](../technical-guides/monitoring-disk-space-usage.md)                                                               |
| Supervisar SQL Server:<br /><br /> -Compruebe que los equipos de alojamiento de SQL Server la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos se están supervisando.<br />-Compruebe que la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajos se están supervisando. |            -   [Supervisión de servidores SQL Server](../technical-guides/monitoring-sql-servers.md)<br />-   [Supervisión de las bases de datos de BizTalk Server](../technical-guides/monitoring-biztalk-server-databases.md)            |
|          Supervisar aplicaciones de BizTalk:<br /><br /> -Modificar las reglas existentes o copiar reglas a un módulo de administración personalizado para supervisar una aplicación personalizada de BizTalk.<br />-Crear acciones para cada regla definida.<br />-Crear procesos iterativos para automatizar las tareas manuales.<br />-Use reglas de umbral para automatizar las tareas manuales.          | -   [Supervisión de aplicaciones e instancias de Host](../technical-guides/monitoring-applications-and-host-instances.md)<br />-   [Supervisión de BizTalk Server2](../technical-guides/monitoring-biztalk-server2.md) |

## <a name="in-this-section"></a>En esta sección  

-   [Supervisión del uso del espacio en disco](../technical-guides/monitoring-disk-space-usage.md)