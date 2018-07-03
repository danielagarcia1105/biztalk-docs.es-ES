---
title: Conectarse a la base de datos de Oracle mediante la autenticación de Windows | Microsoft Docs
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
ms.openlocfilehash: 6c984a62275c58f50b0c360a5f46040a6022b459
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007757"
---
# <a name="connect-to-the-oracle-database-using-windows-authentication"></a>Conectarse a la base de datos de Oracle mediante la autenticación de Windows
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] permite a los clientes del adaptador utilizar autenticación de Windows para establecer una conexión con la base de datos de Oracle. Para usar la autenticación de Windows, deben especificar los clientes del adaptador "/" para el nombre de usuario y deje el valor de contraseña en blanco. Para obtener más información sobre cómo conectarse a la base de datos de Oracle mediante la autenticación de Windows, consulte [conectar con base de datos de Oracle en Visual Studio mediante Consume Adapter Service](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md).  
  
 Para habilitar los clientes del adaptador utilizar la autenticación de Windows para conectarse a una base de datos de Oracle, debe realizar las tareas siguientes en el equipo que ejecuta la base de datos de Oracle.  
  
1. Asegúrese de que el `sqlnet.ora` archivo en el cliente y el servidor, disponible en `ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`, tiene la siguiente entrada:  
  
   ```  
   SQLNET.AUTHENTICATION_SERVICES= (NTS)  
   ```  
  
2. Conéctese a la base de datos de Oracle como SYSDBA.  
  
3. Cree el usuario de Windows como un usuario externo en la base de datos de Oracle. Tenga en cuenta que el nombre de usuario debe estar en mayúsculas.  
  
   ```  
   CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
   ```  
  
4. Conceder privilegios al usuario.  
  
   ```  
   GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
   ```  
  
5. Para permitir que el usuario recién creado, iniciar sesión con autenticación de Windows, para tener acceso a los artefactos de base de datos de Oracle, puede cambiar el esquema del usuario en el esquema SCOTT. Puede agregar el siguiente comando SQL a la secuencia de comandos de inicio de sesión que cambia el esquema predeterminado del usuario a SCOTT cuando el usuario inicia sesión.  
  
   ```  
   alter session set current_schema=SCOTT;  
   ```  
  
6. Aunque se ha cambiado el esquema del usuario en el esquema SCOTT, todavía no será capaz de ver los artefactos de la base de datos de Oracle durante la exploración y la generación de metadatos mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Esto es porque el usuario recién creado no tiene permisos para el esquema SCOTT. Asegúrese de que proporciona permiso para el esquema SCOTT para el usuario recién creado.  
  
## <a name="see-also"></a>Vea también  
 [Configurar al cliente de Oracle para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)   
[Crear una conexión a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)