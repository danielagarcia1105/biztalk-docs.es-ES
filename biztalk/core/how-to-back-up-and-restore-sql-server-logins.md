---
title: "Cómo realizar copias de y restaurar inicios de sesión SQL Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 847c3a3d-0d97-415b-893e-4ba173085bae
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54fa6a51a27f82add8a96c613e36f5ed7ce88e87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-and-restore-sql-server-logins"></a><span data-ttu-id="33b86-102">Cómo realizar copias de seguridad y restaurar inicios de sesión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="33b86-102">How to Back Up and Restore SQL Server Logins</span></span>
<span data-ttu-id="33b86-103">Copia de seguridad y restaurar inicios de sesión de SQL Server asociados con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="33b86-103">Back up and restore SQL Server logins associated with BizTalk Server.</span></span>  
  
## <a name="biztalk-server-sql-server-security-logins"></a><span data-ttu-id="33b86-104">Inicios de sesión de seguridad de SQL Server de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="33b86-104">BizTalk Server SQL Server Security Logins</span></span>  
 <span data-ttu-id="33b86-105">Los siguientes inicios de sesión de seguridad de SQL Server están asociados con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="33b86-105">The SQL Server security logins listed below are associated with BizTalk Server.</span></span> <span data-ttu-id="33b86-106">Es posible que tenga inicios de sesión adicionales asociados con las aplicaciones de BizTalk Server que haya creado.</span><span class="sxs-lookup"><span data-stu-id="33b86-106">You may have additional logins associated with the BizTalk Server applications you have created.</span></span> <span data-ttu-id="33b86-107">Debe realizar una copia de seguridad de los inicios de sesión y restaurarlos al mover las bases de datos de BizTalk Server a un nuevo servidor o una nueva instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33b86-107">You need to back up the logins and restore them when moving the BizTalk Server databases to a new server or new instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="33b86-108">Usuarios de aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="33b86-108">BizTalk Application Users</span></span>  
  
-   <span data-ttu-id="33b86-109">Usuarios de hosts aislados de BizTalk</span><span class="sxs-lookup"><span data-stu-id="33b86-109">BizTalk Isolated Host Users</span></span>  
  
-   <span data-ttu-id="33b86-110">Administradores de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="33b86-110">BizTalk Server Administrators</span></span>  
  
-   <span data-ttu-id="33b86-111">Operadores de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="33b86-111">BizTalk Server Operators</span></span>  
  
-   <span data-ttu-id="33b86-112">Administradores de SSO</span><span class="sxs-lookup"><span data-stu-id="33b86-112">SSO Administrators</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="33b86-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="33b86-113">Prerequisites</span></span>  
<span data-ttu-id="33b86-114">Debe ser un miembro de la **administradores** rol de seguridad en el servidor SQL Server donde una copia de seguridad y restaurar los inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="33b86-114">You must be a member of the **Administrators** security role on the SQL Server where you backup and restore the logins.</span></span>  
  
## <a name="back-up-a-login-using-a-script"></a><span data-ttu-id="33b86-115">Copia de seguridad de un inicio de sesión mediante un script</span><span class="sxs-lookup"><span data-stu-id="33b86-115">Back up a login using a script</span></span>  
  
1.  <span data-ttu-id="33b86-116">Abra **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="33b86-116">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="33b86-117">Expanda **seguridad**y expanda la lista de **inicios de sesión**.</span><span class="sxs-lookup"><span data-stu-id="33b86-117">Expand **Security**, and expand the list of **Logins**.</span></span>  
  
3.  <span data-ttu-id="33b86-118">Haga clic en el inicio de sesión que desea crear un script para copia de seguridad y, a continuación, seleccione **secuencia de comandos de inicio de sesión como**.</span><span class="sxs-lookup"><span data-stu-id="33b86-118">Right-click the login you want to create a backup script for, and then select **Script Login as**.</span></span>  
  
4.  <span data-ttu-id="33b86-119">Seleccione **CREATE To**y, a continuación, seleccione uno de **nueva ventana del Editor de consultas**, **archivo**, o **Portapapeles** para seleccionar un destino para la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="33b86-119">Select **CREATE To**, and then select one of **New Query Editor Window**, **File**, or **Clipboard** to select a destination for the script.</span></span> <span data-ttu-id="33b86-120">Normalmente, el destino es un archivo con un **.sql** extensión.</span><span class="sxs-lookup"><span data-stu-id="33b86-120">Typically, the destination is a file with a **.sql** extension.</span></span>  
  
5.  <span data-ttu-id="33b86-121">Repita este procedimiento en el paso 3 para cada inicio de sesión que desee incluir en el script.</span><span class="sxs-lookup"><span data-stu-id="33b86-121">Repeat this procedure from Step 3 for each login you want to script.</span></span> <span data-ttu-id="33b86-122">Consulte la lista de inicios de sesión relacionados con BizTalk Server para determinar qué inicios de sesión debe incluir en el script.</span><span class="sxs-lookup"><span data-stu-id="33b86-122">Refer to the list of BizTalk Server related logins to determine which logins you need to script.</span></span>  
  
## <a name="restore-a-login-from-a-script"></a><span data-ttu-id="33b86-123">Restaurar un inicio de sesión desde un script</span><span class="sxs-lookup"><span data-stu-id="33b86-123">Restore a login from a script</span></span>  
  
1.  <span data-ttu-id="33b86-124">Abra **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="33b86-124">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="33b86-125">En el **archivo** menú, **abiertos** el archivo que contiene el inicio de sesión con scripts.</span><span class="sxs-lookup"><span data-stu-id="33b86-125">On the **File** menu, **Open** the file containing the scripted login.</span></span>  
  
3.  <span data-ttu-id="33b86-126">Ejecute el script para crear el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="33b86-126">Execute the script to create the login.</span></span>