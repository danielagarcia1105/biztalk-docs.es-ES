---
title: "Cómo configurar controlador de recepción de HTTP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- permissions, receive handlers
- configuring [HTTP adapters], permissions
- HTTP adapters, receive handlers
- receive handlers, permissions
- configuring [HTTP adapters], receive handlers
- permissions, HTTP adapters
- receive handlers, HTTP adapters
- HTTP adapters, permissions
ms.assetid: c295489e-dbbb-44f7-bddb-d3cdfe302cf5
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0380804039d45efbe3db06b6fc072a3afb8b6b48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-http-receive-handler"></a><span data-ttu-id="fab16-102">Cómo configurar controlador de recepción de HTTP</span><span class="sxs-lookup"><span data-stu-id="fab16-102">How to Configure an HTTP Receive Handler</span></span>
<span data-ttu-id="fab16-103">Utilice este procedimiento para configurar las propiedades de un controlador de recepción de HTTP.</span><span class="sxs-lookup"><span data-stu-id="fab16-103">Use the following procedure to configure the properties for an HTTP receive handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fab16-104">Cada host sólo podrá tener un controlador de recepción asociado.</span><span class="sxs-lookup"><span data-stu-id="fab16-104">Each host can have only one receive handler associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fab16-105">El adaptador de recepción de HTTP se ejecuta en el contexto de una instancia de host aislado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fab16-105">The HTTP receive adapter runs in the context of a BizTalk Isolated Host instance.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="fab16-106">Al usar controladores de adaptador de HTTP o de SOAP, se recomienda instalar las instancias de host de estos controladores en equipos de Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fab16-106">When using HTTP or SOAP adapter handlers, it is recommended that you install the host instances for these handlers on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computers.</span></span>  
  
### <a name="to-configure-the-general-properties-for-an-http-receive-handler"></a><span data-ttu-id="fab16-107">Para configurar las propiedades generales de un controlador de recepción de HTTP</span><span class="sxs-lookup"><span data-stu-id="fab16-107">To configure the general properties for an HTTP receive handler</span></span>  
  
1.  <span data-ttu-id="fab16-108">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="fab16-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="fab16-109">En la lista de adaptadores expandida, haga clic en **HTTP,** en el panel derecho, haga clic en el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fab16-109">In the expanded adapter list, click **HTTP,** in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="fab16-110">En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host al que se asociará el controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="fab16-110">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="fab16-111">Haga clic en **propiedades** para tener acceso a la **tamaño de los lotes** controlador de recepción de propiedad para el HTTP.</span><span class="sxs-lookup"><span data-stu-id="fab16-111">Click **Properties** to access the **Batch size** property for the HTTP receive handler.</span></span>  
  
5.  <span data-ttu-id="fab16-112">Escriba un valor entre 1 y 256 y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fab16-112">Enter a value from 1 to 256 and click **OK**.</span></span>  
  
6.  <span data-ttu-id="fab16-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fab16-113">Click **OK**.</span></span>  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="fab16-114"> está diseñado para procesar lotes de mensajes eficazmente y no para procesar un único mensaje muy rápidamente.</span><span class="sxs-lookup"><span data-stu-id="fab16-114"> is designed to process batches of messages effectively and not to process a single message very quickly.</span></span> <span data-ttu-id="fab16-115">Por lo que si se va a usar este controlador de recepción para ubicaciones de recepción bidireccionales o de solicitud-respuesta, puede minimizar la latencia siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fab16-115">So if this receive handler is going to be used for two way/request-response receive locations then you can minimize latency by following these steps:</span></span>  
  
-   <span data-ttu-id="fab16-116">Establecer el **tamaño de los lotes** en un valor de 1.</span><span class="sxs-lookup"><span data-stu-id="fab16-116">Set the **Batch size** property to a value of 1.</span></span>  
  
-   <span data-ttu-id="fab16-117">Reducir el **MaxReceiveInterval** valor entre el valor predeterminado de 500 y un valor inferior a 100 para la **Messaging Isolated, XLANG/s,** y **Messaging In-Process** servicio clases.</span><span class="sxs-lookup"><span data-stu-id="fab16-117">Reduce the **MaxReceiveInterval** value from the default value of 500 to a value less than 100 for the **Messaging Isolated, XLANG/s,** and **Messaging In-Process** service classes.</span></span>  <span data-ttu-id="fab16-118">Se realizan cambios el **adm_ServiceClass** tabla de la base de datos de administración de BizTalk, que contiene un registro para cada uno de estos tipos de servicio.</span><span class="sxs-lookup"><span data-stu-id="fab16-118">Changes are made the **adm_ServiceClass** table of the BizTalk Management database, which contains one record for each of these service types.</span></span>  <span data-ttu-id="fab16-119">Tenga cuidado al cambiar esta configuración porque se trata de un cambio amplio de tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="fab16-119">Use caution when changing this setting because this is a service-type-wide change.</span></span> <span data-ttu-id="fab16-120">Esta configuración especifica el intervalo máximo de sondeo (en milisegundos) para que el agente de mensajería de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sondee la base de datos de cuadro de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para ver si hay mensajes.</span><span class="sxs-lookup"><span data-stu-id="fab16-120">This setting specifies the maximum polling interval (in milliseconds) at which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messaging agent polls the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Messagebox database for messages.</span></span>  <span data-ttu-id="fab16-121">También se usa por el controlador de limitación para decidir si se necesita la limitación de mensajes bajo determinadas condiciones de carga.</span><span class="sxs-lookup"><span data-stu-id="fab16-121">It also is used by the throttle controller to decide whether message throttling is needed under certain load conditions.</span></span> <span data-ttu-id="fab16-122">Si es necesario, el controlador de limitación retrasará de manera incremental el intervalo de distribución de mensajes según las condiciones de sobrecarga del sistema.</span><span class="sxs-lookup"><span data-stu-id="fab16-122">If needed, the throttling controller will incrementally delay the message dispatch interval based upon stress conditions on the system.</span></span> <span data-ttu-id="fab16-123">En un sistema de alto rendimiento, esa configuración no se usará.</span><span class="sxs-lookup"><span data-stu-id="fab16-123">In a high throughput system, this setting will not be used.</span></span>  <span data-ttu-id="fab16-124">Sin embargo, una vez usados estos valores, el intervalo de tiempo cambiará dinámicamente entre MaxReceiveInteral/10 y MaxReceiveInterval.</span><span class="sxs-lookup"><span data-stu-id="fab16-124">Once this values is used, however, the time interval will dynamically change between MaxReceiveInteral/10 and MaxReceiveInterval.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fab16-125">Si cambia esta configuración afecta a todos los hosts que se crean con un **tipo de Host** de **Isolated**.</span><span class="sxs-lookup"><span data-stu-id="fab16-125">Changing this setting affects all hosts that are created with a **Host Type** of **Isolated**.</span></span>  
  
-   <span data-ttu-id="fab16-126">Reinicie los grupos de aplicaciones de IIS asociados con las funciones de recepción HTTP configuradas.</span><span class="sxs-lookup"><span data-stu-id="fab16-126">Restart the IIS Application Pool(s) associated with any HTTP receive functions that you have configured.</span></span>  
  
 <span data-ttu-id="fab16-127">La cuenta de inicio de sesión para la **BizTalkServerIsolatedHost** instancia de host debe tener de lectura y permisos de escritura en el directorio o directorios temporales para compilar dinámicamente los archivos de código subyacente utilizados HTTP recepción (función).</span><span class="sxs-lookup"><span data-stu-id="fab16-127">The logon account for the **BizTalkServerIsolatedHost** host instance must have Read and Write permissions to the temp directory or directories to dynamically compile the code-behind files used by the HTTP receive function.</span></span> <span data-ttu-id="fab16-128">Utilice el procedimiento siguiente para conceder los permisos.</span><span class="sxs-lookup"><span data-stu-id="fab16-128">Use the following procedure to grant permissions.</span></span>  
  
### <a name="to-grant-the-account-for-the-biztalkserverisolatedhost-host-instance-read-and-write-permissions-to-the-temp-directory-of-your-biztalk-server"></a><span data-ttu-id="fab16-129">Para conceder a la cuenta de la instancia de host BizTalkServerIsolatedHost los permisos de lectura y escritura en el escritorio temporal de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fab16-129">To grant the account for the BizTalkServerIsolatedHost host instance Read and Write permissions to the temp directory of your BizTalk server</span></span>  
  
1.  <span data-ttu-id="fab16-130">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **CMD**, y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fab16-130">Click **Start**, click **Run**, type **CMD**, and press ENTER.</span></span>  
  
2.  <span data-ttu-id="fab16-131">En el símbolo del sistema, escriba **set TEMP** y presione ENTRAR para mostrar el directorio asociado con el **TEMP** variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="fab16-131">At the command prompt, type **set TEMP** and press ENTER to display the directory associated with the **TEMP** environment variable.</span></span>  
  
3.  <span data-ttu-id="fab16-132">En el símbolo del sistema, escriba **set TMP** y presione ENTRAR para mostrar el directorio asociado con el **TMP** variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="fab16-132">At the command prompt, type **set TMP** and press ENTER to display the directory associated with the **TMP** environment variable.</span></span>  
  
 <span data-ttu-id="fab16-133">Conceda a la cuenta que se especifica como la cuenta de inicio de sesión para la **BizTalkServerIsolatedHost** hospedar la instancia de lectura y permisos de escritura en el directorio o directorios asociados con la **TEMP** y  **TMP** variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="fab16-133">Grant the account that is specified as the logon account for the **BizTalkServerIsolatedHost** host instance Read and Write permissions to the directory or directories associated with the **TEMP** and **TMP** environment variables.</span></span> <span data-ttu-id="fab16-134">Para determinar la cuenta de inicio de sesión para la **BizTalkServerIsolatedHost** instancia, en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda  **Grupo de BizTalk**, expanda **configuración de plataforma**, expanda **instancias de Host**, haga clic en el **BizTalkServerIsolatedHost** host instancia en el panel derecho y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fab16-134">To determine the logon account for the **BizTalkServerIsolatedHost** instance, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, expand **Host Instances**, right-click the **BizTalkServerIsolatedHost** host instance in the right pane, and then click **Properties**.</span></span> <span data-ttu-id="fab16-135">La cuenta de inicio de sesión usada para la instancia de host aparece junto a la **inicio de sesión** etiqueta.</span><span class="sxs-lookup"><span data-stu-id="fab16-135">The logon account used for the host instance is listed next to the **Logon** label.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab16-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="fab16-136">See Also</span></span>  
 [<span data-ttu-id="fab16-137">Configurar el adaptador HTTP</span><span class="sxs-lookup"><span data-stu-id="fab16-137">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)