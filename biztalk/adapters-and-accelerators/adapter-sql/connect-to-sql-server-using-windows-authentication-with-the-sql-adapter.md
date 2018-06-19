---
title: Conectarse a SQL Server mediante la autenticación de Windows con el adaptador de SQL | Documentos de Microsoft
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
ms.openlocfilehash: db7d0cbe07155d09085091d995b524b3058c0bf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222316"
---
# <a name="connect-to-sql-server-using-windows-authentication-with-the-sql-adapter"></a><span data-ttu-id="5f7b9-102">Conectarse a SQL Server mediante la autenticación de Windows con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="5f7b9-102">Connect to SQL Server using Windows Authentication with the SQL adapter</span></span>
<span data-ttu-id="5f7b9-103">El [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] permite a los clientes de adaptador utilizar la autenticación de Windows para establecer una conexión con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-103">The [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] enables adapter clients to use Windows Authentication to establish a connection with SQL Server.</span></span> <span data-ttu-id="5f7b9-104">Para usar la autenticación de Windows, los clientes de adaptador deben escribir un nombre de usuario vacío y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-104">To use Windows Authentication, adapter clients must enter an empty user name and password.</span></span> 

<span data-ttu-id="5f7b9-105">Para conectarse a SQL Server mediante autenticación de Windows en Visual Studio, vea [conectar con SQL Server en Visual Studio usando el complemento Consume Adapter Service](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="5f7b9-105">To connect to SQL Server using Windows Authentication within Visual Studio, see [Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md).</span></span>  
  
 <span data-ttu-id="5f7b9-106">Para habilitar los clientes de adaptador utilizar la autenticación de Windows para conectarse a SQL Server, habilite la autenticación de Windows para el usuario en el equipo que ejecuta SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-106">To enable adapter clients to use Windows Authentication to connect to SQL Server, enable Windows Authentication for the user on the computer running SQL Server.</span></span>  

> [!TIP]
> <span data-ttu-id="5f7b9-107">Si SQL Server Management Studio no está instalado en el servidor SQL Server, puede [descargar SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)e instalarlo.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-107">If SQL Server Management Studio is not installed on your SQL Server, you can [Download SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms), and install it.</span></span> 
 
## <a name="add-the-user-in-sql-server"></a><span data-ttu-id="5f7b9-108">Agregue el usuario en SQL Server</span><span class="sxs-lookup"><span data-stu-id="5f7b9-108">Add the user in SQL Server</span></span>  
  
1.  <span data-ttu-id="5f7b9-109">Abra SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-109">Open SQL Server Management Studio.</span></span> <span data-ttu-id="5f7b9-110">En **conectar al servidor**, seleccione **motor de base de datos**, escriba SQL **nombre del servidor**y escriba las credenciales de administrador para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-110">In **Connect to Server**, select **Database Engine**, enter your SQL **Server name**, and enter administrator credentials to connect to the server.</span></span>  

    <span data-ttu-id="5f7b9-111">Seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-111">Select **Connect**.</span></span>
  
2.  <span data-ttu-id="5f7b9-112">En **Explorador de objetos**, expanda el servidor SQL Server, **seguridad**, haga clic en **inicios de sesión**y, a continuación, seleccione **nuevo inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-112">In **Object Explorer**, expand the SQL Server, expand **Security**, right-click **Logins**, and then select **New Login**.</span></span>  
  
3.  <span data-ttu-id="5f7b9-113">Para el **nombre de inicio de sesión**, escriba el nombre de usuario de Windows en el `domain\username` formato.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-113">For the **Login name**, enter the Windows user name in the `domain\username` format.</span></span>  

    > [!NOTE]
    >* <span data-ttu-id="5f7b9-114">Al utilizar este adaptador con BizTalk, el nombre de inicio de sesión que especifique, es la identidad de la cuenta de la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-114">When using this adapter with BizTalk, then the login name you enter, is the identity of the host instance account.</span></span>  
    >
    >* <span data-ttu-id="5f7b9-115">Al utilizar este adaptador en código. NET, el nombre de inicio de sesión que especifique, es la identidad de ese proceso.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-115">When using this adapter in .NET code, then the login name you enter, is the identity for that process.</span></span>
  
4.  <span data-ttu-id="5f7b9-116">Seleccione **asignación de usuario** (panel izquierdo).</span><span class="sxs-lookup"><span data-stu-id="5f7b9-116">Select **User Mapping** (left pane).</span></span> <span data-ttu-id="5f7b9-117">Seleccione una base de datos para asociar el usuario.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-117">Select a database to associate with the user.</span></span> <span data-ttu-id="5f7b9-118">Un usuario de BizTalk típico debería estar asociado a las bases de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f7b9-118">A typical BizTalk user should be associated with the following databases:</span></span> 

* <span data-ttu-id="5f7b9-119">BizTalkDTADb</span><span class="sxs-lookup"><span data-stu-id="5f7b9-119">BizTalkDTADb</span></span>
* <span data-ttu-id="5f7b9-120">BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="5f7b9-120">BizTalkMgmtDb</span></span>
* <span data-ttu-id="5f7b9-121">BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="5f7b9-121">BizTalkMsgBoxDb</span></span>
* <span data-ttu-id="5f7b9-122">BTAHL7</span><span class="sxs-lookup"><span data-stu-id="5f7b9-122">BTAHL7</span></span>
* <span data-ttu-id="5f7b9-123">SSODB</span><span class="sxs-lookup"><span data-stu-id="5f7b9-123">SSODB</span></span>

5. <span data-ttu-id="5f7b9-124">En el **miembros del rol para la base de datos** cuadro, seleccione **db_owner** para todas las bases de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-124">In the **Database role membership for** box, select **db_owner** for all the BizTalk databases.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="5f7b9-125">[Roles de servidor y base de datos en SQL Server](https://msdn.microsoft.com/library/bb669065.aspx) proporciona buena información acerca de los roles.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-125">[Server and Database Roles in SQL Server](https://msdn.microsoft.com/library/bb669065.aspx) provides good info on the roles.</span></span> 
  
6.  <span data-ttu-id="5f7b9-126">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-126">Select **OK** to save your changes.</span></span>
  
 <span data-ttu-id="5f7b9-127">Después de haber agregado el usuario, el usuario puede conectarse y autenticarse en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], inicio de sesión con un nombre de usuario en blanco y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="5f7b9-127">After you have added the user, the user can connect and authenticate to SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], logging in with a blank username and password.</span></span>  



## <a name="see-also"></a><span data-ttu-id="5f7b9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f7b9-128">See Also</span></span>  
 [<span data-ttu-id="5f7b9-129">Crear una conexión a SQL Server</span><span class="sxs-lookup"><span data-stu-id="5f7b9-129">Create a connection to SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)