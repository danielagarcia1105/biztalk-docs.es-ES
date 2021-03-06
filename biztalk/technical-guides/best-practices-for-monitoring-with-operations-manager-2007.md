---
title: Procedimientos recomendados para la supervisión con Operations Manager 2007 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a5026c-ef59-498b-9bef-ea0f1c932eae
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d099ba9ea60fd8f553d4eaf2011e93a054f59e68
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018711"
---
# <a name="best-practices-for-monitoring-with-operations-manager-2007"></a>Procedimientos recomendados para la supervisión con Operations Manager 2007
Respetar las prácticas recomendadas descritas en este tema para supervisar de forma eficaz las aplicaciones mediante Operations Manager 2007.  
  
 **Instalar módulos de administración adicionales para una cobertura más completa**  
  
- Para ayudar a garantizar que Operations Manager 2007 supervisa las aplicaciones clave en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, debe instalar los módulos de administración siguientes:  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (obligatorio)  
  
  - Sistema operativo de servidor de Windows (opcional)  
  
  - Clúster de conmutación por error de servidor de Microsoft Windows (si los clústeres son utilizado, opcional)  
  
  - Supervisión de SQL Server  
  
  - Internet Information Services 7  
  
  - Message Queue Server (MSMQ) 5.0 (opcional)  
  
  **Revisar y priorizar las alertas por día**  
  
- Al revisar las alertas y establecer prioridades entre ellas a diario, se contribuye a la resolución de los problemas de una forma oportuna.  
  
  **Compruebe que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se comunica con el servidor de Operations Manager 2007.**  
  
- Si se produce un error de comunicación entre los servidores que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y la infraestructura de supervisión, no recibirá las alertas.  
  
  **Habilitar y deshabilitar las reglas según sea necesario**  
  
- De forma predeterminada, algunas de las reglas en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración están deshabilitadas. Las reglas deshabilitadas son de los siguientes tipos: reglas que necesitan personalización, reglas que se utilizan como plantillas y reglas para la supervisión adicional [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] eventos. Asegúrese de que las reglas pertinentes su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno están habilitadas.  
  
  **Personalización de reglas según sea necesario para su entorno**  
  
- Debería personalizar las reglas del paquete de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para obtener un mejor ajuste a su implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Algunas reglas requieren umbrales de supervisión y los umbrales de tiempo que se definen mejor según específica de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación.  
  
  **Crear reglas adicionales según sea necesario, según las reglas incluidas en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración**  
  
- Las reglas se proporcionan para su uso como plantillas para los artefactos que cree, como [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosts. Debería usar estas reglas de plantilla como referencia al crear reglas de artefactos específicos como:  
  
  -   Reglas de host específico, por ejemplo, supervisión de la cola de host y supervisión de limitación de host  
  
  -   Reglas específicas de cuadro de mensajes  
  
  -   Reglas para componentes adicionales de terceros (por ejemplo, la del adaptador de MQSeries)  
  
  **Todos los supervisar componentes relacionados con el servidor BizTalk Server**  
  
  Los componentes de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluyen entorno que se debe supervisar para asegurarse de que se están ejecutando, pero no está limitado necesariamente a:  
  
- Instancias de host de BizTalk  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Trabajos del agente instalados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- Los servicios personalizados desarrollados para la solución de BizTalk  
  
- Estado de las bases de datos personalizados desarrollados para la solución de BizTalk  
  
- Todas las entradas de registro de eventos personalizado relevantes para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de BizTalk Server con System Center Operations Manager 2007](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)