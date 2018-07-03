---
title: Conectarse a SQL Server mediante la autenticación de Windows con el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c54b2a-e056-496f-9f10-f19b6a3ca1a6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa19a836d4465b96b663dd4abc5f89500b37e338
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973645"
---
# <a name="connect-to-sql-server-using-windows-authentication-with-the-sql-adapter"></a>Conectarse a SQL Server mediante la autenticación de Windows con el adaptador de SQL
El [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] permite a los clientes del adaptador utilizar la autenticación de Windows para establecer una conexión con SQL Server. Para usar la autenticación de Windows, los clientes del adaptador deben escribir un nombre de usuario vacío y una contraseña. 

Para conectarse a SQL Server mediante autenticación de Windows en Visual Studio, consulte [conectar con SQL Server en Visual Studio mediante el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md).  
  
 Para habilitar los clientes del adaptador utilizar autenticación de Windows para conectarse a SQL Server, habilite la autenticación de Windows para el usuario en el equipo que ejecuta SQL Server.  

> [!TIP]
> Si no está instalado SQL Server Management Studio en SQL Server, puede [descargar SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)e instalarlo. 
 
## <a name="add-the-user-in-sql-server"></a>Agregue el usuario en SQL Server  
  
1.  Abra SQL Server Management Studio. En **conectar al servidor**, seleccione **motor de base de datos**, escriba SQL **nombre del servidor**y escriba las credenciales de administrador para conectarse al servidor.  

    Seleccione **Conectar**.
  
2.  En **Explorador de objetos**, expanda el servidor SQL Server, expanda **seguridad**, haga clic en **inicios de sesión**y, a continuación, seleccione **nuevo inicio de sesión**.  
  
3.  Para el **nombre de inicio de sesión**, escriba el nombre de usuario de Windows en el `domain\username` formato.  

    > [!NOTE]
    >* Al utilizar este adaptador con BizTalk, el nombre de inicio de sesión especificado, es la identidad de la cuenta de la instancia de host.  
    >
    >* Al utilizar este adaptador en código. NET, el nombre de inicio de sesión especificado, es la identidad de ese proceso.
  
4.  Seleccione **User Mapping** (panel izquierdo). Seleccione una base de datos para asociar el usuario. Un usuario típico de BizTalk debe asociarse con las bases de datos siguientes: 

* BizTalkDTADb
* BizTalkMgmtDb
* BizTalkMsgBoxDb
* BTAHL7
* SSODB

5. En el **pertenencia al rol de la base de datos** cuadro, seleccione **db_owner** para todas las bases de datos de BizTalk.  

    > [!NOTE]
    > [Roles de servidor y base de datos en SQL Server](https://msdn.microsoft.com/library/bb669065.aspx) proporciona buena información sobre los roles. 
  
6. Seleccione **Aceptar** para guardar los cambios.
  
   Después de haber agregado el usuario, el usuario puede conectarse y autenticarse en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], inicio de sesión con un nombre de usuario en blanco y la contraseña.  



## <a name="see-also"></a>Vea también  
 [Crear una conexión a SQL Server](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)