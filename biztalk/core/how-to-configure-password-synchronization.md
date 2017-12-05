---
title: "Cómo configurar la sincronización de contraseña | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], replay files
- Password Synchronization [SSO], maximum age
- SSOCONFIG command line utility
- Password Synchronization [SSO], SSOCONFIG command line utility
- Password Synchronization [SSO], configuring
- configuring, Password Synchronization [SSO]
ms.assetid: 04000dfc-02b9-4d50-babe-8bc8a07a33b7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2e8348cdf78db3e95ed75e5d83e6ea53bdffdee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-password-synchronization"></a><span data-ttu-id="d9b94-102">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="d9b94-102">How to Configure Password Synchronization</span></span>
<span data-ttu-id="d9b94-103">La utilidad de línea de comandos SSOCONFIG se utiliza para establecer la configuración de la sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="d9b94-103">Use the SSOCONFIG command line utility to configure your password synchronization settings.</span></span>  
  
### <a name="to-specify-the-directory-for-replay-files"></a><span data-ttu-id="d9b94-104">Para especificar el directorio para archivos de reproducción</span><span class="sxs-lookup"><span data-stu-id="d9b94-104">To specify the directory for replay files</span></span>  
  
1.  <span data-ttu-id="d9b94-105">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d9b94-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="d9b94-106">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d9b94-106">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d9b94-107">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d9b94-107">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d9b94-108">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="d9b94-108">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="d9b94-109">Tipo de **ssoconfig - replayfiles \<directorio de archivos de reproducción\> &#124; - predeterminado** y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="d9b94-109">Type **ssoconfig -replayfiles \<replay files directory\> &#124; -default** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9b94-110">Los archivos de reproducción no se eliminan al cambiar la cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="d9b94-110">Replay files are not deleted when you change the service account.</span></span> <span data-ttu-id="d9b94-111">Si se cambia esta cuenta, será necesario eliminar los archivos de reproducción de forma manual.</span><span class="sxs-lookup"><span data-stu-id="d9b94-111">If you change this account, you will need to delete the replay files manually.</span></span>  
  
#### <a name="to-display-or-change-maximum-password-synchronization-age"></a><span data-ttu-id="d9b94-112">Para mostrar o cambiar la antigüedad máxima de la sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="d9b94-112">To display or change maximum password synchronization age</span></span>  
  
1.  <span data-ttu-id="d9b94-113">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d9b94-113">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="d9b94-114">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d9b94-114">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d9b94-115">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d9b94-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d9b94-116">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="d9b94-116">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="d9b94-117">Tipo de **ssoconfig - syncage \<antigüedad máxima de contraseña en horas\>**  y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="d9b94-117">Type **ssoconfig -syncage \<maximum password age in hours\>** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9b94-118">La utilidad SSOCONFIG usa la hora del equipo de SQL Server como la hora del sistema.</span><span class="sxs-lookup"><span data-stu-id="d9b94-118">The SSOCONFIG utility uses the time on the SQL Server computer as its system time.</span></span> <span data-ttu-id="d9b94-119">Téngalo en cuenta al utilizar cualquier comando relacionado con la hora.</span><span class="sxs-lookup"><span data-stu-id="d9b94-119">Remember this when using any commands related to time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9b94-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9b94-120">See Also</span></span>  
 [<span data-ttu-id="d9b94-121">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="d9b94-121">Password Synchronization</span></span>](../core/password-synchronization2.md)