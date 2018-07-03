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
# <a name="connect-to-the-oracle-database-using-windows-authentication"></a><span data-ttu-id="a129b-102">Conectarse a la base de datos de Oracle mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="a129b-102">Connect to the Oracle Database Using Windows Authentication</span></span>
<span data-ttu-id="a129b-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] permite a los clientes del adaptador utilizar autenticación de Windows para establecer una conexión con la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a129b-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] enables adapter clients to use Windows Authentication to establish a connection with the Oracle database.</span></span> <span data-ttu-id="a129b-104">Para usar la autenticación de Windows, deben especificar los clientes del adaptador "/" para el nombre de usuario y deje el valor de contraseña en blanco.</span><span class="sxs-lookup"><span data-stu-id="a129b-104">To use Windows Authentication, the adapter clients must specify “/” for user name and leave the password blank.</span></span> <span data-ttu-id="a129b-105">Para obtener más información sobre cómo conectarse a la base de datos de Oracle mediante la autenticación de Windows, consulte [conectar con base de datos de Oracle en Visual Studio mediante Consume Adapter Service](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md).</span><span class="sxs-lookup"><span data-stu-id="a129b-105">For more information about connecting to the Oracle database using Windows Authentication, see [Connect to Oracle Database in Visual Studio using the Consume Adapter Service](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md).</span></span>  
  
 <span data-ttu-id="a129b-106">Para habilitar los clientes del adaptador utilizar la autenticación de Windows para conectarse a una base de datos de Oracle, debe realizar las tareas siguientes en el equipo que ejecuta la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a129b-106">To enable adapter clients to use Windows Authentication to connect to an Oracle database, you must perform the following tasks on the computer running the Oracle database.</span></span>  
  
1. <span data-ttu-id="a129b-107">Asegúrese de que el `sqlnet.ora` archivo en el cliente y el servidor, disponible en `ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`, tiene la siguiente entrada:</span><span class="sxs-lookup"><span data-stu-id="a129b-107">Make sure that the `sqlnet.ora` file on both the client and the server, available under `ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`, has the following entry:</span></span>  
  
   ```  
   SQLNET.AUTHENTICATION_SERVICES= (NTS)  
   ```  
  
2. <span data-ttu-id="a129b-108">Conéctese a la base de datos de Oracle como SYSDBA.</span><span class="sxs-lookup"><span data-stu-id="a129b-108">Connect to the Oracle database as SYSDBA.</span></span>  
  
3. <span data-ttu-id="a129b-109">Cree el usuario de Windows como un usuario externo en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a129b-109">Create the Windows user as an external user in the Oracle database.</span></span> <span data-ttu-id="a129b-110">Tenga en cuenta que el nombre de usuario debe estar en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="a129b-110">Note that the user name must be in upper case.</span></span>  
  
   ```  
   CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
   ```  
  
4. <span data-ttu-id="a129b-111">Conceder privilegios al usuario.</span><span class="sxs-lookup"><span data-stu-id="a129b-111">Grant privileges to the user.</span></span>  
  
   ```  
   GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
   ```  
  
5. <span data-ttu-id="a129b-112">Para permitir que el usuario recién creado, iniciar sesión con autenticación de Windows, para tener acceso a los artefactos de base de datos de Oracle, puede cambiar el esquema del usuario en el esquema SCOTT.</span><span class="sxs-lookup"><span data-stu-id="a129b-112">To enable the newly created user, logging in using Windows Authentication, to access the Oracle database artifacts, you can change the user’s schema to the SCOTT schema.</span></span> <span data-ttu-id="a129b-113">Puede agregar el siguiente comando SQL a la secuencia de comandos de inicio de sesión que cambia el esquema predeterminado del usuario a SCOTT cuando el usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="a129b-113">You can add the following SQL command to the logon script that changes the user’s default schema to SCOTT when the user logs on.</span></span>  
  
   ```  
   alter session set current_schema=SCOTT;  
   ```  
  
6. <span data-ttu-id="a129b-114">Aunque se ha cambiado el esquema del usuario en el esquema SCOTT, todavía no será capaz de ver los artefactos de la base de datos de Oracle durante la exploración y la generación de metadatos mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a129b-114">Even though you changed the schema of the user to the SCOTT schema, you will still not be able to see the Oracle database artifacts while browsing and generating metadata using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="a129b-115">Esto es porque el usuario recién creado no tiene permisos para el esquema SCOTT.</span><span class="sxs-lookup"><span data-stu-id="a129b-115">This is because the newly created user does not have permissions for the SCOTT schema.</span></span> <span data-ttu-id="a129b-116">Asegúrese de que proporciona permiso para el esquema SCOTT para el usuario recién creado.</span><span class="sxs-lookup"><span data-stu-id="a129b-116">Make sure you provided permission for the SCOTT schema to the newly created user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a129b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a129b-117">See Also</span></span>  
 <span data-ttu-id="a129b-118">[Configurar al cliente de Oracle para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a129b-118">[Configure the Oracle Client for the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md) </span></span>  
[<span data-ttu-id="a129b-119">Crear una conexión a la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="a129b-119">Create a connection to the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)