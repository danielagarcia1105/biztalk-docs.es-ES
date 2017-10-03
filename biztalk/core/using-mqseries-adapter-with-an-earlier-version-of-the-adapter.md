---
title: "Utilizar el adaptador de MQSeries con una versión anterior del adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MQSeries adapters, compatibility
ms.assetid: 278a13ff-8e46-4af4-a76e-b6d4aad5b768
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba635b9bc4569f17418fc925c54c64d0fdc67461
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a><span data-ttu-id="067d2-102">Utilizar el adaptador de MQSeries con una versión anterior del adaptador</span><span class="sxs-lookup"><span data-stu-id="067d2-102">Using MQSeries Adapter with an Earlier Version of the Adapter</span></span>
<span data-ttu-id="067d2-103">Las versiones de [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)], [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] y [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] del adaptador de MQSeries pueden funcionar con la misma instancia de WebSphere MQ Server remota en Windows.</span><span class="sxs-lookup"><span data-stu-id="067d2-103">The [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)], [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)], and [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] versions of the MQSeries adapter can all work with the same remote WebSphere MQ Server on Windows.</span></span> <span data-ttu-id="067d2-104">Esto resulta posible porque las siguientes versiones de las aplicaciones COM+ utilizadas con el adaptador de MQSeries pueden coexistir en el mismo equipo con WebSphere MQSeries:</span><span class="sxs-lookup"><span data-stu-id="067d2-104">This is possible because the following versions of the COM+ applications used with the MQSeries adapter can coexist on the same WebSphere MQSeries computer:</span></span>  
  
-   <span data-ttu-id="067d2-105">**Aplicación MQSAgent (MQSAgent2) COM +** utilizada con el adaptador de MQSeries para [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)].</span><span class="sxs-lookup"><span data-stu-id="067d2-105">**MQSAgent (MQSAgent2) COM+ application** used with the MQSeries Adapter for [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)].</span></span>  
  
-   <span data-ttu-id="067d2-106">**Aplicación MQSAgent COM +** utilizada con el adaptador de MQSeries para [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)].</span><span class="sxs-lookup"><span data-stu-id="067d2-106">**MQSAgent COM+ application** used with the MQSeries Adapter for [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)].</span></span>  
  
-   <span data-ttu-id="067d2-107">**Aplicación MQHelper COM +** utilizada con el adaptador de MQSeries para [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)].</span><span class="sxs-lookup"><span data-stu-id="067d2-107">**MQHelper COM+ application** used with the MQSeries Adapter for [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="067d2-108">Al realizar la configuración de una instalación en paralelo de estas aplicaciones COM+, asegúrese de que ninguna se configura para utilizar las mismas colas de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="067d2-108">When configuring a side-by-side installation of these COM+ applications, ensure that none of these COM+ applications are configured to use the same MQSeries queues.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="067d2-109">La instalación en paralelo de la versión [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] de la aplicación COM+ del Adaptador de MQSeries con una versión anterior de la aplicación COM+ del Adaptador de MQSeries sólo se admite si no hay instalada una versión anterior de BizTalk Server en el equipo con WebSphere MQSeries.</span><span class="sxs-lookup"><span data-stu-id="067d2-109">Side-by-side installation of the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] version of the MQSeries Adapter COM+ application with an earlier version of the MQSeries Adapter COM+ application is only supported if an earlier version of BizTalk Server is not installed on the WebSphere MQSeries computer.</span></span>  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a><span data-ttu-id="067d2-110">Para instalar la versión BizTalk Server 2006 de la aplicación COM+ del Adaptador de MQSeries en un equipo con WebSphere MQSeries que está ejecutando una versión anterior de la aplicación COM+ del Adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="067d2-110">To install the BizTalk Server 2006 version of the MQSeries Adapter COM+ application on a WebSphere MQSeries computer that is running an earlier version of the MQSeries Adapter COM+ application</span></span>  
  
1.  <span data-ttu-id="067d2-111">Ejecute el Bootstrap.msi desde el directorio \Platform\BootStrap\ del CD de [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] para copiar los archivos de dependencia MSVCR80.dll y MSVCP80.dll en el equipo con WebSphere MQSeries.</span><span class="sxs-lookup"><span data-stu-id="067d2-111">Run the Bootstrap.msi from the \Platform\BootStrap\ directory of the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD to copy the dependency files MSVCR80.dll and MSVCP80.dll to the WebSphere MQSeries computer.</span></span>  
  
2.  <span data-ttu-id="067d2-112">Copie el archivo MQSAgent.dll desde el directorio \Msi\Archivos de programa\ del CD de [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] en el equipo con WebSphere MQSeries.</span><span class="sxs-lookup"><span data-stu-id="067d2-112">Copy the file MQSAgent.dll from the \Msi\Program Files\ directory on the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD to the WebSphere MQSeries computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="067d2-113">Copie también el archivo MQSTrace.cmd desde este directorio para usar el equipo con WebSphere MQSeries si tiene intención de usar la utilidad de seguimiento de MQSAgent.</span><span class="sxs-lookup"><span data-stu-id="067d2-113">Also copy the file MQSTrace.cmd from this directory to the WebSphere MQSeries computer if you plan on using the MQSAgent tracing utility.</span></span> <span data-ttu-id="067d2-114">Para obtener más información sobre el MQSAgent vea utilidad de seguimiento [analizar errores del adaptador de MQSeries con las herramientas de seguimiento](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md).</span><span class="sxs-lookup"><span data-stu-id="067d2-114">For more information about the MQSAgent tracing utility see [Analyzing MQSeries Adapter Errors with the Trace Tools](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md).</span></span>  
  
3.  <span data-ttu-id="067d2-115">Registre de forma manual los componentes de MQSAgent.dll mediante la ejecución de regsvr32 mqsagent.dll en el equipo con WebSphere MQSeries:</span><span class="sxs-lookup"><span data-stu-id="067d2-115">Manually register the components in MQSAgent.dll by running regsvr32 mqsagent.dll on the WebSphere MQSeries computer:</span></span>  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="067d2-116">Ejecute este comando desde el mismo directorio al que copió MQSAgent.dll.</span><span class="sxs-lookup"><span data-stu-id="067d2-116">Run this command from the same directory that you copied MQSAgent.dll to.</span></span>  
  
4.  <span data-ttu-id="067d2-117">Cree una nueva aplicación COM+ para los componentes de MQSAgent:</span><span class="sxs-lookup"><span data-stu-id="067d2-117">Create a new COM+ application for the MQSAgent components:</span></span>  
  
    -   <span data-ttu-id="067d2-118">Haga clic en aplicaciones COM +, haga clic en **New**, **aplicación** para mostrar la **Asistente para instalación de aplicación COM +** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="067d2-118">Right-click COM+ Applications, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  
  
    -   <span data-ttu-id="067d2-119">Haga clic en **crear una aplicación vacía**.</span><span class="sxs-lookup"><span data-stu-id="067d2-119">Click **Create an empty application**.</span></span>  
  
    -   <span data-ttu-id="067d2-120">Escriba el nombre **MQSAgent2**, deje la opción predeterminada para **aplicación de servidor** habilitado y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="067d2-120">Enter the name **MQSAgent2**, leave the default option for **Server application** enabled and click **Next**.</span></span>  
  
    -   <span data-ttu-id="067d2-121">Seleccione la opción de **este usuario**, escriba la información de cuenta correspondiente y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="067d2-121">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="067d2-122">Esta cuenta debe tener permisos de connect, put o get en las colas adecuadas de IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="067d2-122">This account should have connect and put and/or get permissions on the appropriate IBM WebSphere MQ queues.</span></span>  
  
    -   <span data-ttu-id="067d2-123">Haga clic en **siguiente** en el complemento **Roles de aplicación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="067d2-123">Click **Next** on the Add **Application Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="067d2-124">Haga clic en **siguiente** en el **agregar usuarios a funciones** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="067d2-124">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="067d2-125">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="067d2-125">Click **Finish**.</span></span>  
  
5.  <span data-ttu-id="067d2-126">Agregue los componentes de MQSAgent.dll a la aplicación MQSAgent2 COM+:</span><span class="sxs-lookup"><span data-stu-id="067d2-126">Add the MQSAgent.dll components to the MQSAgent2 COM+ application:</span></span>  
  
    -   <span data-ttu-id="067d2-127">Haga clic para expandir el **MQSAgent2** aplicación COM +.</span><span class="sxs-lookup"><span data-stu-id="067d2-127">Click to expand the **MQSAgent2** COM+ Application.</span></span>  
  
    -   <span data-ttu-id="067d2-128">Haga clic en **componentes** y haga clic en **New**, **componente** para iniciar el Asistente para instalación de componentes COM + y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="067d2-128">Right-click **Components** and click **New**, **Component** to launch the COM+ Component Install Wizard and then click **Next**.</span></span>  
  
    -   <span data-ttu-id="067d2-129">Haga clic en **instalar nuevos componentes**, busque el archivo MQSAgent.dll y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="067d2-129">Click **Install New Components**, browse to the file MQSAgent.dll and then click **Open**.</span></span>  
  
    -   <span data-ttu-id="067d2-130">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="067d2-130">Click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="067d2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="067d2-131">See Also</span></span>  
 [<span data-ttu-id="067d2-132">Uso del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="067d2-132">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)