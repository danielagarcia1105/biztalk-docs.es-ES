---
title: Conectarse a Oracle E-Business Suite mediante la autenticación de Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0937dfd9-4a94-4d65-a42c-3c5019eefde2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9563f754fd096efb4ab39192f1a8a21a7e6b2207
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009109"
---
# <a name="connect-to-oracle-e-business-suite-using-windows-authentication"></a>Conectarse a Oracle E-Business Suite mediante la autenticación de Windows
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] permite a los clientes del adaptador utilizar la autenticación de Windows para establecer una conexión con Oracle E-Business Suite. Para usar la autenticación de Windows los clientes del adaptador deben especificar "/" para el nombre de usuario y deje la contraseña en blanco. Para obtener más información sobre cómo conectarse a Oracle E-Business Suite mediante la autenticación de Windows, consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).  

## <a name="what-you-need-to-know"></a>Lo que necesita saber  
 Para usar la autenticación de Windows, haga lo siguiente:  
  
-   Si el **ClientCredentialType** propiedad está establecida en **base de datos**, especifique '/' para el nombre de usuario y la deja en blanco la contraseña para conectarse a Oracle E-Business Suite.  
  
-   Si el **ClientCredentialType** propiedad está establecida en **EBusiness**, especifique las credenciales de Oracle E-Business Suite para conectarse. Además, debe especificar "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlaza la propiedad en blanco.  

## <a name="enable-windows-authentication"></a>Habilitar la autenticación de Windows  
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
  
5. Los artefactos de Oracle E-Business Suite están disponibles en el esquema de las aplicaciones. Para permitir que el usuario recién creado, iniciar sesión con autenticación de Windows, para tener acceso a los artefactos de Oracle E-Business Suite, debe cambiar el esquema del usuario en el esquema de las aplicaciones. Puede agregar el siguiente comando SQL a la secuencia de comandos de inicio de sesión que cambia el esquema predeterminado del usuario a las aplicaciones cuando el usuario inicia sesión.  
  
   ```  
   alter session set current_schema=APPS;  
   ```  
  
6. Aunque se ha cambiado el esquema del usuario al esquema de las aplicaciones, todavía no será capaz de ver los artefactos de Oracle E-Business Suite durante la exploración y la generación de metadatos mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Esto es porque el usuario recién creado no tiene permisos para el esquema de las aplicaciones. Asegúrese de que proporciona permiso para el esquema de aplicaciones para el usuario recién creado.  
  
## <a name="see-also"></a>Vea también  
[Configurar al cliente de Oracle para el adaptador de E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)   
[Crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)  
 [Crear una conexión a Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)