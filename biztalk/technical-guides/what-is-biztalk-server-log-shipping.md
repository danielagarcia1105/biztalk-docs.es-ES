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
ms.openlocfilehash: 7735617b0d70aa3c693b1808b07d7670e6137f15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999341"
---
# <a name="what-is-biztalk-server-log-shipping"></a>¿Qué es el trasvase de registros de servidor BizTalk Server?
Procedimientos de recuperación ante desastres de BizTalk Server se basan en BizTalk trasvase de registros. Registro de BizTalk trasvase de registros simplifica la restauración de base de datos en caso de desastre aplicando continuamente las actualizaciones del registro de transacciones a las bases de datos de sitio de recuperación ante desastres.  
  
 Aunque BizTalk trasvase de registros se basa en los principios similares como [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trasvase de registros, [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] del trasvase de registros no es compatible con la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de una copia de seguridad como parte del trabajo del agente de copia de seguridad de BizTalk Server SQL.  
  
## <a name="how-does-biztalk-log-shipping-work"></a>¿Cómo trabajo de trasvase de registros de BizTalk?  
 BizTalk funciones de trasvase de manera similar a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trasvase de registros. La producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo está configurado para realizar copias de seguridad el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos en una ubicación UNC. De forma predeterminada, el trabajo de copia de seguridad del Agente SQL de BizTalk realiza una copia de seguridad completa cada hora y una copia de seguridad de registros cada 15 minutos. El trabajo de copia de seguridad de BizTalk Server implementa la lógica para iniciar automáticamente una copia de seguridad completa si se detecta un error de copia de seguridad.  
  
 Cuando la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se configuran para BizTalk trasvase de registros, los archivos de copia de seguridad creados por la copia de seguridad BizTalk Server el Agente SQL trabajo se restauran en el sitio de recuperación ante desastres cada 15 minutos de forma predeterminada. Los archivos de copia de seguridad se copian a través de la red mediante un comando de restauración de SQL. Se copian los archivos de copia de seguridad completa sólo en las situaciones siguientes:  
  
- Al registro de BizTalk en primer lugar se configura el trasvase de registros  
  
- Cuando se agrega una nueva base de datos para el trabajo de copia de seguridad de BizTalk Server.  
  
- Cuando se produce un error de restauración en el sitio de recuperación ante desastres  
  
  Cada [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia en el sitio de recuperación ante desastres se configura individualmente como parte de BizTalk del trasvase de registros para restaurar las bases de datos hospedadas en una producción [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia de base de datos. Cuando un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia está configurada para que BizTalk Server trasvase de registros y la **BTS registro trasvase de registros restaurar bases de datos** trabajo está habilitado, el **BTS registro trasvase de registros restaurar bases de datos** trabajo se conectará a la Base de datos de administración de BizTalk en la producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.  
  
  Como se ha descrito anteriormente, cuando se configura inicialmente el servidor de destino se restaura la copia de seguridad de base de datos completa al servidor de destino. La mayoría del tiempo solo los registros se restauran cuando el **BTS Log Shipping restaurar las bases de datos** ejecuciones del trabajo.  
  
  Al ver la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias con [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio, las bases de datos se mostrarán en un estado "Cargando". Esto es porque el último registro de un conjunto de copia de seguridad nunca se restaura automáticamente. Una vez que esté disponible, un nuevo registro [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del trasvase de registros restaura la siguiente al último registro. Cuando se produce un evento de recuperación ante desastres y el sitio de recuperación ante desastres se debe poner en línea, se restaura el último registro mediante el comando STOPATMARK para recuperar las bases de datos y las bases de datos ya no se mostrará como si estuviera en un estado "Cargando".