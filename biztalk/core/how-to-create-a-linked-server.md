---
title: Cómo crear un servidor vinculado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- servers, linking for backups
- backing up, linking servers
ms.assetid: 7d4aba3d-77c0-4cdf-8547-71e821ce34a1
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcb954062bb2cb2484a51570109b37341b1c12f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980989"
---
# <a name="how-to-create-a-linked-server"></a>Crear un servidor vinculado
Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una topología distribuida, las bases de datos que pertenecen a un grupo de BizTalk existen en varios servidores [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Debe configurar una conexión de servidor vinculada con cada uno de los servidores remotos para poder realizar una copia de seguridad de todo el entorno BizTalk desde el servidor de administración de BizTalk. Un servidor vinculado es un origen de datos OLE DB que se usa en consultas de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] distribuidas.  
  
 Como parte del proceso de restauración y de copia de seguridad, el trabajo Copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea de forma automática servidores vinculados. No obstante, si resulta necesario, podrá crear servidores vinculados de forma manual mediante este procedimiento.  
  
 También se pueden crear servidores vinculados mediante el *sp_addlinkedserver* procedimiento almacenado. Hay consideraciones de seguridad asociadas con esta operación. Cuando se crea un servidor vinculado mediante sp_addlinkedserver, todos los inicios de sesión locales se asignarán al nuevo servidor vinculado de forma predeterminada. Para controlar el acceso al servidor vinculado, el *sp_droplinkedsvrlogin* se debe usar el procedimiento para quitar la asignación de inicio de sesión global, seguida de *sp_addlinkedsvrlogin* para asignar las cuentas de inicio de sesión deseado a el nuevo servidor vinculado. Al usar sp_addlinkedsvrlogin, se recomienda que establezca el @useself parámetro = TRUE. Esto evita la necesidad de incorporar un nombre de usuario y una contraseña en el script SQL.  

> [!TIP]
> Estos pasos pueden cambiar con el tiempo. Se recomienda que hace referencia a la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] documentación en [crear servidores vinculados](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine).
  
## <a name="prerequisites"></a>Requisitos previos  
  
- Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] **sysadmin** rol fijo de servidor  
  
- Crear una variable local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] inicio de sesión. En los pasos siguientes, esta cuenta se asigna a un inicio de sesión en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] se vinculará a. 
  
## <a name="create-a-linked-server"></a>Crear un servidor vinculado
  
1. Abra **SQL Server Management Studio**, escriba el nombre de la variable local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]y, a continuación, seleccione **Connect**.  
  
2. Expanda **objetos de servidor**, haga clic en **servidores vinculados**y, a continuación, seleccione **nuevo servidor vinculado**.  

   Para ver **objetos de servidor**, conectarse a un on-premises local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. A continuación, **objetos de servidor** debe mostrarse.
  
3. En el **servidor vinculado** texto, escriba el nombre de red completo de la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] desea vincular a.  
  
   > [!NOTE]
   >  Este procedimiento suele referirse al servidor al que se está vinculando como servidor remoto. Se hace así por motivos prácticos, para indicar la relación del servidor vinculado (“remoto”) con el servidor local.  
  
4. En **tipo de servidor**, seleccione **SQL Server**.  
  
5. En el panel izquierdo, seleccione **Seguridad**. 

   En este paso, se asigna la cuenta local creada para el inicio de sesión de servidor remoto. Las opciones son: 
    
   | | | 
   |---|---|
   | **Se realiza mediante el contexto de seguridad actual del inicio de sesión** | En entornos de dominio, los usuarios normalmente se conectan con sus inicios de sesión de dominio. Esta opción puede ser mejor, puesto que el contexto de seguridad de la cuenta de dominio que ha iniciado sesión se asigna a la cuenta local que creó.|
   | **Se establecerán usando este contexto de seguridad** | Cuando los usuarios se conectan al servidor SQL local mediante un inicio de sesión de SQL Server, esta opción puede ser preferible. A continuación, escriba el inicio de sesión y la contraseña de la cuenta en el servidor vinculado. |


6. Seleccione **agregar**y escriba lo siguiente: 

   1. En **inicio de sesión Local**, seleccione la cuenta local que creó. 
   2. Comprobar **Impersonate** si el inicio de sesión local también existe en el servidor remoto. 
   3. Como alternativa, si el inicio de sesión local se asignará a un servidor remoto [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] inicio de sesión, escriba el **usuario remoto** nombre y **contraseña remota** para el inicio de sesión de servidor remoto.  
  
      > [!NOTE]
      >  Para usar la suplantación, la configuración de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y las cuentas de inicio de sesión deben cumplir los requisitos de delegación. Consulte [configurar servidores vinculados para la delegación](https://msdn.microsoft.com/library/ms189580.aspx) para obtener más detalles.  

7. En el panel izquierdo, elija **opciones de servidor**. Establecer el **RPC** y **RPC Out** parámetros **True**y, a continuación, seleccione **Aceptar**. 
 
> [!TIP]
> Para obtener más información y recomendaciones al crear servidores vinculados, includig utilizando el `sp_addlinkedserver` almacenados procedcure, consulte [crear servidores vinculados](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine).

  
## <a name="see-also"></a>Vea también  
 [Información avanzada sobre copias de seguridad y restauración](../core/advanced-information-about-backup-and-restore1.md)