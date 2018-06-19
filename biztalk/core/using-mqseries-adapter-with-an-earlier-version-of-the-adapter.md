---
redirect_url: /biztalk/core/mqseries-adapter-deployment-options
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2aa74be2d86bcb8f32661fdcf06727eb6391861d
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710711"
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a><span data-ttu-id="ece9d-101">Utilizar el adaptador de MQSeries con una versión anterior del adaptador</span><span class="sxs-lookup"><span data-stu-id="ece9d-101">Using MQSeries Adapter with an Earlier Version of the Adapter</span></span>
<span data-ttu-id="ece9d-102">Las distintas versiones de BizTalk Server del adaptador de MQSeries pueden trabajar con el mismo WebSphere MQ Server remoto en Windows.</span><span class="sxs-lookup"><span data-stu-id="ece9d-102">The different BizTalk Server versions of the MQSeries adapter can all work with the same remote WebSphere MQ Server on Windows.</span></span> <span data-ttu-id="ece9d-103">Esto resulta posible porque las siguientes versiones de las aplicaciones COM+ utilizadas con el adaptador de MQSeries pueden coexistir en el mismo equipo con WebSphere MQSeries:</span><span class="sxs-lookup"><span data-stu-id="ece9d-103">This is possible because the following versions of the COM+ applications used with the MQSeries adapter can coexist on the same WebSphere MQSeries computer:</span></span>  
  
-   <span data-ttu-id="ece9d-104">**Aplicación MQSAgent (MQSAgent2) COM +** utilizada con el adaptador de MQSeries (BizTalk Server 2006)</span><span class="sxs-lookup"><span data-stu-id="ece9d-104">**MQSAgent (MQSAgent2) COM+ application** used with the MQSeries Adapter (BizTalk Server 2006)</span></span> 
  
-   <span data-ttu-id="ece9d-105">**Aplicación MQSAgent COM +** utilizada con el adaptador de MQSeries (BizTalk Server 2004)</span><span class="sxs-lookup"><span data-stu-id="ece9d-105">**MQSAgent COM+ application** used with the MQSeries Adapter (BizTalk Server 2004)</span></span>  
  
-   <span data-ttu-id="ece9d-106">**Aplicación MQHelper COM +** utilizada con el adaptador de MQSeries (BizTalk Server 2002)</span><span class="sxs-lookup"><span data-stu-id="ece9d-106">**MQHelper COM+ application** used with the MQSeries Adapter (BizTalk Server 2002)</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="ece9d-107">Al realizar la configuración de una instalación en paralelo de estas aplicaciones COM+, asegúrese de que ninguna se configura para utilizar las mismas colas de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="ece9d-107">When configuring a side-by-side installation of these COM+ applications, ensure that none of these COM+ applications are configured to use the same MQSeries queues.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ece9d-108">Solo se admite la instalación en paralelo de la versión de BizTalk Server 2006 de la aplicación COM + del adaptador de MQSeries con una versión anterior de la aplicación COM + del adaptador de MQSeries si una versión anterior de BizTalk Server no está instalada en el WebSphere Equipo de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="ece9d-108">Side-by-side installation of the BizTalk Server 2006 version of the MQSeries Adapter COM+ application with an earlier version of the MQSeries Adapter COM+ application is only supported if an earlier version of BizTalk Server is not installed on the WebSphere MQSeries computer.</span></span>  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a><span data-ttu-id="ece9d-109">Para instalar la versión BizTalk Server 2006 de la aplicación COM+ del Adaptador de MQSeries en un equipo con WebSphere MQSeries que está ejecutando una versión anterior de la aplicación COM+ del Adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="ece9d-109">To install the BizTalk Server 2006 version of the MQSeries Adapter COM+ application on a WebSphere MQSeries computer that is running an earlier version of the MQSeries Adapter COM+ application</span></span>  
  
1.  <span data-ttu-id="ece9d-110">Ejecute el Bootstrap.msi desde el directorio \Platform\BootStrap\ del CD BizTalk Server 2006 para copiar los archivos de dependencia MSVCR80.dll y MSVCP80.dll en el equipo con WebSphere MQSeries.</span><span class="sxs-lookup"><span data-stu-id="ece9d-110">Run the Bootstrap.msi from the \Platform\BootStrap\ directory of the BizTalk Server 2006 CD to copy the dependency files MSVCR80.dll and MSVCP80.dll to the WebSphere MQSeries computer.</span></span>  
  
2.  <span data-ttu-id="ece9d-111">Copie el archivo MQSAgent.dll desde el directorio \Msi\Program Files\ en el CD de BizTalk Server 2006 en el equipo con WebSphere MQSeries.</span><span class="sxs-lookup"><span data-stu-id="ece9d-111">Copy the file MQSAgent.dll from the \Msi\Program Files\ directory on the BizTalk Server 2006 CD to the WebSphere MQSeries computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ece9d-112">Copie también el archivo MQSTrace.cmd desde este directorio para usar el equipo con WebSphere MQSeries si tiene intención de usar la utilidad de seguimiento de MQSAgent.</span><span class="sxs-lookup"><span data-stu-id="ece9d-112">Also copy the file MQSTrace.cmd from this directory to the WebSphere MQSeries computer if you plan on using the MQSAgent tracing utility.</span></span> <span data-ttu-id="ece9d-113">Para obtener más información sobre el MQSAgent vea utilidad de seguimiento [analizar errores del adaptador de MQSeries con las herramientas de seguimiento](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ece9d-113">For more information about the MQSAgent tracing utility see [Analyzing MQSeries Adapter Errors with the Trace Tools](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md).</span></span>  
  
3.  <span data-ttu-id="ece9d-114">Registre de forma manual los componentes de MQSAgent.dll mediante la ejecución de regsvr32 mqsagent.dll en el equipo con WebSphere MQSeries:</span><span class="sxs-lookup"><span data-stu-id="ece9d-114">Manually register the components in MQSAgent.dll by running regsvr32 mqsagent.dll on the WebSphere MQSeries computer:</span></span>  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ece9d-115">Ejecute este comando desde el mismo directorio al que copió MQSAgent.dll.</span><span class="sxs-lookup"><span data-stu-id="ece9d-115">Run this command from the same directory that you copied MQSAgent.dll to.</span></span>  
  
4.  <span data-ttu-id="ece9d-116">Cree una nueva aplicación COM+ para los componentes de MQSAgent:</span><span class="sxs-lookup"><span data-stu-id="ece9d-116">Create a new COM+ application for the MQSAgent components:</span></span>  
  
    -   <span data-ttu-id="ece9d-117">Haga clic en aplicaciones COM +, haga clic en **New**, **aplicación** para mostrar la **Asistente para instalación de aplicación COM +** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ece9d-117">Right-click COM+ Applications, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  
  
    -   <span data-ttu-id="ece9d-118">Haga clic en **crear una aplicación vacía**.</span><span class="sxs-lookup"><span data-stu-id="ece9d-118">Click **Create an empty application**.</span></span>  
  
    -   <span data-ttu-id="ece9d-119">Escriba el nombre **MQSAgent2**, deje la opción predeterminada para **aplicación de servidor** habilitado y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ece9d-119">Enter the name **MQSAgent2**, leave the default option for **Server application** enabled and click **Next**.</span></span>  
  
    -   <span data-ttu-id="ece9d-120">Seleccione la opción de **este usuario**, escriba la información de cuenta correspondiente y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ece9d-120">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ece9d-121">Esta cuenta debe tener permisos de connect, put o get en las colas adecuadas de IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="ece9d-121">This account should have connect and put and/or get permissions on the appropriate IBM WebSphere MQ queues.</span></span>  
  
    -   <span data-ttu-id="ece9d-122">Haga clic en **siguiente** en el complemento **Roles de aplicación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ece9d-122">Click **Next** on the Add **Application Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="ece9d-123">Haga clic en **siguiente** en el **agregar usuarios a funciones** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ece9d-123">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="ece9d-124">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ece9d-124">Click **Finish**.</span></span>  
  
5.  <span data-ttu-id="ece9d-125">Agregue los componentes de MQSAgent.dll a la aplicación MQSAgent2 COM+:</span><span class="sxs-lookup"><span data-stu-id="ece9d-125">Add the MQSAgent.dll components to the MQSAgent2 COM+ application:</span></span>  
  
    -   <span data-ttu-id="ece9d-126">Haga clic para expandir el **MQSAgent2** aplicación COM +.</span><span class="sxs-lookup"><span data-stu-id="ece9d-126">Click to expand the **MQSAgent2** COM+ Application.</span></span>  
  
    -   <span data-ttu-id="ece9d-127">Haga clic en **componentes** y haga clic en **New**, **componente** para iniciar el Asistente para instalación de componentes COM + y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ece9d-127">Right-click **Components** and click **New**, **Component** to launch the COM+ Component Install Wizard and then click **Next**.</span></span>  
  
    -   <span data-ttu-id="ece9d-128">Haga clic en **instalar nuevos componentes**, busque el archivo MQSAgent.dll y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="ece9d-128">Click **Install New Components**, browse to the file MQSAgent.dll and then click **Open**.</span></span>  
  
    -   <span data-ttu-id="ece9d-129">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ece9d-129">Click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece9d-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ece9d-130">See Also</span></span>  
 [<span data-ttu-id="ece9d-131">Uso del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="ece9d-131">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)