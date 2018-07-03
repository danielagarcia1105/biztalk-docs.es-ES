---
title: Cómo agregar cuentas a una vista | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], security
- Add-Account command [BAM]
- managing [BAM], adding accounts to views
ms.assetid: 0875796c-82a4-4165-9bed-88e8ba466548
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39d1d6b29c7f0b2b7704d6634b49b93a0aede738
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985445"
---
# <a name="how-to-add-accounts-to-a-view"></a><span data-ttu-id="f5390-102">Cómo agregar cuentas a una vista</span><span class="sxs-lookup"><span data-stu-id="f5390-102">How to Add Accounts to a View</span></span>
<span data-ttu-id="f5390-103">Los administradores utilizan el **Agregar cuenta** comando para asociar usuarios a vistas de BAM y proteger las vistas de hojas de cálculo de Excel de BAM de accesos no autorizados.</span><span class="sxs-lookup"><span data-stu-id="f5390-103">Administrators use the **add-account** command to associate users with BAM views and protect BAM Excel Spreadsheet views from unauthorized access.</span></span> <span data-ttu-id="f5390-104">Cuando los usuarios guardan vistas de BAM, estas vistas hacen referencia a una cadena de conexión de SQL oculta en el libro.</span><span class="sxs-lookup"><span data-stu-id="f5390-104">When users save BAM views, the views reference a SQL connection string that is hidden within the workbook.</span></span> <span data-ttu-id="f5390-105">El libro está protegido, pero debe asegurarse de que el documento también esté protegido.</span><span class="sxs-lookup"><span data-stu-id="f5390-105">The workbook is protected, but you must ensure that the document is protected.</span></span>  
  
 <span data-ttu-id="f5390-106">Cuando se asocian usuarios a vistas de BAM, se limita el acceso a las vistas sólo a los usuarios o grupos a los que se concede acceso.</span><span class="sxs-lookup"><span data-stu-id="f5390-106">When you associate users with BAM views, you restrict access to the views to only the users or groups to whom you grant access.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5390-107">Si usa agregaciones en tiempo real (ATR), los usuarios agregados con **Agregar cuenta** no se concede automáticamente derechos de inicio de sesión en el equipo que ejecuta SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f5390-107">If you are using real-time aggregations (RTAs), users added with **add-account** are not automatically granted logon rights to the computer running SQL Server.</span></span> <span data-ttu-id="f5390-108">Si está utilizando ATR, considere la posibilidad de establecer un grupo de usuarios de Windows que contenga todos los usuarios que necesitan tener acceso a las vistas de las ATR.</span><span class="sxs-lookup"><span data-stu-id="f5390-108">If you are using RTAs, consider establishing a Windows user group that contains all of the users that need to see views of the RTAs.</span></span> <span data-ttu-id="f5390-109">Conceda a ese grupo derechos explícitos de inicio de sesión en el servidor SQL Server en el que resida la base de datos de importación principal.</span><span class="sxs-lookup"><span data-stu-id="f5390-109">Grant that group explicit SQL Server logon rights on the SQL server hosting the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="f5390-110">Para obtener información acerca de cómo ver las vistas de BAM, consulte [cómo enumerar vistas de BAM](../core/how-to-list-bam-views.md).</span><span class="sxs-lookup"><span data-stu-id="f5390-110">For information about viewing BAM views, see [How to List BAM Views](../core/how-to-list-bam-views.md).</span></span>  
  
### <a name="to-add-an-account-to-a-view"></a><span data-ttu-id="f5390-111">Para agregar una cuenta a una vista</span><span class="sxs-lookup"><span data-stu-id="f5390-111">To add an account to a view</span></span>  
  
1. <span data-ttu-id="f5390-112">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f5390-112">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="f5390-113">Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f5390-113">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="f5390-114">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f5390-114">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="f5390-115">Tipo **bm agregar-account - AccountName:\<nombreCuenta\> -View:\<nombre de la vista\>**.</span><span class="sxs-lookup"><span data-stu-id="f5390-115">Type **bm add-account -AccountName:\<account name\> -View:\<view name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f5390-116">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="f5390-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="f5390-117">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f5390-117">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5390-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5390-118">See Also</span></span>  
 <span data-ttu-id="f5390-119">[Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="f5390-119">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="f5390-120">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="f5390-120">BAM Management Utility</span></span>](../core/bam-management-utility.md)