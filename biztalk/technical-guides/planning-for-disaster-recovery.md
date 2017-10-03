---
title: "Planear la recuperación ante desastres de | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a33e8875-cfde-4a60-9dab-fc6bb3ac4f1c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f342030cd016dc0b1ea015a463e8777d498f860
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-disaster-recovery"></a>Planear la recuperación de un desastre
Este tema proporciona instrucciones para los equipos de la aplicación para los requisitos de recuperación ante desastres y los procedimientos para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]. Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] almacena información de configuración y el procesamiento en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]alta disponibilidad y recuperación ante desastres se logra a través de las capacidades de recuperación de desastres y la disponibilidad alta de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
 Un grupo de BizTalk se define mediante un conjunto de bases de datos hospedadas en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. El conjunto de bases de datos hospedadas en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] puede estar muy disponible mediante el uso de un clúster de Windows Server. En un entorno de BizTalk, los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporcionar el entorno de tiempo de ejecución de"" y las bases de datos en los equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] proporcionan el almacén persistente para el entorno. Por lo tanto, [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] procedimientos de recuperación ante desastres, restauración y copia de seguridad muy se centran en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
## <a name="purpose"></a>Finalidad  
 En este tema consolida [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] información de recuperación ante desastres de la documentación principal, varios sitios Web de Microsoft e información de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo del producto para definir los procedimientos de recuperación ante desastres de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos.  
  
 Los equipos de la aplicación deben probar exhaustivamente los procedimientos de recuperación ante desastres, restauración y copia de seguridad. También debe asegurarse de que los procedimientos se han adaptado para cumplir los requisitos de la aplicación antes de entrar en producción.  
  
## <a name="scope"></a>Ámbito  
 En esta sección se centra en los procedimientos de recuperación ante desastres de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] y relacionados con los procedimientos para [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Esta guía se basa en la documentación relacionada acerca de cómo realizar copias de y restaurar el servidor BizTalk Server.  
  
 Para obtener más información sobre la copia de seguridad y restauración, vea esta documentación y vea [copia de seguridad y restauración de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071) en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda. Cada equipo de la aplicación debe aumentar la información de este tema con procedimientos adicionales específicos para su entorno, como los nombres de equipo de documento, letras de unidad, y relacionados con la configuración del clúster, así como procedimientos de recuperación ante desastres de en las aplicaciones de BizTalk no forman parte de la solución.  
  
 En este tema no proporciona ante desastres detallada procedimientos de recuperación para las siguientes áreas:  
  
-   Aplicaciones no son de BizTalk  
  
-   Código fuente de aplicación  
  
-   Certificados  
  
-   Operaciones de aplicación  
  
 Puede haber otras áreas que requieren la documentación en el plan de recuperación ante desastres de una aplicación no aparece por encima de la que se debe dirigir cada equipo de la aplicación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Prácticas recomendadas para la recuperación ante desastres](../technical-guides/best-practices-for-disaster-recovery.md)  
  
-   [¿Qué es el trasvase de registros de servidor BizTalk Server?](../technical-guides/what-is-biztalk-server-log-shipping.md)