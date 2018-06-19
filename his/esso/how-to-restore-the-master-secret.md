---
title: Cómo restaurar el secreto principal | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b331c9c5-ca90-4a05-b3f6-59db88bf73dc
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5e640f2762ed9f9cc03a7795062c98a6aa76a59d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250952"
---
# <a name="how-to-restore-the-master-secret"></a><span data-ttu-id="02a36-102">Cómo restaurar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="02a36-102">How to Restore the Master Secret</span></span>
<span data-ttu-id="02a36-103">Como parte de los procedimientos de recuperación de datos, es posible que deba restaurar el secreto principal para poder reutilizar los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="02a36-103">As part of data recovery procedures, you might have to restore the master secret to reuse existing data.</span></span> <span data-ttu-id="02a36-104">Para llevar a cabo esta tarea, debe iniciar sesión en el servidor secreto principal mediante el uso de una cuenta que sea un administrador de Windows y un administrador de inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="02a36-104">To perform this task, you must log on to the master secret server by using an account that is both a Windows administrator and a Single Sign-On (SSO) administrator.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="02a36-105">Para restaurar el secreto principal mediante el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="02a36-105">To restore the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="02a36-106">Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="02a36-106">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="02a36-107">En el panel de ámbito del complemento de Microsoft Management Console (MMC) de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="02a36-107">In the scope pane of the ENTSSO Microsoft Management Console (MMC) Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="02a36-108">Haga clic en **System**y, a continuación, haga clic en **restaurar secreto principal**.</span><span class="sxs-lookup"><span data-stu-id="02a36-108">Right-click **System**, and then click **Restore Master Secret**.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a><span data-ttu-id="02a36-109">Para restaurar el secreto principal utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="02a36-109">To restore the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="02a36-110">En el **iniciar** menú, haga clic en **programas**y, a continuación, haga clic en **Accesorios**.</span><span class="sxs-lookup"><span data-stu-id="02a36-110">On the **Start** menu, click **Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="02a36-111">Haga clic en **símbolo**y, a continuación, haga clic en **ejecutar como...** .</span><span class="sxs-lookup"><span data-stu-id="02a36-111">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="02a36-112">Seleccione el administrador apropiado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02a36-112">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="02a36-113">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="02a36-113">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="02a36-114">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="02a36-114">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="02a36-115">Tipo de `ssoconfig –restoresecret <restore file>`, donde  *\<Restaurar archivo >* es la ruta de acceso y nombre del archivo donde se almacena el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="02a36-115">Type `ssoconfig –restoresecret <restore file>`, where *\<restore file>* is the path and name of the file where the master secret is stored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a36-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="02a36-116">See Also</span></span>  
 <span data-ttu-id="02a36-117">[Cómo generar el secreto principal](../esso/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="02a36-117">[How to Generate the Master Secret](../esso/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="02a36-118">[Cómo realizar copias de seguridad del secreto principal](../esso/how-to-back-up-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="02a36-118">[How to Back Up the Master Secret](../esso/how-to-back-up-the-master-secret.md) </span></span>  
 <span data-ttu-id="02a36-119">[Servidor secreto principal](../esso/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="02a36-119">[Master Secret Server](../esso/master-secret-server.md) </span></span>  
 [<span data-ttu-id="02a36-120">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="02a36-120">Managing the Master Secret</span></span>](../esso/managing-the-master-secret.md)