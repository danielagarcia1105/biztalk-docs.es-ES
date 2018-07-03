---
title: Cómo realizar copias de seguridad de bases de datos personalizadas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom databases
- customizing, custom databases
- backing up, custom databases
ms.assetid: 86bebf3c-968e-4fad-9dab-ced1b04aaac7
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59ddab49315f7d4a194224eb0773a7ea1fa1a314
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998581"
---
# <a name="how-to-back-up-custom-databases"></a>Cómo realizar copias de seguridad de bases de datos personalizadas
Ya que las bases de datos personalizadas no se instalan con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], no se incluyen en la lista predeterminada de bases de datos que deben marcarse y de las que el trabajo de copia de seguridad de BizTalk Server debe realizar una copia de seguridad. Si desea que el trabajo de copia de seguridad de BizTalk realice una copia de seguridad de las bases de datos personalizadas, tendrá que agregar manualmente las bases de datos al trabajo mencionado.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
1. SQL Server debe configurarse para usar el modelo de recuperación completa y garantizar la integridad de los datos en los conjuntos de copias de seguridad de bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  Para obtener más información, consulte [del trasvase de registros](../core/log-shipping.md).  
  
2. Para realizar una copia de seguridad de las bases de datos personalizadas, tendrá que haber iniciado sesión con una cuenta de usuario que tenga acceso a cada una de las bases de datos de las que se va a efectuar una copia de seguridad.  
  
    BizTalk Server incluye una función de SQL Server denominada BTS_BACKUP_USERS para que la cuenta de usuario utilizada para realizar una copia de seguridad de las bases de datos no necesite permisos de administrador del sistema en SQL Server, a excepción del servidor principal que controla el proceso de copia de seguridad.  
  
    Al configurar la cuenta de usuario utilizada para realizar la copia de seguridad de las bases de datos, tenga en cuenta lo siguiente:  
  
   -   Debe crear una cuenta de inicio de sesión de SQL Server para este usuario y asignar este último a la función BTS_BACKUP_USERS de BizTalk en cada uno de los servidores.  
  
   -   Los trabajos de copia de seguridad de BizTalk Server pueden configurarse para ejecutarse bajo una cuenta de usuario diferente de la usada para el servicio Agente SQL Server.  
  
   -   Tendrá que configurar el servicio del Agente SQL Server para que se ejecute en una cuenta de dominio. Si todas las bases de datos se encuentran en el mismo equipo, podrá configurar el Agente SQL Server para que utilice una cuenta local.  
  
### <a name="to-back-up-custom-databases"></a>Para realizar una copia de seguridad de bases de datos personalizadas  
  
1. Genere los objetos en la nueva base de datos:  
  
   - Desplácese al directorio [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema y, a continuación, ejecute Backup_Setup_All_Procs.sql y Backup_Setup_All_Tables.sql en todas las bases de datos personalizadas de las que desee realizar una copia de seguridad. Con ello, se crean la función, la tabla y los procedimientos necesarios, además de efectuarse la asignación de permisos a los procedimientos almacenados.  
  
2. Lleve a cabo la configuración siguiente:  
  
   -   Vincule el servidor SQL Server que aloja la base de datos de administración de BizTalk con el servidor SQL Server que aloja la nueva base de datos. La cuenta utilizada para ejecutar el servicio Agente SQL Server en el servidor SQL Server de administración debe ser una cuenta de dominio asignada a cada uno de los equipos que contiene una base de datos de la que se va a realizar una copia de seguridad. Si las bases de datos se encuentran en el mismo equipo, puede omitir este paso. puesto que se lleva a cabo de forma automática.  
  
   -   Agregue un inicio de sesión en el servidor SQL Server que aloja la nueva base de datos para la cuenta con la que se ejecuta el servicio Agente SQL Server en el servidor SQL Server de administración. Si las bases de datos se encuentran en el mismo equipo, puede omitir este paso.  
  
   -   Agregue un usuario a la nueva base de datos para el inicio de sesión creado en el paso anterior y efectúe su agregación a la función BTS_BACKUP_USERS. Las secuencias de comandos del Paso 1 crean esta función y conceden permisos de ejecución en los procedimientos necesarios.  
  
3. Con el Administrador corporativo de SQL Server o SQL Server Management Studio, en la base de datos de administración de BizTalk (BizTalkMgmtDb), modifique la **adm_OtherBackupDatabases** tabla para incluir una fila para cada una de las bases de datos personalizados.  
  
4. Escriba los nuevos nombres de base de datos y servidor en las columnas correspondientes, tal y como se muestra en la siguiente tabla.  
  
   |columna|Valor|  
   |------------|-----------|  
   |DefaultDatabaseName|Nombre descriptivo de la base de datos personalizada.|  
   |DatabaseName|Nombre de la base de datos personalizada.|  
   |ServerName|Nombre del equipo en el que se ejecuta SQL Server.|  
   |BTSServerName|Nombre del servidor BizTalk Server. Aunque no se utilice, debe contener un valor.|  
  
   La próxima vez que ejecute el trabajo de copia de seguridad de BizTalk Server, éste realizará una copia de seguridad de las bases de datos personalizadas.  
  
## <a name="see-also"></a>Vea también  
 [Copia de seguridad y restaurar bases de datos de BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [Información avanzada sobre copias de seguridad y restauración](../core/advanced-information-about-backup-and-restore1.md)