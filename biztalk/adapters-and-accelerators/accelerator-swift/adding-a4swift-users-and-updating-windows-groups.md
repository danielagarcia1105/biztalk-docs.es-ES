---
title: Agregar usuarios de A4SWIFT y actualizar grupos de Windows | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user accounts, Windows groups
- Windows groups, user accounts
- user accounts, creating
- Windows groups, updating
- updating Windows groups
- A4SWIFT, creating user accounts
ms.assetid: ddc54457-6499-402c-9cc2-f7b17bbc255f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce3fbf2f3b78b13205b43989c2b0c03909dec392
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adding-a4swift-users-and-updating-windows-groups"></a><span data-ttu-id="ff447-102">Agregar usuarios de A4SWIFT y actualizar grupos de Windows</span><span class="sxs-lookup"><span data-stu-id="ff447-102">Adding A4SWIFT Users and Updating Windows Groups</span></span>
<span data-ttu-id="ff447-103">Después de crear e instalar certificados para los roles de reparación de mensajes y nuevo envío, debe crear [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a los usuarios y agregue [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] a los usuarios a grupos.</span><span class="sxs-lookup"><span data-stu-id="ff447-103">After you create and install certificates for Message Repair and New Submission roles, you must create [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] users and add [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] users to groups.</span></span>  
  
 <span data-ttu-id="ff447-104">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="ff447-104">**Summary**</span></span>  
  
 <span data-ttu-id="ff447-105">Crear usuarios de reparación de mensajes y nuevo envío y agregar cuentas de dominio o local a [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] grupos de usuarios, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="ff447-105">Create Message Repair and New Submission users and add local or domain accounts to [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] user groups, as follows:</span></span>  
  
-   <span data-ttu-id="ff447-106">En el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] consola de administración, debe crear tantos usuarios como funciones en las fases de flujo de trabajo del proceso de reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="ff447-106">In the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Management Console, you need to create as many users as there are roles in the workflow stages of your Message Repair and New Submission process.</span></span> <span data-ttu-id="ff447-107">Asociar un certificado diferente a cada uno de estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="ff447-107">Associate a distinct certificate with each of these users.</span></span>  
  
-   <span data-ttu-id="ff447-108">Mediante el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] utilidad de administración de equipos, agregue cada usuario local que está creando, reparación, comprobar o la aprobación de un mensaje a los usuarios de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="ff447-108">Using the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Computer Management utility, add each local user who is creating, repairing, verifying, or approving a message to the A4SWIFT Users.</span></span>  
  
-   <span data-ttu-id="ff447-109">Mediante el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] utilidad de administración de equipos, agregue el usuario local que se muestra en el campo de inicio de sesión para que el servicio del servicio de BizTalk grupo la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="ff447-109">Using the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Computer Management utility, add the local user that is listed in the Log On As field for the BizTalk Service BizTalk Group service to the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Users group.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff447-110">Para obtener más información acerca de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuarios y roles, consulte [crear departamentos y Roles para la reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md).</span><span class="sxs-lookup"><span data-stu-id="ff447-110">For more information about [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] users and roles, see [Creating Departments and Roles for Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md).</span></span>  
  
### <a name="to-add-user-accounts-to-the-a4swift-users-group"></a><span data-ttu-id="ff447-111">Para agregar cuentas de usuario al grupo de usuarios de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="ff447-111">To add User Accounts to the A4SWIFT Users Group</span></span>  
  
1.  <span data-ttu-id="ff447-112">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.</span><span class="sxs-lookup"><span data-stu-id="ff447-112">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="ff447-113">En el **administración de equipos** cuadro de diálogo, en el panel izquierdo, expanda **usuarios y grupos locales**y, a continuación, haga clic en **grupos**.</span><span class="sxs-lookup"><span data-stu-id="ff447-113">In the **Computer Management** dialog box, in the left pane, expand **Local Users and Groups**, and then click **Groups**.</span></span>  
  
3.  <span data-ttu-id="ff447-114">En el **administración de equipos** cuadro de diálogo, en el panel derecho, haga doble clic en **A4SWIFT usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ff447-114">In the **Computer Management** dialog box, in the right pane, double-click **A4SWIFT Users**.</span></span>  
  
4.  <span data-ttu-id="ff447-115">En el **propiedades de los usuarios de A4SWIFT** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="ff447-115">In the **A4SWIFT Users Properties** dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="ff447-116">En el **Seleccionar usuarios, equipos o grupos** cuadro de diálogo, en la **escriba los nombres de objeto para seleccionar** panel, escriba el nombre de un usuario local que está creando, reparación, comprobar o aprobar un mensaje y, a continuación, Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff447-116">In the **Select Users, Computers, or Groups** dialog box, in the **Enter the object names to select** pane, type the name of a local user who is creating, repairing, verifying, or approving a message, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="ff447-117">Repita el paso 5 para cada usuario local que está creando, reparación, comprobar o aprobar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ff447-117">Repeat step 5 for each local user who is creating, repairing, verifying, or approving a message.</span></span>  
  
7.  <span data-ttu-id="ff447-118">En el cuadro de diálogo Propiedades de los usuarios de A4SWIFT, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff447-118">In the A4SWIFT Users Properties dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="ff447-119">En el cuadro de diálogo Administración de equipos, en el panel izquierdo, expanda Servicios y aplicaciones y, a continuación, haga clic en servicios.</span><span class="sxs-lookup"><span data-stu-id="ff447-119">In the Computer Management dialog box, in the left pane, expand Services and Applications, and then click Services.</span></span> <span data-ttu-id="ff447-120">En el panel derecho, haga clic en **servicio de BizTalk grupo**.</span><span class="sxs-lookup"><span data-stu-id="ff447-120">In the right pane, click **BizTalk Service BizTalk Group**.</span></span> <span data-ttu-id="ff447-121">Tenga en cuenta el usuario mencionado en la columna de inicio de sesión de **servicio de BizTalk grupo**.</span><span class="sxs-lookup"><span data-stu-id="ff447-121">Note the user listed in the Log On As column for **BizTalk Service BizTalk Group**.</span></span>  
  
9. <span data-ttu-id="ff447-122">En el panel izquierdo de la **administración de equipos** cuadro de diálogo, expanda **usuarios y grupos locales**y, a continuación, haga clic en **grupos**.</span><span class="sxs-lookup"><span data-stu-id="ff447-122">In the left pane of the **Computer Management** dialog box, expand **Local Users and Groups**, and then click **Groups**.</span></span> <span data-ttu-id="ff447-123">Haga doble clic en **A4SWIFT usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ff447-123">Double-click **A4SWIFT Users**.</span></span> <span data-ttu-id="ff447-124">Asegúrese de que el usuario aparece en la columna de inicio de sesión de **servicio de BizTalk grupo** forma parte de la **A4SWIFT usuarios** grupo.</span><span class="sxs-lookup"><span data-stu-id="ff447-124">Ensure that the user listed in the Log On As column for **BizTalk Service BizTalk Group** is part of the **A4SWIFT Users** group.</span></span> <span data-ttu-id="ff447-125">Si no es así, agregue ese usuario a la **A4SWIFT usuarios** grupo.</span><span class="sxs-lookup"><span data-stu-id="ff447-125">If not, add that user to the **A4SWIFT Users** group.</span></span>  
  
10. <span data-ttu-id="ff447-126">Cerrar la sesión del servidor y, a continuación, volver a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="ff447-126">Log off the server, and then log back on.</span></span>