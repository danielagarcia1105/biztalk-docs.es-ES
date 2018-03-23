---
title: 'Paso 3: Implementar la conexión para el adaptador de eco | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc223901-3ad3-4e71-8672-fea6bb4efe65
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a735654fd03f5efb39fe73eb845f4db3632d283
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="step-3-implement-the-connection-for-the-echo-adapter"></a><span data-ttu-id="742ee-102">Paso 3: Implementar la conexión para el adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="742ee-102">Step 3: Implement the Connection for the Echo Adapter</span></span>
<span data-ttu-id="742ee-103">![Paso 3 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span><span class="sxs-lookup"><span data-stu-id="742ee-103">![Step 3 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span></span>  
  
 <span data-ttu-id="742ee-104">**Tiempo en completarse:** 45 minutos</span><span class="sxs-lookup"><span data-stu-id="742ee-104">**Time to complete:** 45 minutes</span></span>  
  
 <span data-ttu-id="742ee-105">En este paso, implementará la capacidad de conexión del adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="742ee-105">In this step, you implement the connection capability of the Echo adapter.</span></span> <span data-ttu-id="742ee-106">Según el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], debe implementar las interfaces y clases abstractas siguientes cuando se conecte al sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="742ee-106">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], you must implement the following abstract class and interfaces when connecting to the target system.</span></span>  
  
-   `Microsoft.ServiceModel.Channels.Common.ConnectionUri`  
  
-   `Microsoft.ServiceModel.Channels.Common.IConnection`  
  
-   `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`  
  
 <span data-ttu-id="742ee-107">En lugar de derivar de los anteriores abstracta clases e interfaces, la [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente las tres clases derivadas, EchoAdapterConnection, EchoAdapterConnectionUri y EchoAdapterConnectionFactory.</span><span class="sxs-lookup"><span data-stu-id="742ee-107">Instead of deriving from the above abstract class and interfaces, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the three derived classes, EchoAdapterConnection, EchoAdapterConnectionUri, and EchoAdapterConnectionFactory.</span></span> <span data-ttu-id="742ee-108">Además de crear las clases, cada una tiene un método predeterminado que se produce una excepción concreta, `System.NotImplementedException`.</span><span class="sxs-lookup"><span data-stu-id="742ee-108">In addition to creating the classes, each has a default method that throws a specific exception, `System.NotImplementedException`.</span></span>  <span data-ttu-id="742ee-109">Esta instrucción le recuerda a los desarrolladores implementar cada clase.</span><span class="sxs-lookup"><span data-stu-id="742ee-109">This statement reminds the developer to implement each class.</span></span>  <span data-ttu-id="742ee-110">Cuando se implementa la clase, se debe quitar esta declaración de generación de excepciones.</span><span class="sxs-lookup"><span data-stu-id="742ee-110">When the class is implemented, this exception-throwing statement must be removed.</span></span>  
  
 <span data-ttu-id="742ee-111">En la sección siguiente, va a actualizar esas tres clases para obtener una mejor comprensión de cómo administrar una conexión, ¿cuál es la estructura URI y cómo recuperar mediante programación los distintos elementos URI y, a continuación, usar esos elementos en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="742ee-111">In the following section, you update those three classes to get a better understanding of how to handle a connection, what the URI structure is, and how to programmatically retrieve various URI elements and then use those elements within the adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="742ee-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="742ee-112">Prerequisites</span></span>  
 <span data-ttu-id="742ee-113">Antes de comenzar este paso, debe haber completado correctamente [paso 2: clasificar las propiedades de conexión y el adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="742ee-113">Before you begin this step, you must have successfully completed [Step 2: Categorize the Adapter and Connection Properties](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).</span></span> <span data-ttu-id="742ee-114">Y debe tener una idea clara de los `Microsoft.ServiceModel.Channels.Common.IConnection`, `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`, y `Microsoft.ServiceModel.Channels.Common.ConnectionUri` clases.</span><span class="sxs-lookup"><span data-stu-id="742ee-114">And you should have a clear understanding of the `Microsoft.ServiceModel.Channels.Common.IConnection`, `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`, and `Microsoft.ServiceModel.Channels.Common.ConnectionUri` classes.</span></span>  
  
## <a name="connection-related-classes"></a><span data-ttu-id="742ee-115">Clases relacionadas con la conexión</span><span class="sxs-lookup"><span data-stu-id="742ee-115">Connection-Related Classes</span></span>  
 <span data-ttu-id="742ee-116">El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera tres clases derivadas, EchoAdapterConnection, EchoAdapterConnectionUri y EchoAdapterConnectionFactory.</span><span class="sxs-lookup"><span data-stu-id="742ee-116">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] generates three derived classes, EchoAdapterConnection, EchoAdapterConnectionUri, and EchoAdapterConnectionFactory.</span></span> <span data-ttu-id="742ee-117">A continuación proporciona una breve descripción de los métodos asociados a cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="742ee-117">The following provides a brief overview of methods associated with each.</span></span>  
  
### <a name="echoadapterconnection"></a><span data-ttu-id="742ee-118">EchoAdapterConnection</span><span class="sxs-lookup"><span data-stu-id="742ee-118">EchoAdapterConnection</span></span>  
 <span data-ttu-id="742ee-119">Dependiendo de la complejidad de adaptador, tendrá que implementar todos los cinco métodos siguientes.</span><span class="sxs-lookup"><span data-stu-id="742ee-119">Depending on your adapter complexity, you might need to implement all of the following five methods.</span></span> <span data-ttu-id="742ee-120">Adaptador de eco, mayoría no son compatibles, dado que el ejemplo del adaptador eco implicar cualquier sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="742ee-120">For Echo adapter, most are not supported, because the Echo adapter sample does not involve any target system.</span></span>  
  
|<span data-ttu-id="742ee-121">**Método**</span><span class="sxs-lookup"><span data-stu-id="742ee-121">**Method**</span></span>|<span data-ttu-id="742ee-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="742ee-122">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="742ee-123">Cierre void público (tiempo de espera de intervalo de tiempo)</span><span class="sxs-lookup"><span data-stu-id="742ee-123">public void Close(TimeSpan timeout)</span></span>|<span data-ttu-id="742ee-124">Cierra la conexión con el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="742ee-124">Closes the connection to the target system.</span></span> <span data-ttu-id="742ee-125">El adaptador de eco utiliza este método para agregar solo los eventos de seguimiento para el agente de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="742ee-125">The Echo adapter uses this method to only add trace events to the trace listener.</span></span>|  
|<span data-ttu-id="742ee-126">bool pública IsValid (tiempo de espera de intervalo de tiempo)</span><span class="sxs-lookup"><span data-stu-id="742ee-126">public bool IsValid(TimeSpan timeout)</span></span>|<span data-ttu-id="742ee-127">Devuelve un valor que indica si la conexión sigue siendo válida.</span><span class="sxs-lookup"><span data-stu-id="742ee-127">Returns a value indicating whether the connection is still valid.</span></span><br /><br /> <span data-ttu-id="742ee-128">No se admite el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="742ee-128">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="742ee-129">Abrir void público (tiempo de espera de intervalo de tiempo)</span><span class="sxs-lookup"><span data-stu-id="742ee-129">public void Open(TimeSpan timeout)</span></span>|<span data-ttu-id="742ee-130">Se abre la conexión con el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="742ee-130">Opens the connection to the target system.</span></span><br /><br /> <span data-ttu-id="742ee-131">No disponible para el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="742ee-131">N/A for the Echo adapter.</span></span> <span data-ttu-id="742ee-132">Sin embargo, en el ejemplo se muestra cómo usar un elemento URI denominado enableAuthentication para obligar a los usuarios proporcionar un nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="742ee-132">However, the example shows you how to use a URI element called enableAuthentication to require users to provide a user name.</span></span>|  
|<span data-ttu-id="742ee-133">ClearContext() void público</span><span class="sxs-lookup"><span data-stu-id="742ee-133">public void ClearContext()</span></span>|<span data-ttu-id="742ee-134">Borra el contexto de la conexión.</span><span class="sxs-lookup"><span data-stu-id="742ee-134">Clears the context of the connection.</span></span> <span data-ttu-id="742ee-135">Este método se llama cuando la conexión se vuelve a establecer para la agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="742ee-135">This method is called when the connection is set back to the connection pool.</span></span><br /><br /> <span data-ttu-id="742ee-136">No se admite el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="742ee-136">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="742ee-137">pública Abort() void</span><span class="sxs-lookup"><span data-stu-id="742ee-137">public void Abort()</span></span>|<span data-ttu-id="742ee-138">Anula la conexión al sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="742ee-138">Aborts the connection to the target system.</span></span><br /><br /> <span data-ttu-id="742ee-139">No se admite el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="742ee-139">Not supported by the Echo adapter.</span></span>|  
  
### <a name="echoadapterconnectionfactory"></a><span data-ttu-id="742ee-140">EchoAdapterConnectionFactory</span><span class="sxs-lookup"><span data-stu-id="742ee-140">EchoAdapterConnectionFactory</span></span>  
 <span data-ttu-id="742ee-141">El generador de conexiones es responsable de crear la conexión.</span><span class="sxs-lookup"><span data-stu-id="742ee-141">The connection factory is responsible for creating the connection.</span></span> <span data-ttu-id="742ee-142">De forma predeterminada, debe modificar esta clase solo cuando se conecta a un sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="742ee-142">By default, you must modify this class only when connecting to a target system.</span></span> <span data-ttu-id="742ee-143">Aunque el adaptador de eco no implica ningún sistema de destino, muestra cómo utilizar un elemento URI personalizado denominado enableAuthentication si la conexión requiere autenticación de usuario.</span><span class="sxs-lookup"><span data-stu-id="742ee-143">Although the Echo adapter does not involve any target system, it shows you how to use a custom URI element called enableAuthentication if your connection requires user authentication.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="742ee-144">El enableAuthentication no es una palabra clave, es un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="742ee-144">The enableAuthentication is not a keyword, it is just a variable name.</span></span> <span data-ttu-id="742ee-145">Por lo tanto, puede elegir un nombre para ella.</span><span class="sxs-lookup"><span data-stu-id="742ee-145">Hence, you can choose any name for it.</span></span>  
  
### <a name="echoadapterconnectionuri"></a><span data-ttu-id="742ee-146">EchoAdapterConnectionUri</span><span class="sxs-lookup"><span data-stu-id="742ee-146">EchoAdapterConnectionUri</span></span>  
 <span data-ttu-id="742ee-147">Representa una cadena de conexión al sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="742ee-147">This represents a connection string to the target system.</span></span>  
  
|<span data-ttu-id="742ee-148">**Método**</span><span class="sxs-lookup"><span data-stu-id="742ee-148">**Method**</span></span>|<span data-ttu-id="742ee-149">**Description**</span><span class="sxs-lookup"><span data-stu-id="742ee-149">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="742ee-150">invalidación públicas Uri Uri</span><span class="sxs-lookup"><span data-stu-id="742ee-150">public override Uri Uri</span></span>|<span data-ttu-id="742ee-151">Obtiene y establece el identificador Uri.</span><span class="sxs-lookup"><span data-stu-id="742ee-151">Gets and sets the Uri.</span></span> <span data-ttu-id="742ee-152">Obtiene para generar la cadena de Uri y se establece para analizar la cadena de Uri.</span><span class="sxs-lookup"><span data-stu-id="742ee-152">Gets to build the Uri string and sets to parse the Uri string.</span></span>|  
|<span data-ttu-id="742ee-153">public EchoAdapterConnectionUri()</span><span class="sxs-lookup"><span data-stu-id="742ee-153">public EchoAdapterConnectionUri()</span></span>|<span data-ttu-id="742ee-154">Inicializa una nueva instancia de la clase ConnectionUri.</span><span class="sxs-lookup"><span data-stu-id="742ee-154">Initializes a new instance of the ConnectionUri class.</span></span>|  
|<span data-ttu-id="742ee-155">cadena de invalidación públicas SampleUriString</span><span class="sxs-lookup"><span data-stu-id="742ee-155">public override string SampleUriString</span></span>|<span data-ttu-id="742ee-156">Returns EchoAdapter.SCHEME + "://{hostname}/{application}?enableAuthentication={True&#124;False}".</span><span class="sxs-lookup"><span data-stu-id="742ee-156">Returns EchoAdapter.SCHEME + "://{hostname}/{application}?enableAuthentication={True&#124;False}".</span></span><br /><br /> <span data-ttu-id="742ee-157">Esta cadena de valor devuelta se muestra como el **ejemplo** en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] de herramientas, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="742ee-157">This return string displays as the **Example** in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, as shown in the following figure.</span></span>|  
  
 <span data-ttu-id="742ee-158">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")</span><span class="sxs-lookup"><span data-stu-id="742ee-158">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")</span></span>  
  
## <a name="echo-adapter-connection-uri"></a><span data-ttu-id="742ee-159">URI de conexión del adaptador eco</span><span class="sxs-lookup"><span data-stu-id="742ee-159">Echo Adapter Connection URI</span></span>  
 <span data-ttu-id="742ee-160">La conexión del adaptador de eco de ejemplo URI se describe como: EchoAapter.SCHEME://{hostname}/{application}?enableAuthentication={true&#124;false}</span><span class="sxs-lookup"><span data-stu-id="742ee-160">The sample Echo adapter connection URI is described as: EchoAapter.SCHEME://{hostname}/{application}?enableAuthentication={true&#124;false}</span></span>  
  
 <span data-ttu-id="742ee-161">Dado que la EchoAapter.SCHEME es echov2, la conexión URI es:</span><span class="sxs-lookup"><span data-stu-id="742ee-161">Since the EchoAapter.SCHEME is echov2, the connection URI is:</span></span>  
  
 <span data-ttu-id="742ee-162">echo2://lobhostname/lobapplication?enableAuthentication={true&#124;false}</span><span class="sxs-lookup"><span data-stu-id="742ee-162">echo2://lobhostname/lobapplication?enableAuthentication={true&#124;false}</span></span>  
  
 <span data-ttu-id="742ee-163">Puede leer el URI de conexión anterior cuando enableAuthentication = false como sigue:</span><span class="sxs-lookup"><span data-stu-id="742ee-163">You can read the previous connection URI when enableAuthentication=false as follows:</span></span>  
  
 <span data-ttu-id="742ee-164">Con el esquema de transporte echov2, vaya a un equipo denominado lobhostname, donde una aplicación denominada lobapplication que no se requiere la autenticación está esperando la conexión.</span><span class="sxs-lookup"><span data-stu-id="742ee-164">Using the echov2 transport schema, go to a computer named lobhostname, where an application named lobapplication that does not require any authentication is waiting for your connection.</span></span>  
  
 <span data-ttu-id="742ee-165">O bien, cuando enableAuthentication = true, la conexión de lectura como sigue:</span><span class="sxs-lookup"><span data-stu-id="742ee-165">Or, when enableAuthentication=true, read the connection as follows:</span></span>  
  
 <span data-ttu-id="742ee-166">Con el esquema de transporte echov2, vaya a un equipo denominado lobhostname, donde una aplicación denominada lobapplication espera que la autenticación está esperando la conexión.</span><span class="sxs-lookup"><span data-stu-id="742ee-166">Using the echov2 transport schema, go to a computer named lobhostname, where an application named lobapplication expects that authentication is waiting for your connection.</span></span> <span data-ttu-id="742ee-167">Para el adaptador de eco, se requiere un nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="742ee-167">For the Echo adapter, only a user name is required.</span></span>  
  
 <span data-ttu-id="742ee-168">Con un URI definido, mediante programación puede consumir y analizarlos para conectividad y la configuración.</span><span class="sxs-lookup"><span data-stu-id="742ee-168">With a defined URI, you can programmatically consume and parse it for connectivity and configuration.</span></span> <span data-ttu-id="742ee-169">Si la conexión requiere que los datos confidenciales, como un nombre de usuario y una contraseña, no contienen dicha información en el URI.</span><span class="sxs-lookup"><span data-stu-id="742ee-169">If the connection requires sensitive data such as a user name and password, do not contain such information in the URI.</span></span> <span data-ttu-id="742ee-170">En su lugar, agregue dicha información en el `System.ServiceModel.Description.ClientCredentials` objeto.</span><span class="sxs-lookup"><span data-stu-id="742ee-170">Instead, add such information in the `System.ServiceModel.Description.ClientCredentials` object.</span></span> <span data-ttu-id="742ee-171">El ejemplo de código que agregue muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="742ee-171">The code example that you add shows you how to do so.</span></span>  
  
 <span data-ttu-id="742ee-172">En el código siguiente, el adaptador de eco construye el URI de dos maneras para mostrar cómo el adaptador puede utilizar varios elementos URI para modificar la característica de adaptador.</span><span class="sxs-lookup"><span data-stu-id="742ee-172">In the following code, the Echo adapter constructs the URI in two ways to show you how the adapter can use various URI elements to modify the adapter feature.</span></span>  
  
 <span data-ttu-id="742ee-173">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]</span><span class="sxs-lookup"><span data-stu-id="742ee-173">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]</span></span>  
  
 <span data-ttu-id="742ee-174">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]&echoInUpperCase=true</span><span class="sxs-lookup"><span data-stu-id="742ee-174">echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]&echoInUpperCase=true</span></span>  
  
### <a name="retrieving-the-uri-element"></a><span data-ttu-id="742ee-175">Recupera el elemento de URI</span><span class="sxs-lookup"><span data-stu-id="742ee-175">Retrieving the URI Element</span></span>  
 <span data-ttu-id="742ee-176">Puede analizar el elemento de cada URI en el adaptador de eco URI echo2: / / lobhostname/lobapplication? enableAuthentication = false & echoInUpperCase = false.</span><span class="sxs-lookup"><span data-stu-id="742ee-176">You can parse each URI element in the Echo adapter URI echo2://lobhostname/lobapplication?enableAuthentication=false&echoInUpperCase=false.</span></span>  <span data-ttu-id="742ee-177">En la tabla siguiente se muestran los valores de elemento URI y los métodos asociados:</span><span class="sxs-lookup"><span data-stu-id="742ee-177">The URI element values and associated methods are listed in the following table:</span></span>  
  
|<span data-ttu-id="742ee-178">**Valor del elemento URI**</span><span class="sxs-lookup"><span data-stu-id="742ee-178">**URI Element Value**</span></span>|<span data-ttu-id="742ee-179">**Método**</span><span class="sxs-lookup"><span data-stu-id="742ee-179">**Method**</span></span>|  
|---------------------------|----------------|  
|<span data-ttu-id="742ee-180">lobhostname</span><span class="sxs-lookup"><span data-stu-id="742ee-180">lobhostname</span></span>|<span data-ttu-id="742ee-181">`System.Uri.Host%2A` para recuperar el nombre de host</span><span class="sxs-lookup"><span data-stu-id="742ee-181">`System.Uri.Host%2A` to retrieve the host name</span></span>|  
|<span data-ttu-id="742ee-182">Lobapplication</span><span class="sxs-lookup"><span data-stu-id="742ee-182">Lobapplication</span></span>|<span data-ttu-id="742ee-183">`System.Uri.AbsolutePath%2A` para recuperar el nombre de la aplicación de destino</span><span class="sxs-lookup"><span data-stu-id="742ee-183">`System.Uri.AbsolutePath%2A` to retrieve the target application name</span></span>|  
|<span data-ttu-id="742ee-184">enableAuthentation=false</span><span class="sxs-lookup"><span data-stu-id="742ee-184">enableAuthentation=false</span></span>|<span data-ttu-id="742ee-185">GetQueryStringValue("enableAuthentication")</span><span class="sxs-lookup"><span data-stu-id="742ee-185">GetQueryStringValue("enableAuthentication")</span></span><br /><br /> <span data-ttu-id="742ee-186">Utilice este elemento URI para validar las credenciales de usuario **Nota:** GetQueryStringValue es un método estático definido en el `Microsoft.ServiceModel.Channels.Common.ConnectionUri`</span><span class="sxs-lookup"><span data-stu-id="742ee-186">Use this URI element to validate user credentials **Note:**  GetQueryStringValue is a static method defined in the `Microsoft.ServiceModel.Channels.Common.ConnectionUri`</span></span>|  
|<span data-ttu-id="742ee-187">echoInUpperValue=false</span><span class="sxs-lookup"><span data-stu-id="742ee-187">echoInUpperValue=false</span></span>|<span data-ttu-id="742ee-188">GetQueryStringValue("echoInUpperValue")</span><span class="sxs-lookup"><span data-stu-id="742ee-188">GetQueryStringValue("echoInUpperValue")</span></span><br /><br /> <span data-ttu-id="742ee-189">Utilice este elemento URI para convertir la cadena de entrada en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="742ee-189">Use this URI element to convert the incoming string to upper case.</span></span>|  
  
### <a name="enableauthentication-uri-element"></a><span data-ttu-id="742ee-190">Elemento EnableAuthentication URI</span><span class="sxs-lookup"><span data-stu-id="742ee-190">EnableAuthentication URI Element</span></span>  
 <span data-ttu-id="742ee-191">El sistema de destino a menudo requiere que proporcione las credenciales de cliente para establecer una conexión con el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="742ee-191">Your target system often requires you to provide client credentials to establish a connection to the target system.</span></span> <span data-ttu-id="742ee-192">Como se ha mencionado, el adaptador de eco no implica ningún sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="742ee-192">As mentioned, the Echo adapter does not involve any target system.</span></span> <span data-ttu-id="742ee-193">Aunque como ejemplo, se muestra cómo usar un elemento URI personalizado denominado enableAuthentication para proporcionar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="742ee-193">Though as a sample, it shows how to use a custom URI element called enableAuthentication to provide the credentials.</span></span>  
  
```  
 public class EchoAdapterConnection : IConnection   
{  
….  
   public void Open(TimeSpan timeout)  
  {  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
  }  
}  
```  
  
 <span data-ttu-id="742ee-194">El código comprueba si enableAuthentication es true y si no se proporciona un nombre de usuario; Si no se proporciona un nombre de usuario, produce una excepción, que ha sido detectada por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta, tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="742ee-194">The code checks to see if enableAuthentication is true and if a user name is not provided; if a user name is not provided, it throws an exception, which is caught by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, as shown below:</span></span>  
  
 <span data-ttu-id="742ee-195">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/901095c7-c70d-491a-a1ae-8f37f22a61a7.gif "901095c7-c70d-491a-a1ae-8f37f22a61a7")</span><span class="sxs-lookup"><span data-stu-id="742ee-195">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/901095c7-c70d-491a-a1ae-8f37f22a61a7.gif "901095c7-c70d-491a-a1ae-8f37f22a61a7")</span></span>  
  
 <span data-ttu-id="742ee-196">Para proporcionar el nombre de usuario, se puede escribir en el cuadro de diálogo Configurar el adaptador el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta, como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="742ee-196">To provide the user name, you can enter it in the Configure Adapter dialog box in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, as shown in the following figure:</span></span>  
  
 <span data-ttu-id="742ee-197">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4069a7d-1403-4195-b0b5-21ad97dbc3ce.gif "e4069a7d-1403-4195-b0b5-21ad97dbc3ce")</span><span class="sxs-lookup"><span data-stu-id="742ee-197">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4069a7d-1403-4195-b0b5-21ad97dbc3ce.gif "e4069a7d-1403-4195-b0b5-21ad97dbc3ce")</span></span>  
  
### <a name="echoinuppercase-uri-element"></a><span data-ttu-id="742ee-198">Elemento EchoInUpperCase URI</span><span class="sxs-lookup"><span data-stu-id="742ee-198">EchoInUpperCase URI Element</span></span>  
 <span data-ttu-id="742ee-199">El elemento EchoInUpperCase URI puede hacer referencia como una marca booleana.</span><span class="sxs-lookup"><span data-stu-id="742ee-199">The EchoInUpperCase URI element can be referenced like a Boolean flag.</span></span> <span data-ttu-id="742ee-200">Si la marca es true, el adaptador convierte la cadena de entrada de la operación de EchoStrings a mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="742ee-200">If the flag is true, then the adapter converts the input string of the EchoStrings operation to uppercase.</span></span>  
  
 <span data-ttu-id="742ee-201">Para cambiar el valor predeterminado del elemento URI echoInUpperCase, use la ficha de propiedades del URI de configurar el adaptador en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="742ee-201">To change the default value of the echoInUpperCase URI element, use the URI Properties tab of the Configure Adapter in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], as shown below.</span></span>  
  
 <span data-ttu-id="742ee-202">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f22511b2-3fca-4875-ac65-8e61f4367e94.gif "f22511b2-3fca-4875-ac65-8e61f4367e94")</span><span class="sxs-lookup"><span data-stu-id="742ee-202">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f22511b2-3fca-4875-ac65-8e61f4367e94.gif "f22511b2-3fca-4875-ac65-8e61f4367e94")</span></span>  
  
## <a name="updating-echoadapterconnection"></a><span data-ttu-id="742ee-203">Actualizar EchoAdapterConnection</span><span class="sxs-lookup"><span data-stu-id="742ee-203">Updating EchoAdapterConnection</span></span>  
 <span data-ttu-id="742ee-204">Implemente el método IsValid, la apertura y el cierre de la clase EchoAdapterConnection.</span><span class="sxs-lookup"><span data-stu-id="742ee-204">You implement the IsValid, Open, and Close method of the EchoAdapterConnection class.</span></span>  
  
#### <a name="to-update-the-echoadapterconnection-class"></a><span data-ttu-id="742ee-205">Para actualizar la clase EchoAdapterConnection</span><span class="sxs-lookup"><span data-stu-id="742ee-205">To update the EchoAdapterConnection class</span></span>  
  
1.  <span data-ttu-id="742ee-206">En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterConnection.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="742ee-206">In **Solution Explorer**, double-click the **EchoAdapterConnection.cs** file.</span></span>  
  
2.  <span data-ttu-id="742ee-207">En el editor de Visual Studio, el botón secundario en cualquier lugar en el editor, en el menú contextual, seleccione **esquematización**y, a continuación, haga clic en **Detener esquematización**.</span><span class="sxs-lookup"><span data-stu-id="742ee-207">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  
  
3.  <span data-ttu-id="742ee-208">En el editor de Visual Studio, busque el **IsValid** método.</span><span class="sxs-lookup"><span data-stu-id="742ee-208">In the Visual Studio editor, find the **IsValid** method.</span></span> <span data-ttu-id="742ee-209">Dentro de la **IsValid** método, reemplace la implementación existente por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="742ee-209">Inside the **IsValid** method, replace the existing implementation with the one below:</span></span>  
  
    ```csharp  
    return true;  
    ```  
  
4.  <span data-ttu-id="742ee-210">En el editor de Visual Studio, busque el **abiertos** método.</span><span class="sxs-lookup"><span data-stu-id="742ee-210">In the Visual Studio editor, find the **Open** method.</span></span> <span data-ttu-id="742ee-211">Dentro de la **abiertos** método, reemplace la implementación existente con la siguiente implementación.</span><span class="sxs-lookup"><span data-stu-id="742ee-211">Inside the **Open** method, replace the existing implementation with the following implementation.</span></span> <span data-ttu-id="742ee-212">Esto muestra cómo utilizar el elemento de enableAuthentication URI para asegurarse de que se proporciona el nombre de usuario:</span><span class="sxs-lookup"><span data-stu-id="742ee-212">This shows you how to use the URI enableAuthentication element to ensure user  name is provided:</span></span>  
  
    ```csharp  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        // it just logs the credentials in the trace file  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
        // got the username, log it in trace file  
        EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Username is " + this.connectionFactory.ClientCredentials.UserName.UserName);  
    }  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully established!");  
    ```  
  
5.  <span data-ttu-id="742ee-213">En el editor de Visual Studio, busque el **cerrar** método.</span><span class="sxs-lookup"><span data-stu-id="742ee-213">In the Visual Studio editor, find the **Close** method.</span></span> <span data-ttu-id="742ee-214">Dentro de la **cerrar** método, agregue la siguiente instrucción única:</span><span class="sxs-lookup"><span data-stu-id="742ee-214">Inside the **Close** method, add the following single statement:</span></span>  
  
    ```csharp  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Close", "Connection successfully closed!");  
    ```  
  
## <a name="updating-the-echoadapterconnectionfactory"></a><span data-ttu-id="742ee-215">Actualizando el EchoAdapterConnectionFactory</span><span class="sxs-lookup"><span data-stu-id="742ee-215">Updating the EchoAdapterConnectionFactory</span></span>  
 <span data-ttu-id="742ee-216">Implemente el constructor de EchoAdapterConnectionFactory y agregar dos propiedades denominadas ClientCredentials y ConnectionUri.</span><span class="sxs-lookup"><span data-stu-id="742ee-216">You implement EchoAdapterConnectionFactory constructor, and add two properties called ClientCredentials and ConnectionUri.</span></span>  
  
#### <a name="to-update-the-echoadapterconnectionfactory-class"></a><span data-ttu-id="742ee-217">Para actualizar la clase EchoAdapterConnectionFactory</span><span class="sxs-lookup"><span data-stu-id="742ee-217">To update the EchoAdapterConnectionFactory class</span></span>  
  
1.  <span data-ttu-id="742ee-218">En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterConnectionFactory.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="742ee-218">In **Solution Explorer**, double-click the **EchoAdapterConnectionFactory.cs** file.</span></span>  
  
2.  <span data-ttu-id="742ee-219">En el editor de Visual Studio, el botón secundario en cualquier lugar en el editor, en el menú contextual, seleccione **esquematización**y, a continuación, haga clic en **Detener esquematización**.</span><span class="sxs-lookup"><span data-stu-id="742ee-219">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  
  
3.  <span data-ttu-id="742ee-220">En el editor de Visual Studio, busque el **campos privados** región.</span><span class="sxs-lookup"><span data-stu-id="742ee-220">In the Visual Studio editor, find the **Private Fields** region.</span></span> <span data-ttu-id="742ee-221">Agregue la siguiente instrucción única:</span><span class="sxs-lookup"><span data-stu-id="742ee-221">Add the following single statement:</span></span>  
  
    ```csharp  
    private EchoAdapterConnectionUri connectionUri;  
    ```  
  
     <span data-ttu-id="742ee-222">La lista de campos privados debe coincidir con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="742ee-222">Your list of private fields should match the following:</span></span>  
  
    ```csharp  
    // Stores the client credentials  
    private ClientCredentials clientCredentials;  
    // Stores the adapter class  
    private EchoAdapter adapter;  
    private EchoAdapterConnectionUri connectionUri;  
    ```  
  
4.  <span data-ttu-id="742ee-223">En el editor de Visual Studio, busque el **EchoAdapterConnectionFactory** método.</span><span class="sxs-lookup"><span data-stu-id="742ee-223">In the Visual Studio editor, find the **EchoAdapterConnectionFactory** method.</span></span> <span data-ttu-id="742ee-224">Dentro de la **EchoAdapterConnectionFactory** método de constructor, antes de "}", agregue la siguiente instrucción única como la última instrucción.</span><span class="sxs-lookup"><span data-stu-id="742ee-224">Inside the **EchoAdapterConnectionFactory** constructor method, before "}", add the following single statement as the last statement.</span></span>  
  
    ```csharp  
    this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    ```  
  
     <span data-ttu-id="742ee-225">La implementación de la **EchoAdapterConnectionFactory** método debe coincidir con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="742ee-225">The implementation of the **EchoAdapterConnectionFactory** method should match the following:</span></span>  
  
    ```csharp  
    /// <summary>  
    /// Initializes a new instance of the EchoAdapterConnectionFactory class  
    /// </summary>  
    public EchoAdapterConnectionFactory(ConnectionUri connectionUri  
        , ClientCredentials clientCredentials  
        , EchoAdapter adapter)  
    {  
        this.clientCredentials = clientCredentials;  
        this.adapter = adapter;  
        //added  
        this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    }  
    ```  
  
5.  <span data-ttu-id="742ee-226">En el editor de Visual Studio, busque el **propiedades públicas** región.</span><span class="sxs-lookup"><span data-stu-id="742ee-226">In the Visual Studio editor, find the **Public Properties** region.</span></span> <span data-ttu-id="742ee-227">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="742ee-227">Add the following code:</span></span>  
  
    ```csharp  
    /// <summary>  
    /// Returns the client credentials  
    /// </summary>  
    public ClientCredentials ClientCredentials  
    {  
        get  
        {  
            return this.clientCredentials;  
        }  
    }  
  
    /// <summary>  
    /// Returns the Connection Uri for this adapter  
    /// </summary>  
    public EchoAdapterConnectionUri ConnectionUri  
    {  
        get  
        {  
            return this.connectionUri;  
        }  
    }  
    ```  
  
## <a name="updating-the-echoadapterconnectionuri"></a><span data-ttu-id="742ee-228">Actualizando el EchoAdapterConnectionUri</span><span class="sxs-lookup"><span data-stu-id="742ee-228">Updating the EchoAdapterConnectionUri</span></span>  
 <span data-ttu-id="742ee-229">Implemente el constructor predeterminado de EchoAdapterConnectionUri, EchoAdapterConnectionUri(Uri uri) sobrecargar el constructor y el público invalidar la propiedad Uri Uri.</span><span class="sxs-lookup"><span data-stu-id="742ee-229">You implement the EchoAdapterConnectionUri default constructor, EchoAdapterConnectionUri(Uri uri) overloaded constructor, and the public override Uri Uri property.</span></span>  
  
#### <a name="to-update-the-echoadapterconnectionuri-class"></a><span data-ttu-id="742ee-230">Para actualizar la clase EchoAdapterConnectionUri</span><span class="sxs-lookup"><span data-stu-id="742ee-230">To update the EchoAdapterConnectionUri class</span></span>  
  
1.  <span data-ttu-id="742ee-231">En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterConnectionUri.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="742ee-231">In **Solution Explorer**, double-click the **EchoAdapterConnectionUri.cs** file.</span></span>  
  
2.  <span data-ttu-id="742ee-232">En el editor de Visual Studio, el botón secundario en cualquier lugar en el editor, en el menú contextual, seleccione **esquematización**y, a continuación, haga clic en **Detener esquematización**.</span><span class="sxs-lookup"><span data-stu-id="742ee-232">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  
  
3.  <span data-ttu-id="742ee-233">En el editor de Visual Studio, busque el **constructores** región.</span><span class="sxs-lookup"><span data-stu-id="742ee-233">In the Visual Studio editor, find the **Constructors** region.</span></span> <span data-ttu-id="742ee-234">Dentro de la **EchoAdapterConnectionUri()** un constructor predeterminado, agregue la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="742ee-234">Inside the **EchoAdapterConnectionUri()** default constructor, add the following statement:</span></span>  
  
    ```csharp  
    Uri = new Uri("echov2://lobhostname/lobapplication?enableauthentication=False");  
    ```  
  
4.  <span data-ttu-id="742ee-235">En el editor de Visual Studio, dentro de la **EchoAdapterConnectionUri (Uri uri)** sobrecarga de constructor y agregue la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="742ee-235">In the Visual Studio editor, inside the **EchoAdapterConnectionUri(Uri uri)** overloaded constructor, and add the following statement:</span></span>  
  
    ```csharp  
    Uri = uri;  
    ```  
  
     <span data-ttu-id="742ee-236">La implementación del método EchoAdapterConnectionUri(Uri uri) debe coincidir con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="742ee-236">Your implementation of the EchoAdapterConnectionUri(Uri uri) method should match the following:</span></span>  
  
    ```csharp  
    public EchoAdapterConnectionUri(Uri uri)  
        : base()  
    {  
        Uri = uri;  
    }  
    ```  
  
5.  <span data-ttu-id="742ee-237">En el editor de Visual Studio, dentro de la **público invalidar Uri Uri** (método), reemplazar el existente con la lógica siguiente.</span><span class="sxs-lookup"><span data-stu-id="742ee-237">In the Visual Studio editor, inside the **public override Uri Uri** method, replace the existing with the following logic.</span></span> <span data-ttu-id="742ee-238">Get basa el Uri con echoInUpperCase o sin él.</span><span class="sxs-lookup"><span data-stu-id="742ee-238">The get builds the Uri with echoInUpperCase or without it.</span></span> <span data-ttu-id="742ee-239">El conjunto analiza el URI para recuperar el nombre de host, nombre de base de datos y valores de la consulta.</span><span class="sxs-lookup"><span data-stu-id="742ee-239">The set parses the URI to retrieve host name, database name, and query values.</span></span>  
  
    ```csharp  
    get  
    {  
        // Build the uri  
        if (String.IsNullOrEmpty(this.hostname)) throw new InvalidUriException("Invalid target system host name.");  
        if (String.IsNullOrEmpty(this.application)) throw new InvalidUriException("Invalid target system data source name.");  
        if (EchoInUpperCase)  
        {  
            // build the uri with echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication + "&" + "echoInUpperCase=" + echoInUpperCase);  
        }  
        else  
        {  
            // build the uri without echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication);  
        }  
    }  
    set  
    {  
        // Parse the uri  
        String[] enableAuthValue = GetQueryStringValue(value, "enableAuthentication");  
        if (enableAuthValue.Length > 0) this.enableAuthentication = Boolean.Parse(enableAuthValue[0]);  
        String[] echoInUpperValue = GetQueryStringValue(value, "echoInUpperCase");  
        if (echoInUpperValue.Length > 0) this.echoInUpperCase = Boolean.Parse(echoInUpperValue[0]);  
  
        this.hostname = value.Host;  
        String[] applicationValue = value.AbsolutePath.Split('/');  
        if (applicationValue.Length > 1) this.Application = applicationValue[1];  
    }  
    ```  
  
6.  <span data-ttu-id="742ee-240">En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="742ee-240">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
7.  <span data-ttu-id="742ee-241">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="742ee-241">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="742ee-242">Debe compilar correctamente el proyecto.</span><span class="sxs-lookup"><span data-stu-id="742ee-242">You should successfully compile the project.</span></span> <span data-ttu-id="742ee-243">Si no es así, asegúrese de que ha seguido todos los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="742ee-243">If not, ensure that you have followed every step above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="742ee-244">Ya ha guardado su trabajo.</span><span class="sxs-lookup"><span data-stu-id="742ee-244">You saved your work.</span></span> <span data-ttu-id="742ee-245">Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 4: implementar el controlador de examinar de metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="742ee-245">You can safely close Visual Studio at this time or go to the next step, [Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="742ee-246">¿Simplemente lo que hacía?</span><span class="sxs-lookup"><span data-stu-id="742ee-246">What Did I Just Do?</span></span>  
 <span data-ttu-id="742ee-247">Implementa la conexión para el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="742ee-247">You implemented the connection for the Echo adapter.</span></span> <span data-ttu-id="742ee-248">Ha aprendido los componentes de conexión de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], la estructura básica del URI de conexión, cómo analizar mediante programación los elementos del identificador URI y cómo puede usar el elemento URI para cambiar la función de adaptador.</span><span class="sxs-lookup"><span data-stu-id="742ee-248">You learned the connection components of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], the basic structure of the connection URI, how to programmatically parse the URI elements, and how you can use the URI element to change the adapter feature.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="742ee-249">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="742ee-249">Next Steps</span></span>  
 <span data-ttu-id="742ee-250">Implementar metadatos exploración, búsqueda y resolviendo las capacidades y el intercambio de mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="742ee-250">You implement metadata browsing, searching, and resolving capabilities, and the outbound message exchange.</span></span> <span data-ttu-id="742ee-251">Por último, generar e implementar el adaptador.</span><span class="sxs-lookup"><span data-stu-id="742ee-251">Finally, you build and deploy the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="742ee-252">Vea también</span><span class="sxs-lookup"><span data-stu-id="742ee-252">See Also</span></span>  
 <span data-ttu-id="742ee-253">[Paso 4: Implementar el controlador de exploración de metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="742ee-253">[Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="742ee-254">Tutorial 1: Desarrollar el adaptador de Echo</span><span class="sxs-lookup"><span data-stu-id="742ee-254">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)