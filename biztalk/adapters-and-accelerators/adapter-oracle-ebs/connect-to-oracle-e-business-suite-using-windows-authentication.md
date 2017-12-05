---
title: "Conectarse a Oracle E-Business Suite mediante la autenticación de Windows | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0937dfd9-4a94-4d65-a42c-3c5019eefde2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed71a893ef029e6524b7e71f68626c32f207f91e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="connect-to-oracle-e-business-suite-using-windows-authentication"></a><span data-ttu-id="bc58f-102">Conectarse a Oracle E-Business Suite mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="bc58f-102">Connect to Oracle E-Business Suite using Windows Authentication</span></span>
<span data-ttu-id="bc58f-103">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] permite a los clientes de adaptador utilizar la autenticación de Windows para establecer una conexión con Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="bc58f-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enables adapter clients to use Windows Authentication to establish a connection with the Oracle E-Business Suite.</span></span> <span data-ttu-id="bc58f-104">Para usar la autenticación de Windows los clientes de adaptador deben especificar una "/" para el nombre de usuario y deje la contraseña en blanco.</span><span class="sxs-lookup"><span data-stu-id="bc58f-104">To use Windows Authentication adapter clients must specify a “/” for user name and leave the password blank.</span></span> <span data-ttu-id="bc58f-105">Para obtener más información sobre cómo conectarse a Oracle E-Business Suite mediante la autenticación de Windows, vea [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="bc58f-105">For more information about connecting to the Oracle E-Business Suite using Windows Authentication, see [Connect to the Oracle E-Business Suite in Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).</span></span>  

## <a name="what-you-need-to-know"></a><span data-ttu-id="bc58f-106">Lo que necesita saber</span><span class="sxs-lookup"><span data-stu-id="bc58f-106">What you need to know</span></span>  
 <span data-ttu-id="bc58f-107">Para usar la autenticación de Windows, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc58f-107">To use Windows Authentication, you must do the following:</span></span>  
  
-   <span data-ttu-id="bc58f-108">Si el **ClientCredentialType** propiedad está establecida en **base de datos**, especifique "/" para el nombre de usuario y deje en blanco la contraseña para conectarse a Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="bc58f-108">If the **ClientCredentialType** property is set to **Database**, specify “/” for the user name and leave the password blank to connect to the Oracle E-Business Suite.</span></span>  
  
-   <span data-ttu-id="bc58f-109">Si el **ClientCredentialType** propiedad está establecida en **EBusiness**, especifique las credenciales de Oracle E-Business Suite para conectarse.</span><span class="sxs-lookup"><span data-stu-id="bc58f-109">If the **ClientCredentialType** property is set to **EBusiness**, specify the Oracle E-Business Suite credentials to connect.</span></span> <span data-ttu-id="bc58f-110">Además, debe especificar "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlace de propiedad en blanco.</span><span class="sxs-lookup"><span data-stu-id="bc58f-110">Also, you must specify “/” for the **OracleUserName** binding property and leave the **OraclePassword** binding property blank.</span></span>  

## <a name="enable-windows-authentication"></a><span data-ttu-id="bc58f-111">Habilitar la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="bc58f-111">Enable Windows Authentication</span></span>  
 <span data-ttu-id="bc58f-112">Para permitir que los clientes de adaptador utilizar la autenticación de Windows para conectarse a una base de datos de Oracle, debe realizar las siguientes tareas en el equipo que ejecuta la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bc58f-112">To enable adapter clients to use Windows Authentication to connect to an Oracle database, you must perform the following tasks on the computer running the Oracle database.</span></span>  
  
1.  <span data-ttu-id="bc58f-113">Asegúrese de que el `sqlnet.ora` archivo en el cliente y el servidor, disponible en `ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`, tiene la siguiente entrada:</span><span class="sxs-lookup"><span data-stu-id="bc58f-113">Make sure that the `sqlnet.ora` file on both the client and the server, available under `ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`, has the following entry:</span></span>  
  
    ```  
    SQLNET.AUTHENTICATION_SERVICES= (NTS)  
    ```  
  
2.  <span data-ttu-id="bc58f-114">Conectarse a la base de datos de Oracle como SYSDBA.</span><span class="sxs-lookup"><span data-stu-id="bc58f-114">Connect to the Oracle database as SYSDBA.</span></span>  
  
3.  <span data-ttu-id="bc58f-115">Cree el usuario de Windows como un usuario externo en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bc58f-115">Create the Windows user as an external user in Oracle database.</span></span> <span data-ttu-id="bc58f-116">Tenga en cuenta que el nombre de usuario debe estar en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="bc58f-116">Note that the user name must be in upper case.</span></span>  
  
    ```  
    CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
    ```  
  
4.  <span data-ttu-id="bc58f-117">Conceder privilegios para el usuario.</span><span class="sxs-lookup"><span data-stu-id="bc58f-117">Grant privileges to the user.</span></span>  
  
    ```  
    GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
    ```  
  
5.  <span data-ttu-id="bc58f-118">Los artefactos de Oracle E-Business Suite están disponibles en el esquema de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bc58f-118">The Oracle E-Business Suite artifacts are available under the APPS schema.</span></span> <span data-ttu-id="bc58f-119">Para habilitar al usuario recién creado, inicia sesión con autenticación de Windows, para tener acceso a los artefactos de Oracle E-Business Suite, esquema del usuario debe cambiarse en el esquema de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bc58f-119">To enable the newly created user, logging in using Windows Authentication, to access the Oracle E-Business Suite artifacts, the user’s schema must be changed to the APPS schema.</span></span> <span data-ttu-id="bc58f-120">Puede agregar el siguiente comando SQL a la secuencia de comandos de inicio de sesión que cambia el esquema predeterminado del usuario a las aplicaciones cuando el usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="bc58f-120">You can add the following SQL command to the logon script that changes the user’s default schema to APPS when the user logs on.</span></span>  
  
    ```  
    alter session set current_schema=APPS;  
    ```  
  
6.  <span data-ttu-id="bc58f-121">Aunque se ha cambiado el esquema del usuario al esquema de aplicaciones, todavía no será capaz de ver artefactos de Oracle E-Business Suite mientras navega y generar los metadatos que utilizan el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc58f-121">Even though you changed the schema of the user to APPS schema, you will still not be able to see Oracle E-Business Suite artifacts while browsing and generating metadata using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="bc58f-122">Esto es porque el usuario recién creado no tiene permisos para el esquema de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bc58f-122">This is because the newly created user does not have permissions for the APPS schema.</span></span> <span data-ttu-id="bc58f-123">Asegúrese de que ha proporcionado el permiso para el esquema de aplicaciones para el usuario recién creado.</span><span class="sxs-lookup"><span data-stu-id="bc58f-123">Make sure you provided permission for the APPS schema for the newly created user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc58f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc58f-124">See Also</span></span>  
<span data-ttu-id="bc58f-125">[Configurar al cliente de Oracle para el adaptador de E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="bc58f-125">[Configure the Oracle client for the E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md) </span></span>  
[<span data-ttu-id="bc58f-126">Crear el URI de conexión de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="bc58f-126">Create the Oracle E-Business Suite connection URI</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)  
 [<span data-ttu-id="bc58f-127">Crear una conexión a Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="bc58f-127">Create a connection to Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)