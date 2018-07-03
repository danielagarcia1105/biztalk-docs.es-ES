---
title: Plan de pruebas de la base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4cf5e1f-a960-4702-a050-a2cdacddcbca
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bce48244f67fd757fae5c2657634274625677850
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996621"
---
# <a name="planning-for-database-testing"></a>Plan de pruebas de la base de datos
Pruebas de carga completa de una solución de BizTalk cifras de forma destacada en el ultimate éxito o fracaso de la solución. Puesto que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] por lo que depende el rendimiento de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, pruebas y optimización de una solución con frecuencia se centra en las pruebas de BizTalk y optimización de los equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que hospedan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]bases de datos.  
  
## <a name="considerations-when-planning-for-database-testing"></a>Consideraciones al plan de pruebas de la base de datos  
 Tenga en cuenta lo siguiente al planear la base de datos de prueba:  
  
1. **Asegúrese de que el entorno de prueba coincida lo máximo posible con el entorno de producción.** Uso de un entorno virtual, como Microsoft Hyper-V Server 2008 para las pruebas unitarias es perfectamente aceptable; Sin embargo, todas las pruebas de carga o esfuerzo deben realizarse en hardware que coincida lo máximo posible con el entorno de producción final.  
  
2. **Planee la medición de rendimiento máximo sostenible y rendimiento de seguimiento sostenible máximo del sistema BizTalk Server**. Rendimiento máximo sostenible se mide como la mayor carga de tráfico de mensajes que el sistema de BizTalk Server puede controlar indefinidamente en producción. Siga los pasos descritos en los siguientes temas de Ayuda de BizTalk Server:  
  
   - [Medir el rendimiento máximo sostenible del motor](http://go.microsoft.com/fwlink/?LinkID=154388) (http://go.microsoft.com/fwlink/?LinkID=154388).  
  
   - [Medir el rendimiento de seguimiento sostenible máximo](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815).  
  
     Estos temas describe la metodología para generar carga en el sistema, los parámetros que se deben medir y recomendaciones generales a seguir cuando se prueba el MST.  
  
3. **Entender las implicaciones de cómo BizTalk Server**  
    **implementa la limitación de host.** El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] algoritmo de limitación de host intenta moderar la carga de trabajo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instancias para garantizar que la carga de trabajo no supera la capacidad de la instancia de host o cualquier nivel inferior alojar instancias de host. El mecanismo de limitación se ajusta automáticamente y son adecuadas para la mayoría de las opciones de configuración predeterminadas [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] escenarios de procesamiento. Sin embargo, debería, tener una buena comprensión del mecanismo de limitación antes de implementar las pruebas de carga o esfuerzo. Para obtener más información, consulte [optimizar recursos uso a través de la limitación de Host](http://go.microsoft.com/fwlink/?LinkId=155770) (<http://go.microsoft.com/fwlink/?LinkId=155770>) en la Ayuda de BizTalk Server.