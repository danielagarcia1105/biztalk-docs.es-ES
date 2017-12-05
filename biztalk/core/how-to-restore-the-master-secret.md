---
title: "Cómo restaurar el secreto principal | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], restoring
- Master Secret server, restoring
- restoring, Master Secret server
ms.assetid: 68e133c5-4591-4d76-9a3b-c9564ff1aa60
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9241c8d9c5f6e41f47199211d0215c16526951d6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-restore-the-master-secret"></a><span data-ttu-id="d6f22-102">Cómo restaurar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="d6f22-102">How to Restore the Master Secret</span></span>
<span data-ttu-id="d6f22-103">Como parte de los procedimientos de recuperación de datos, es probable que tenga que restaurar el secreto principal para poder reutilizar los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="d6f22-103">As part of data recovery procedures, you may need to restore the master secret to re-use existing data.</span></span> <span data-ttu-id="d6f22-104">Para realizar esta tarea, debe iniciar la sesión en el servidor secreto principal con una cuenta que sea administrador de Windows y administrador de SSO.</span><span class="sxs-lookup"><span data-stu-id="d6f22-104">In order to perform this task, you must log on to the master secret server with an account that is both a Windows administrator and an SSO administrator.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="d6f22-105">Para restaurar el secreto principal mediante el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="d6f22-105">To restore the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="d6f22-106">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="d6f22-106">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="d6f22-107">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="d6f22-107">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="d6f22-108">Haga clic en **System**y, a continuación, haga clic en **restaurar secreto**.</span><span class="sxs-lookup"><span data-stu-id="d6f22-108">Right-click **System**, and then click **Restore Secret**.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a><span data-ttu-id="d6f22-109">Para restaurar el secreto principal utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="d6f22-109">To restore the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="d6f22-110">En el **iniciar** menú, haga clic en **todos los programas**y, a continuación, haga clic en **Accesorios**.</span><span class="sxs-lookup"><span data-stu-id="d6f22-110">On the **Start** menu, click **All Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="d6f22-111">Haga clic en **símbolo**y, a continuación, haga clic en **ejecutar como...** .</span><span class="sxs-lookup"><span data-stu-id="d6f22-111">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="d6f22-112">Seleccione el administrador apropiado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d6f22-112">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d6f22-113">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d6f22-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d6f22-114">El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="d6f22-114">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="d6f22-115">Tipo de **ssoconfig – restoreSecret \<Restaurar archivo\>**, donde  **\<Restaurar archivo\>**  es la ruta de acceso y el nombre del archivo donde se encuentra el secreto principal almacena.</span><span class="sxs-lookup"><span data-stu-id="d6f22-115">Type **ssoconfig –restoreSecret \<restore file\>**, where **\<restore file\>** is the path and name of the file where the master secret is stored.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6f22-116">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="d6f22-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f22-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6f22-117">See Also</span></span>  
 <span data-ttu-id="d6f22-118">[Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="d6f22-118">[How to Generate the Master Secret](../core/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="d6f22-119">[Cómo realizar copias de seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="d6f22-119">[How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md) </span></span>  
 <span data-ttu-id="d6f22-120">[Servidor secreto principal](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="d6f22-120">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 [<span data-ttu-id="d6f22-121">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="d6f22-121">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)