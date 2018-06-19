---
title: ¿Qué es el trasvase de registros de servidor BizTalk Server? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79a2088a-ff36-4590-97c9-51d5bb245486
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3b20589229b1e3868f23c3823d2a26decc56081
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010501"
---
# <a name="what-is-biztalk-server-log-shipping"></a>¿Qué es el trasvase de registros de servidor BizTalk Server?
Procedimientos de recuperación ante desastres de BizTalk Server se basan en BizTalk trasvase de registros. Registro de BizTalk envío simplifica la restauración de base de datos si se produce un desastre aplicando continuamente las actualizaciones del registro de transacciones para las bases de datos de sitio de recuperación ante desastres.  
  
 Mientras que BizTalk trasvase de registros se basa en los principios similares como [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] envío, de registro [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trasvase de registros no es compatible con la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de copia de seguridad como parte del trabajo del agente de copia de seguridad de BizTalk Server SQL.  
  
## <a name="how-does-biztalk-log-shipping-work"></a>¿Cómo trabajo de trasvase de registros de BizTalk?  
 BizTalk trasvase de registros funciones en una forma parecida a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trasvase de registros. Los entornos de producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo está configurado para realizar una copia de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos a una ubicación UNC. De forma predeterminada, el trabajo del agente de SQL de BizTalk copia de seguridad realiza una copia de seguridad completa cada hora y una copia de seguridad de registros cada 15 minutos. El trabajo de copia de seguridad de BizTalk Server implementa la lógica para iniciar automáticamente una copia de seguridad completa si se detecta un error de copia de seguridad.  
  
 Cuando la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se configuran para BizTalk trasvase de registros, los archivos de copia de seguridad creados por la copia de seguridad SQL de agente de servidor de BizTalk trabajo se restauran en el sitio de recuperación ante desastres cada 15 minutos de forma predeterminada. Se copian los archivos de copia de seguridad a través de la red por un comando de restauración de SQL. Archivos de copia de seguridad completa se copian solo en las situaciones siguientes:  
  
-   Cuando inicie sesión BizTalk envío se configura primero  
  
-   Cuando se agrega una nueva base de datos para el trabajo de copia de seguridad de BizTalk Server.  
  
-   Cuando se produce un error de restauración en el sitio de recuperación ante desastres  
  
 Cada [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en el sitio de recuperación ante desastres se configura individualmente como parte del trasvase de registros de BizTalk para restaurar bases de datos hospedadas en uno de producción [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia de base de datos. Cuando un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia se configura para que BizTalk Server trasvase de registros y la **BTS registro envío restaurar bases de datos** trabajo está habilitado, el **BTS registro envío restaurar bases de datos** trabajo se conectará a la Base de datos de administración de BizTalk en la producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.  
  
 Como se describió anteriormente, cuando el servidor de destino se configura primero la copia de seguridad completa de la base de datos se restaura en el servidor de destino. La mayoría de las veces que se restauran solo los registros cuando el **bases de datos con restauración de trasvase de registros de BTS** ejecuciones del trabajo.  
  
 Al ver la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias con [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio, las bases de datos se mostrarán en un estado "Cargando". Esto es porque el último registro de un conjunto de copia de seguridad nunca se restaura automáticamente. Una vez que hay un nuevo registro [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros restaura la siguiente al último registro. Cuando se produce un evento de recuperación ante desastres y el sitio de recuperación ante desastres se debe poner en línea, se restaura el último registro utilizando el comando STOPATMARK para recuperar las bases de datos y las bases de datos ya no se mostrará como perteneciente a un estado "Cargando".