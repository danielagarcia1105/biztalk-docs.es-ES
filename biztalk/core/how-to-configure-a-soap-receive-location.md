---
title: Cómo configurar ubicación de recepción de SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], virtual directories
- SOAP adapters, code samples
- configuring [SOAP adapters], receive locations
- virtual directories, SOAP adapters
- SOAP adapters, receive locations
- code samples, SOAP adapters
- configuring [SOAP adapters], code samples
- SOAP adapters, virtual directories
- receive locations, SOAP adapters
ms.assetid: 7e348409-9181-47e4-b3c0-c73eb2acffa3
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4de95a4d414cddde0812f590c84c237866772741
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999269"
---
# <a name="how-to-configure-a-soap-receive-location"></a><span data-ttu-id="fc368-102">Cómo configurar una ubicación de recepción de SOAP</span><span class="sxs-lookup"><span data-stu-id="fc368-102">How to Configure a SOAP Receive Location</span></span>
<span data-ttu-id="fc368-103">Puede configurar una ubicación de recepción SOAP mediante programación o con la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc368-103">You can configure a SOAP receive location either programmatically or by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

 <span data-ttu-id="fc368-104">**Cómo configurar un ubicación de recepción SOAP mediante programación**</span><span class="sxs-lookup"><span data-stu-id="fc368-104">**How to Configure a SOAP Receive Location Programmatically**</span></span>  

 <span data-ttu-id="fc368-105">El modelo de objetos para el Explorador de BizTalk permite crear y configurar ubicaciones de recepción mediante programación.</span><span class="sxs-lookup"><span data-stu-id="fc368-105">The BizTalk Explorer object model enables you to create and configure receive locations programmatically.</span></span> <span data-ttu-id="fc368-106">El modelo de objetos del explorador de BizTalk expone la**IReceiveLocation** recibir de la interfaz de configuración de ubicación que tenga un **TransportTypeData** propiedad de lectura/escritura.</span><span class="sxs-lookup"><span data-stu-id="fc368-106">The BizTalk Explorer object model exposes the**IReceiveLocation** receive location configuration interface that has a **TransportTypeData** read/write property.</span></span> <span data-ttu-id="fc368-107">Esta propiedad acepta una bolsa de propiedades de configuración de ubicación de recepción SOAP con formato de un par de nombre y valor de cadenas XML.</span><span class="sxs-lookup"><span data-stu-id="fc368-107">This property accepts a SOAP receive location configuration property bag in the form of a name-value pair of XML strings.</span></span> <span data-ttu-id="fc368-108">Para establecer esta propiedad en el modelo de objetos del explorador de BizTalk, debe establecer el **InboundTransportLocation** propiedad de la **IReceiveLocation** interfaz.</span><span class="sxs-lookup"><span data-stu-id="fc368-108">To set this property in the BizTalk Explorer object model, you must set the **InboundTransportLocation** property of the **IReceiveLocation** interface.</span></span>  

 <span data-ttu-id="fc368-109">El **TransportTypeData** propiedad de la **IReceiveLocation** interfaz no tiene que establecerse.</span><span class="sxs-lookup"><span data-stu-id="fc368-109">The **TransportTypeData** property of the **IReceiveLocation** interface does not have to be set.</span></span> <span data-ttu-id="fc368-110">Si no se establece, el adaptador de SOAP utiliza los valores predeterminados de la configuración de ubicación de recepción SOAP que se incluyen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="fc368-110">If it is not set, the SOAP adapter uses the default values for the SOAP receive location configuration as indicated in the following table.</span></span>  

 <span data-ttu-id="fc368-111">La siguiente tabla enumera las propiedades de configuración que se pueden establecer en el modelo de objetos del Explorador de BizTalk para la ubicación de recepción SOAP.</span><span class="sxs-lookup"><span data-stu-id="fc368-111">The following table lists the configuration properties that you can set in the BizTalk Explorer object model for the SOAP receive location.</span></span>  

|<span data-ttu-id="fc368-112">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="fc368-112">Property name</span></span>|<span data-ttu-id="fc368-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="fc368-113">Type</span></span>|<span data-ttu-id="fc368-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc368-114">Description</span></span>|  
|-------------------|----------|-----------------|  
|<span data-ttu-id="fc368-115">**IDENTIFICADOR URI**</span><span class="sxs-lookup"><span data-stu-id="fc368-115">**URI**</span></span>|<span data-ttu-id="fc368-116">String</span><span class="sxs-lookup"><span data-stu-id="fc368-116">String</span></span>|<span data-ttu-id="fc368-117">Directorio virtual que contiene el servicio Web en el servidor de implementación.</span><span class="sxs-lookup"><span data-stu-id="fc368-117">Virtual directory containing the Web service on the deployment server.</span></span>|  
|<span data-ttu-id="fc368-118">**AddressableURI**</span><span class="sxs-lookup"><span data-stu-id="fc368-118">**AddressableURI**</span></span>|<span data-ttu-id="fc368-119">String</span><span class="sxs-lookup"><span data-stu-id="fc368-119">String</span></span>|<span data-ttu-id="fc368-120">Campo de dirección pública que contiene la dirección URL completa a la que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="fc368-120">Public address field containing the entire, callable URL.</span></span><br /><br /> <span data-ttu-id="fc368-121">Valor predeterminado: en blanco</span><span class="sxs-lookup"><span data-stu-id="fc368-121">Default value: Blank</span></span>|  
|<span data-ttu-id="fc368-122">**UseSSO**</span><span class="sxs-lookup"><span data-stu-id="fc368-122">**UseSSO**</span></span>|<span data-ttu-id="fc368-123">Boolean</span><span class="sxs-lookup"><span data-stu-id="fc368-123">Boolean</span></span>|<span data-ttu-id="fc368-124">Especifica si el adaptador de SOAP emite el vale de inicio de sesión único para los mensajes que llegan a esta ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="fc368-124">Specifies whether the SOAP adapter issues the Single Sign-On ticket to the messages that arrive on this receive location.</span></span><br /><br /> <span data-ttu-id="fc368-125">Valor predeterminado: False</span><span class="sxs-lookup"><span data-stu-id="fc368-125">Default value: False</span></span>|  

 <span data-ttu-id="fc368-126">Utilice el siguiente formato para establecer las propiedades:</span><span class="sxs-lookup"><span data-stu-id="fc368-126">Use the following format to set the properties:</span></span>  

```  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
```  

 <span data-ttu-id="fc368-127">El **URI** y **AddressableURI** propiedades se establecen mediante el **dirección** y **PublicAddress** propiedades de la ubicación de recepción objeto.</span><span class="sxs-lookup"><span data-stu-id="fc368-127">The **URI** and **AddressableURI** properties are set using the **Address** and **PublicAddress** properties of the receive location object.</span></span>  

 <span data-ttu-id="fc368-128">El siguiente fragmento de código muestra la creación de una ubicación de recepción SOAP:</span><span class="sxs-lookup"><span data-stu-id="fc368-128">The following code fragment illustrates creating a SOAP receive location:</span></span>  

```  
// Use BizTalk Explorer object model to create new SOAP receive location.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  

// Add a new Request-Response port  
ReceivePort receivePort = explorer.AddNewReceivePort(true);  
receivePort.Name = "SampleReceivePort";  
receivePort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  

// Add primary SOAP receive location  
ReceiveLocation receiveLocation = receivePort.AddNewReceiveLocation();  
receiveLocation.Name = "SampleReceiveLocation";  
receiveLocation.Address = "/PurchaseOrder/POOrchestration.asmx";  
receiveLocation.TransportType = explorer.ProtocolTypes["SOAP"];  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
receiveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
foreach (ReceiveHandler receiveHandler in explorer.ReceiveHandlers)  
{  
if (receiveHandler.TransportType.Name == receiveLocation.TransportType.Name)  
{  
receiveLocation.ReceiveHandler = receiveHandler;   
}  
}  

// Save  
explorer.SaveChanges();   
```  

 <span data-ttu-id="fc368-129">**Cómo configurar un SOAP ubicación de recepción con la consola de administración de BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="fc368-129">**How to Configure a SOAP Receive Location with the BizTalk Server Administration Console**</span></span>  

 <span data-ttu-id="fc368-130">Puede establecer variables de adaptador de ubicación de recepción SOAP en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc368-130">You can set SOAP receive location adapter variables in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="fc368-131">Si no hay propiedades establecidas en la ubicación de recepción, se usarán los valores predeterminados del controlador de recepción establecidos en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc368-131">If properties are not set in the receive location, the default receive handler values set in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console are used.</span></span>  

> [!NOTE]
>  <span data-ttu-id="fc368-132">Antes de realizar los siguientes procedimientos, debe haber agregado un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="fc368-132">Before completing the following procedures you must have already added a receive port.</span></span> <span data-ttu-id="fc368-133">Para obtener más información, consulte [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).</span><span class="sxs-lookup"><span data-stu-id="fc368-133">For more information, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span>  

### <a name="to-configure-variables-for-a-soap-receive-location"></a><span data-ttu-id="fc368-134">Para configurar variables para una ubicación de recepción SOAP</span><span class="sxs-lookup"><span data-stu-id="fc368-134">To configure variables for a SOAP receive location</span></span>  

1. <span data-ttu-id="fc368-135">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el aplicación que desea crear una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="fc368-135">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application you want to create a receive location in.</span></span>  

2. <span data-ttu-id="fc368-136">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en el panel izquierdo, haga clic en el **puerto de recepción** nodo.</span><span class="sxs-lookup"><span data-stu-id="fc368-136">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, in the left pane, click the **Receive Port** node.</span></span> <span data-ttu-id="fc368-137">A continuación, en el panel de la derecha, haga clic con el botón secundario en el puerto de recepción asociado con una ubicación de recepción existente o que desee asociar con una nueva ubicación de recepción. A continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fc368-137">Then in the right pane, right-click the receive port that is associated with an existing receive location or that you want to associate with a new receive location, and then click **Properties**.</span></span>  

3. <span data-ttu-id="fc368-138">En el **propiedades de puerto de recepción** cuadro de diálogo, en el panel izquierdo, seleccione **ubicaciones de recepción**y, a continuación, en el panel derecho, haga doble clic en una existente, ubicación de recepción o haga clic en **New**para crear una nueva ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="fc368-138">In the **Receive Port Properties** dialog box, in the left pane, select **Receive Locations**, and then in the right pane, double-click an existing receive location or click **New**to create a new receive location.</span></span>  

4. <span data-ttu-id="fc368-139">En el **propiedades de ubicación de recepción** cuadro de diálogo el **transporte** junto a la sección **tipo**, seleccione **SOAP** en la lista desplegable, y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="fc368-139">In the **Receive Location Properties** dialog box, in the **Transport** section next to **Type**, select **SOAP** from the drop-down list, and then click **Configure**.</span></span>  

5. <span data-ttu-id="fc368-140">En el **propiedades de transporte SOAP** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc368-140">In the **SOAP Transport Properties** dialog box, do the following:</span></span>  


   |                     <span data-ttu-id="fc368-141">Use</span><span class="sxs-lookup"><span data-stu-id="fc368-141">Use this</span></span>                      |                                                                                                                                                                                                                                                                                                              <span data-ttu-id="fc368-142">Para</span><span class="sxs-lookup"><span data-stu-id="fc368-142">To do this</span></span>                                                                                                                                                                                                                                                                                                               |
   |---------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="fc368-143">**Directorio virtual más archivo .asmx de servicio Web**</span><span class="sxs-lookup"><span data-stu-id="fc368-143">**Virtual directory plus Web Service .asmx file**</span></span> |                                                                                                                 <span data-ttu-id="fc368-144">Indicar el archivo .asmx creado por el Asistente para publicación de servicios Web de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fc368-144">Indicate the .asmx file created by the BizTalk Web Services Publishing Wizard.</span></span><br /><br /> <span data-ttu-id="fc368-145">El formato del mensaje es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc368-145">The format of this message is similar to the following:</span></span><br /><br /> <span data-ttu-id="fc368-146">/PurchaseOrder/POOrchestration.asmx</span><span class="sxs-lookup"><span data-stu-id="fc368-146">/PurchaseOrder/POOrchestration.asmx</span></span><br /><br /> <span data-ttu-id="fc368-147">Donde es la ubicación completa del archivo .asmx http://localhost/PurchaseOrder/POOrchestration.asmx.</span><span class="sxs-lookup"><span data-stu-id="fc368-147">Where the full location of the .asmx file is http://localhost/PurchaseOrder/POOrchestration.asmx.</span></span> <span data-ttu-id="fc368-148">**Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="fc368-148">**Note:**  The URI for a send port or receive location cannot exceed 256 characters.</span></span>                                                                                                                 |
   |                <span data-ttu-id="fc368-149">**Dirección pública**</span><span class="sxs-lookup"><span data-stu-id="fc368-149">**Public address**</span></span>                 | <span data-ttu-id="fc368-150">Especificar el URI completo de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="fc368-150">Specify the fully qualified URI for this receive location.</span></span> <span data-ttu-id="fc368-151">El valor de esta propiedad es una combinación del nombre del servidor y el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="fc368-151">The value for this property is a combination of the server name and the virtual directory.</span></span> <span data-ttu-id="fc368-152">El URI especificado debe designar la dirección URL del sitio web público para que los socios comerciales se conecten cuando envíen mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc368-152">The specified URI should designate the public Web site URL for trading partners to connect to when sending messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="fc368-153">Esta información es opcional y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no la usa.</span><span class="sxs-lookup"><span data-stu-id="fc368-153">This information is optional and is not used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="fc368-154">Este parámetro está disponible para permitir a los administradores documentar la dirección URL pública a la que está vinculada la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="fc368-154">This parameter is available to allow administrators to document the public URL that the receive location is tied to.</span></span> |
   |              <span data-ttu-id="fc368-155">**Uso del inicio de sesión único**</span><span class="sxs-lookup"><span data-stu-id="fc368-155">**Use Single Sign-On**</span></span>               |                                                                                                                                                                                                 <span data-ttu-id="fc368-156">Indicar que el adaptador de SOAP utilice el inicio de sesión único (SSO) empresarial.</span><span class="sxs-lookup"><span data-stu-id="fc368-156">Indicate that the SOAP adapter uses Enterprise Single Sign-On.</span></span> <span data-ttu-id="fc368-157">**Nota:** el Asistente para publicar servicios Web de BizTalk permite utilizar SharePoint Portal Server Single Sign-On; esta propiedad solo habilita Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="fc368-157">**Note:**  The BizTalk Web Services Publishing Wizard allows you to use SharePoint Portal Server Single Sign-On; this property only enables Enterprise Single Sign-On.</span></span>                                                                                                                                                                                                 |


6. <span data-ttu-id="fc368-158">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fc368-158">Click **OK**.</span></span>  

7. <span data-ttu-id="fc368-159">En el **propiedades de ubicación de recepción** diálogo cuadro, escriba los valores adecuados para completar la configuración de la ubicación de recepción y, a continuación, haga clic en **Aceptar** para guardar la configuración.</span><span class="sxs-lookup"><span data-stu-id="fc368-159">In the **Receive Location Properties** dialog box, enter the appropriate values to complete the configuration of the receive location, and then click **OK** to save settings.</span></span> <span data-ttu-id="fc368-160">Para obtener información sobre la **propiedades de las ubicaciones de recepción** cuadro de diálogo, vea [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="fc368-160">For information about the **Receive Locations Properties** dialog box, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  

   <span data-ttu-id="fc368-161">La configuración de seguridad que utiliza la ubicación de recepción SOAP se establece en IIS.</span><span class="sxs-lookup"><span data-stu-id="fc368-161">The security settings used by the SOAP receive location are set in IIS.</span></span> <span data-ttu-id="fc368-162">De forma predeterminada, la ubicación de recepción SOAP no está establecida para usar autenticación anónima.</span><span class="sxs-lookup"><span data-stu-id="fc368-162">By default, the SOAP receive location is not set to use anonymous authentication.</span></span>  

   <span data-ttu-id="fc368-163">Si bien el cliente SOAP llama al servicio Web, el adaptador de SOAP autentica el cliente SOAP usando autenticación anónima, básica, implícita o integrada de Windows.</span><span class="sxs-lookup"><span data-stu-id="fc368-163">While the SOAP client calls the Web service, the SOAP adapter authenticates the SOAP client by using either Anonymous, Basic, Digest, or Windows Integrated authentication.</span></span> <span data-ttu-id="fc368-164">Si se comprueba el usuario, se pasa el contexto del usuario al controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="fc368-164">If the user is verified, the user context is passed to the receive handler.</span></span>  

> [!NOTE]
>  <span data-ttu-id="fc368-165">No será válida ninguna configuración de IIS que haga que SOAP y HTTP compartan el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="fc368-165">Any IIS configuration that leads to SOAP and HTTP sharing the same process is not valid.</span></span> <span data-ttu-id="fc368-166">Sólo puede haber un receptor aislado por proceso.</span><span class="sxs-lookup"><span data-stu-id="fc368-166">You can have only one isolated receiver per process.</span></span>  

### <a name="to-update-a-virtual-directory-to-use-aspnet-40"></a><span data-ttu-id="fc368-167">Para actualizar un directorio virtual con el fin de usar ASP.NET 4.0</span><span class="sxs-lookup"><span data-stu-id="fc368-167">To update a virtual directory to use ASP.NET 4.0</span></span>  

1.  <span data-ttu-id="fc368-168">Inicie el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="fc368-168">Launch the Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="fc368-169">Haga clic en **iniciar**, haga clic en **todos los programas**y haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="fc368-169">Click **Start**, click **All Programs**, and click **Internet Information Services (IIS) Manager**.</span></span>  

2.  <span data-ttu-id="fc368-170">Si necesita conectarse a un servidor IIS remoto, haga clic la **Internet Information Services** nodo y, a continuación, haga clic en **Connect**.</span><span class="sxs-lookup"><span data-stu-id="fc368-170">If you need to connect to a remote IIS server, right click the **Internet Information Services** node and then click **Connect**.</span></span>  

3.  <span data-ttu-id="fc368-171">Escriba el nombre de equipo del servidor IIS remoto y las credenciales si es necesario.</span><span class="sxs-lookup"><span data-stu-id="fc368-171">Type the computer name for the remote IIS server and credentials if necessary.</span></span>  

4.  <span data-ttu-id="fc368-172">Expanda el nombre del servidor que aloja el sitio Web o el directorio virtual que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="fc368-172">Expand the server name that houses the Web site or virtual directory to be updated.</span></span>  

5.  <span data-ttu-id="fc368-173">Expanda **sitios**.</span><span class="sxs-lookup"><span data-stu-id="fc368-173">Expand **Sites**.</span></span>  

6.  <span data-ttu-id="fc368-174">Expanda **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="fc368-174">Expand **Default Web Site**.</span></span>  

7.  <span data-ttu-id="fc368-175">Expanda el sitio web predeterminado para ver los directorios virtuales que contiene.</span><span class="sxs-lookup"><span data-stu-id="fc368-175">Expand the Default Web site to view the virtual directories under the Web site.</span></span>  

8.  <span data-ttu-id="fc368-176">Haga clic en el directorio virtual que desea actualizar para usar ASP.NET 4.0, haga clic en **administrar aplicación**y, a continuación, haga clic en **configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="fc368-176">Right-click the virtual directory that you want to update to use ASP.NET 4.0, click **Manage Application**, and then click **Advanced Settings**.</span></span> <span data-ttu-id="fc368-177">El **AppPool** campo muestra el grupo de aplicaciones definido para el directorio virtual seleccionado.</span><span class="sxs-lookup"><span data-stu-id="fc368-177">The **Application Pool** field displays the application pool set for the selected virtual directory.</span></span> <span data-ttu-id="fc368-178">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fc368-178">Click **OK**.</span></span>  

9. <span data-ttu-id="fc368-179">En la ventana del Administrador de Internet Information Services (IIS), haga clic en **grupos de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="fc368-179">In the Internet Information Services (IIS) Manager window, click **Application Pools**.</span></span> <span data-ttu-id="fc368-180">El panel de detalles muestra una lista de grupos de aplicaciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="fc368-180">The details pane displays a list of application pools on the server.</span></span>  

10. <span data-ttu-id="fc368-181">Haga clic en el grupo de aplicaciones establecido en el paso 8 y, a continuación, haga clic en **configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="fc368-181">Right-click the application pool set in step 8, and then click **Basic Settings**.</span></span>  

11. <span data-ttu-id="fc368-182">En el **Modificar grupo de aplicaciones** diálogo cuadro, cambie lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc368-182">In the **Edit Application Pool** dialog box, change the following:</span></span>  

    -   <span data-ttu-id="fc368-183">**Versión de .NET framework** a **4.0**</span><span class="sxs-lookup"><span data-stu-id="fc368-183">**.NET Framework version** to **4.0**</span></span>  

    -   <span data-ttu-id="fc368-184">**Modo de canalización administrada** a **clásico**</span><span class="sxs-lookup"><span data-stu-id="fc368-184">**Managed pipeline mode** to **Classic**</span></span>  

12. <span data-ttu-id="fc368-185">Haga clic en **Aceptar** para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="fc368-185">Click **OK** to apply the changes.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fc368-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc368-186">See Also</span></span>  
 [<span data-ttu-id="fc368-187">Consumo de servicios web</span><span class="sxs-lookup"><span data-stu-id="fc368-187">Consuming Web Services</span></span>](../core/consuming-web-services.md)