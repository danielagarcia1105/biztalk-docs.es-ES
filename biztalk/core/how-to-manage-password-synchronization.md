---
title: "Cómo administrar la sincronización de contraseña | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], managing
- managing [SSO], disabling features
- managing [SSO], enabling features
- Password Synchronization [SSO], SSOMANAGE command line utility
- SSO database, SSOMANAGE command line utility
- managing, Password Synchronization [SSO]
- SSO database, database settings
- SSOMANAGE command line utility
ms.assetid: 033e63f2-e5b0-4400-99c3-145679d9b84e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ce76f2ca16cca44af1658983c49d11f6931e931
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-manage-password-synchronization"></a><span data-ttu-id="b17a7-102">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="b17a7-102">How to Manage Password Synchronization</span></span>
<span data-ttu-id="b17a7-103">El Complemento MMC o la utilidad de línea de comandos SSOMANAGE se utiliza para habilitar o deshabilitar las características de SSO, así como para mostrar la configuración de la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="b17a7-103">Use the MMC Snap-in or the SSOMANAGE command line utility to enable or disable SSO features, and to display current SSO database settings.</span></span>  
  
### <a name="to-manage-features-or-display-settings-using-the-mmc-snap-in"></a><span data-ttu-id="b17a7-104">Para administrar características o mostrar la configuración utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="b17a7-104">To manage features or display settings using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="b17a7-105">Haga clic con el botón secundario en la base de datos o característica adecuada.</span><span class="sxs-lookup"><span data-stu-id="b17a7-105">Right-click the appropriate feature or database.</span></span>  
  
2.  <span data-ttu-id="b17a7-106">Haga clic en el elemento de menú que proceda.</span><span class="sxs-lookup"><span data-stu-id="b17a7-106">Click the appropriate menu item.</span></span>  
  
### <a name="to-enable-sso-features-using-the-command-line"></a><span data-ttu-id="b17a7-107">Para habilitar las características de SSO utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b17a7-107">To enable SSO features using the command line</span></span>  
  
1.  <span data-ttu-id="b17a7-108">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b17a7-108">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b17a7-109">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b17a7-109">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b17a7-110">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="b17a7-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b17a7-111">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="b17a7-111">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b17a7-112">Tipo de **ssomanage-habilitar** y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b17a7-112">Type **ssomanage -enable** and press Enter.</span></span>  
  
### <a name="to-disable-sso-features-using-the-command-line"></a><span data-ttu-id="b17a7-113">Para deshabilitar las características de SSO utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b17a7-113">To disable SSO features using the command line</span></span>  
  
1.  <span data-ttu-id="b17a7-114">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b17a7-114">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b17a7-115">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b17a7-115">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b17a7-116">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="b17a7-116">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b17a7-117">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="b17a7-117">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b17a7-118">Tipo de **ssomanage-deshabilitar** y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b17a7-118">Type **ssomanage -disable** and press Enter.</span></span>  
  
### <a name="to-display-current-database-settings-using-the-command-line"></a><span data-ttu-id="b17a7-119">Para mostrar la configuración de la base de datos utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b17a7-119">To display current database settings using the command line</span></span>  
  
1.  <span data-ttu-id="b17a7-120">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b17a7-120">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b17a7-121">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b17a7-121">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b17a7-122">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="b17a7-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b17a7-123">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="b17a7-123">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b17a7-124">Tipo de **ssomanage - displaydb** y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b17a7-124">Type **ssomanage -displaydb** and press Enter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b17a7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b17a7-125">See Also</span></span>  
 [<span data-ttu-id="b17a7-126">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="b17a7-126">Password Synchronization</span></span>](../core/password-synchronization2.md)