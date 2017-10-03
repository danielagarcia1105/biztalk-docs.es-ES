---
title: Plan de pruebas de la base de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4cf5e1f-a960-4702-a050-a2cdacddcbca
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c0f9b54c866b3ab3d1eebc56bb815284ba3d7c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-database-testing"></a>Plan de pruebas de la base de datos
Pruebas de carga completa de una solución de BizTalk cifras de forma destacada en el último éxito o fracaso de la solución. Puesto que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es por lo que influye en el rendimiento de rendimiento de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, pruebas y optimización de una solución con frecuencia se centra en las pruebas de BizTalk y optimización de los equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que alojar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]bases de datos.  
  
## <a name="considerations-when-planning-for-database-testing"></a>Consideraciones al plan de pruebas de la base de datos  
 Tenga en cuenta lo siguiente al plan de pruebas de la base de datos:  
  
1.  **Asegúrese de que el entorno de prueba coincide con el entorno de producción lo más fielmente posible.** El uso de un entorno virtual, como Microsoft Hyper-V Server 2008 para las pruebas unitarias es absolutamente aceptable; Sin embargo, todas las pruebas de carga o esfuerzo deberían realizarse con hardware que coincida con el entorno de producción final lo más fielmente posible.  
  
2.  **Planear medir el rendimiento máximo sostenible y rendimiento de seguimiento sostenible máximo del sistema BizTalk Server**. Rendimiento máximo sostenible se mide como la mayor carga de tráfico de mensajes que el sistema de BizTalk Server puede controlar indefinidamente en producción. Siga los pasos descritos en los temas siguientes en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda:  
  
    -   [Medir el rendimiento máximo sostenible del motor](http://go.microsoft.com/fwlink/?LinkID=154388) (http://go.microsoft.com/fwlink/?LinkID=154388).  
  
    -   [Medir el rendimiento de seguimiento sostenible máximo](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815).  
  
     Estos temas describe la metodología para generar carga en el sistema, los parámetros que deben medirse y recomendaciones generales que deben seguirse al probar el rendimiento máximo Sostenible.  
  
3.  **Entender las implicaciones de cómo BizTalk Server**  
     **implementa la limitación de host.** El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] algoritmo de limitación de host intenta moderado la carga de trabajo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instancias para asegurarse de que la carga de trabajo no supera la capacidad de la instancia de host o cualquier host en un nivel inferior instancias de host. El mecanismo de limitación se ajusta automáticamente y son adecuadas para la mayoría de las opciones de configuración predeterminadas [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] escenarios de procesamiento. Sin embargo, debe, tener un buen conocimiento del mecanismo de limitación antes de implementar las pruebas de carga y esfuerzo. Para obtener más información, consulte [optimizar recursos a través de Host de límite de uso](http://go.microsoft.com/fwlink/?LinkId=155770) (http://go.microsoft.com/fwlink/?LinkId=155770) en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda.