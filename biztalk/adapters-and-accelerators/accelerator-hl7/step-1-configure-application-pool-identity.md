---
title: 'Paso 1: Configurar la identidad del grupo de aplicaciones | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, application pools
- application pools
ms.assetid: 66286327-8580-4378-89ee-ddd7204b03c6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e61ee2994e81c3fdd352506d6a9757cde557fbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-application-pool-identity"></a><span data-ttu-id="b88f9-102">Paso 1: Configurar la identidad del grupo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b88f9-102">Step 1: Configure Application Pool Identity</span></span>
<span data-ttu-id="b88f9-103">En este tutorial, utilice un grupo de aplicaciones en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Internet Information Services (IIS) para procesar la orquestación, que se publique como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="b88f9-103">In this tutorial, you use an application pool in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Internet Information Services (IIS) to process the orchestration, which you publish as a Web service.</span></span> <span data-ttu-id="b88f9-104">Un grupo de aplicaciones es una agrupación de una o más direcciones URL servidas por un proceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b88f9-104">An application pool is a grouping of one or more URLs served by a worker process.</span></span>  
  
 <span data-ttu-id="b88f9-105">La identidad de un grupo de aplicaciones es el nombre de la cuenta de servicio en la que se ejecuta el proceso de trabajo del grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b88f9-105">The identity of an application pool is the name of the service account under which the worker process of the application pool runs.</span></span> <span data-ttu-id="b88f9-106">De forma predeterminada, grupos de aplicaciones funcionan bajo la cuenta de usuario del servicio de red, que tiene derechos de bajo nivel de acceso de usuario y no es suficiente para que la función de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="b88f9-106">By default, application pools operate under the Network Service user account, which has low-level user-access rights and is insufficient for this tutorial to function.</span></span> <span data-ttu-id="b88f9-107">Por motivos de seguridad que desea configurar la identidad del grupo de aplicaciones a una cuenta de usuario con los permisos mínimos, pero al menos permisos para escribir en la base de datos de cuadro de mensajes (BizTalkMsgBoxDb) y la base de datos de configuración (también conocido como el de BizTalk Base de datos de administración, o BizTalkMgmtDb).</span><span class="sxs-lookup"><span data-stu-id="b88f9-107">For security reasons, you want to configure the application pool identity to a user account with the absolute minimum permissions, but at least permissions to write to the MessageBox database (BizTalkMsgBoxDb) and Configuration database (also known as the BizTalk Management database, or BizTalkMgmtDb).</span></span>  
  
### <a name="to-change-the-service-account-under-which-an-application-pool-runs"></a><span data-ttu-id="b88f9-108">Para cambiar la cuenta de servicio en la que se ejecuta un grupo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b88f9-108">To change the service account under which an application pool runs</span></span>  
  
1.  <span data-ttu-id="b88f9-109">Haga clic en **iniciar**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="b88f9-109">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="b88f9-110">En el Administrador de Internet Information Services (IIS), expanda el equipo local y expanda **grupos de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b88f9-110">In Internet Information Services (IIS) Manager, expand the local computer, and expand **Application Pools**.</span></span>  
  
3.  <span data-ttu-id="b88f9-111">Haga clic en el grupo de aplicaciones que desea configurar (de forma predeterminada, este tutorial se ejecuta bajo la **DefaultAppPool**) y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b88f9-111">Right-click the application pool you want to configure (by default, this tutorial runs under the **DefaultAppPool**), and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b88f9-112">En el cuadro de diálogo Propiedades de DefaultAppPool, en la **identidad** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b88f9-112">In the DefaultAppPool Properties dialog box, on the **Identity** tab, do the following:</span></span>  
  
    |<span data-ttu-id="b88f9-113">Use</span><span class="sxs-lookup"><span data-stu-id="b88f9-113">Use this</span></span>|<span data-ttu-id="b88f9-114">Para</span><span class="sxs-lookup"><span data-stu-id="b88f9-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b88f9-115">**Predefinidos**</span><span class="sxs-lookup"><span data-stu-id="b88f9-115">**Predefined**</span></span>|<span data-ttu-id="b88f9-116">Anule la selección de **predefinidos**.</span><span class="sxs-lookup"><span data-stu-id="b88f9-116">Deselect **Predefined**.</span></span> <span data-ttu-id="b88f9-117">**Predefinidos** hace referencia a las cuentas de servicio estándar, como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b88f9-117">**Predefined** refers to standard service accounts, such as the following:</span></span><br /><br /> <span data-ttu-id="b88f9-118">-   **Servicio de red** (valor predeterminado), que tiene derechos de acceso de usuario de bajo nivel que se pueden usar para tener acceso a recursos en equipos remotos.</span><span class="sxs-lookup"><span data-stu-id="b88f9-118">-   **Network Service** (the default), which has low-level user access rights that can be used for access to resources on remote computers.</span></span><br /><span data-ttu-id="b88f9-119">-   **Servicio local**, que tiene derechos de acceso de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="b88f9-119">-   **Local Service**, which has low-level access rights.</span></span> <span data-ttu-id="b88f9-120">Use esta opción para las situaciones que no requieren acceso a los recursos de equipos remotos.</span><span class="sxs-lookup"><span data-stu-id="b88f9-120">You use this setting for situations that do not require access to resources on remote computers.</span></span><br /><span data-ttu-id="b88f9-121">-   **Sistema local**, que es una cuenta con más derechos de usuario de la cuenta de servicio de red o servicio Local.</span><span class="sxs-lookup"><span data-stu-id="b88f9-121">-   **Local System**, which is an account with more user rights than the Network Service or Local Service account.</span></span>|  
    |<span data-ttu-id="b88f9-122">**Configurable**</span><span class="sxs-lookup"><span data-stu-id="b88f9-122">**Configurable**</span></span>|<span data-ttu-id="b88f9-123">Seleccione **Configurable**.</span><span class="sxs-lookup"><span data-stu-id="b88f9-123">Select **Configurable**.</span></span> <span data-ttu-id="b88f9-124">**Puede configurar** hace referencia a nombres de usuario registrado.</span><span class="sxs-lookup"><span data-stu-id="b88f9-124">**Configurable** refers to registered user names.</span></span>|  
    |<span data-ttu-id="b88f9-125">**Nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="b88f9-125">**User name**</span></span>|<span data-ttu-id="b88f9-126">Escriba el nombre de usuario de la cuenta bajo la que desea que funcione el proceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b88f9-126">Type the user name of the account under which you want the worker process to operate.</span></span>|  
    |<span data-ttu-id="b88f9-127">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="b88f9-127">**Password**</span></span>|<span data-ttu-id="b88f9-128">Escriba la contraseña.</span><span class="sxs-lookup"><span data-stu-id="b88f9-128">Type the password.</span></span>|  
  
5.  <span data-ttu-id="b88f9-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b88f9-129">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b88f9-130">O bien, para mayor seguridad, podría crear un grupo de aplicaciones completamente nuevo que se ejecuta bajo una identidad personalizada que cree con permisos personalizados para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="b88f9-130">Alternatively, for increased security, you could create an entirely new application pool that runs under a custom identity that you create with permissions tailored for this tutorial.</span></span>  
  
 <span data-ttu-id="b88f9-131">Continúe con [paso 2: crear un nuevo proyecto](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md).</span><span class="sxs-lookup"><span data-stu-id="b88f9-131">Proceed to [Step 2: Create a New Project](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b88f9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b88f9-132">See Also</span></span>  
 [<span data-ttu-id="b88f9-133">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="b88f9-133">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)