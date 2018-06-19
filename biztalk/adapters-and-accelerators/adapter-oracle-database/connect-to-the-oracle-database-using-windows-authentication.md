---
title: Conectarse a la base de datos de Oracle mediante la autenticación de Windows | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73b42a1b-1105-4278-bf8a-62cf0cffb08f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 840435ce334863a4b76e6ac7da0d8dd64e7d4937
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961946"
---
# <a name="connect-to-the-oracle-database-using-windows-authentication"></a>Conectarse a la base de datos de Oracle mediante la autenticación de Windows
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] permite a los clientes de adaptador utilizar la autenticación de Windows para establecer una conexión con la base de datos de Oracle. Para usar la autenticación de Windows, deben especificar los clientes de adaptador "/" para el nombre de usuario y deje en blanco la contraseña. Para obtener más información sobre cómo conectarse a la base de datos de Oracle mediante la autenticación de Windows, vea [conectar con base de datos de Oracle en Visual Studio mediante el servicio de adaptador](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md).  
  
 Para permitir que los clientes de adaptador utilizar la autenticación de Windows para conectarse a una base de datos de Oracle, debe realizar las siguientes tareas en el equipo que ejecuta la base de datos de Oracle.  
  
1.  Asegúrese de que el `sqlnet.ora` archivo en el cliente y el servidor, disponible en `ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`, tiene la siguiente entrada:  
  
    ```  
    SQLNET.AUTHENTICATION_SERVICES= (NTS)  
    ```  
  
2.  Conectarse a la base de datos de Oracle como SYSDBA.  
  
3.  Cree el usuario de Windows como un usuario externo en la base de datos de Oracle. Tenga en cuenta que el nombre de usuario debe estar en mayúsculas.  
  
    ```  
    CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
    ```  
  
4.  Conceder privilegios para el usuario.  
  
    ```  
    GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
    ```  
  
5.  Para habilitar al usuario recién creado, inicia sesión con autenticación de Windows, para tener acceso a los artefactos de base de datos de Oracle, puede cambiar el esquema del usuario en el esquema SCOTT. Puede agregar el siguiente comando SQL a la secuencia de comandos de inicio de sesión que cambia el esquema predeterminado del usuario a SCOTT cuando el usuario inicia sesión.  
  
    ```  
    alter session set current_schema=SCOTT;  
    ```  
  
6.  Aunque se ha cambiado el esquema del usuario en el esquema SCOTT, todavía no podrá ver los artefactos de base de datos de Oracle durante la exploración y generar los metadatos que utilizan el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Esto es porque el usuario recién creado no tiene permisos para el esquema SCOTT. Asegúrese de que proporciona permiso para el esquema SCOTT para el usuario recién creado.  
  
## <a name="see-also"></a>Vea también  
 [Configurar al cliente de Oracle para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)   
[Crear una conexión a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)