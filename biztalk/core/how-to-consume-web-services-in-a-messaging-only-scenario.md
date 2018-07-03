---
title: Cómo consumir Web Services en un escenario únicamente de mensajería | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66873959-5b1b-4d9b-ad19-f083670420b8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71d1e38305fd5b798a2fa8dd59fc6341dc806dfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985453"
---
# <a name="how-to-consume-web-services-in-a-messaging-only-scenario"></a><span data-ttu-id="08971-102">Cómo consumir servicios web en un escenario únicamente de mensajería</span><span class="sxs-lookup"><span data-stu-id="08971-102">How to Consume Web Services in a Messaging Only Scenario</span></span>
<span data-ttu-id="08971-103">Una de las nuevas mejoras del adaptador de SOAP es la capacidad de para llamar a los servicios Web en un escenario únicamente de mensajería mediante el uso de puertos de envío de enrutamiento basados en el contenido.</span><span class="sxs-lookup"><span data-stu-id="08971-103">One of the new enhancements for the SOAP adapter is ability to call Web services in a messaging only scenario by using content-based routing send ports.</span></span> <span data-ttu-id="08971-104">Esta característica hace posible la consumición de servicios Web sin crear orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="08971-104">This feature makes it possible to consume Web services without creating orchestrations.</span></span> <span data-ttu-id="08971-105">Además, proporciona un mayor rendimiento para consumir servicios Web, ya que los mensajes no pasan a través de las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="08971-105">It also provides better performance to consume Web services because messages do not pass through orchestrations.</span></span>  
  
 <span data-ttu-id="08971-106">Para consumir servicios Web en un escenario únicamente de mensajería, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08971-106">To consume Web services in a messaging only scenario, do the following:</span></span>  
  
-   <span data-ttu-id="08971-107">Crear una biblioteca de proxy y esquemas XML para la invocación de servicios Web</span><span class="sxs-lookup"><span data-stu-id="08971-107">Create a proxy library and XML schemas for invoking Web services</span></span>  
  
-   <span data-ttu-id="08971-108">Configurar un puerto de envío y una ubicación de recepción para consumir un servicio Web</span><span class="sxs-lookup"><span data-stu-id="08971-108">Configure a send port and receive location for consuming a Web service</span></span>  
  
### <a name="to-create-a-proxy-library-and-xml-schemas-for-invoking-web-services"></a><span data-ttu-id="08971-109">Para crear una biblioteca de proxy y esquemas XML para invocar servicios Web</span><span class="sxs-lookup"><span data-stu-id="08971-109">To create a proxy library and XML schemas for invoking Web services</span></span>  
  
1. <span data-ttu-id="08971-110">Determine la dirección URL del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="08971-110">Determine the URL for the Web service.</span></span>  
  
2. <span data-ttu-id="08971-111">Abra un **proyecto vacío de servidor BizTalk** en un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="08971-111">Open an **Empty BizTalk Server Project** in a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] solution.</span></span> <span data-ttu-id="08971-112">Para obtener más información sobre cómo crear un proyecto de BizTalk Server, consulte [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md).</span><span class="sxs-lookup"><span data-stu-id="08971-112">For more information about how to create a BizTalk Server project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="08971-113">Este tutorial usa un proyecto de BizTalk Server para generar bibliotecas proxy y esquemas XML que usa el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="08971-113">This walkthrough uses a BizTalk Server project to generate proxy libraries and XML schemas that the Web service uses.</span></span> <span data-ttu-id="08971-114">Además, puede usar Wsdl.exe y Xsd.exe en el SDK de .NET Framework 4.0 con el mismo fin.</span><span class="sxs-lookup"><span data-stu-id="08971-114">You can also use the Wsdl.exe and Xsd.exe in the .NET Framework 4.0 SDK for the same purpose.</span></span>  
  
3. <span data-ttu-id="08971-115">En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk Server y, a continuación, haga clic en **Add Service Reference**.</span><span class="sxs-lookup"><span data-stu-id="08971-115">In Solution Explorer, right-click the BizTalk Server project name, and then click **Add Service Reference**.</span></span>  
  
4. <span data-ttu-id="08971-116">En el **Add Service Reference** cuadro de diálogo, haga clic en **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="08971-116">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
5. <span data-ttu-id="08971-117">En el **configuración de referencia de servicio** cuadro de diálogo, haga clic en **Agregar referencia Web** en el **compatibilidad** sección.</span><span class="sxs-lookup"><span data-stu-id="08971-117">In the **Service Reference Settings** dialog box, Click **Add Web Reference** in the **Compatibility** section.</span></span>  
  
6. <span data-ttu-id="08971-118">En el **Agregar referencia Web** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08971-118">In the **Add Web Reference** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="08971-119">En el **URL** campo, escriba una dirección URL del servicio Web y, a continuación, haga clic en **vaya**.</span><span class="sxs-lookup"><span data-stu-id="08971-119">In the **URL** field, type a Web service URL, and then click **Go**.</span></span>  
  
   2.  <span data-ttu-id="08971-120">En el **nombre de referencia Web** campo, escriba un nombre para el espacio de nombres y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="08971-120">In the **Web reference name** field, type a name for the namespace, and then click **Add Reference**.</span></span>  
  
7. <span data-ttu-id="08971-121">La referencia Web aparecerá en **referencias Web** nodo en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="08971-121">The Web reference will appear under **Web References** node in Solution Explorer.</span></span>  
  
   > [!TIP]
   >  <span data-ttu-id="08971-122">Una vez que tenga una referencia web que se agrega a un proyecto de BizTalk, el **Agregar referencia Web** comando está directamente disponible cuando hace clic en el nombre del proyecto o **referencias** o **referencias Web**.</span><span class="sxs-lookup"><span data-stu-id="08971-122">Once you have a web reference added to a BizTalk project, the **Add Web Reference** command is directly available when you right-click the project name or **References** or **Web References**.</span></span>  
  
8. <span data-ttu-id="08971-123">En el Explorador de soluciones, haga clic en el nombre del proyecto y, a continuación, haga clic en **propiedades** para iniciar el Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="08971-123">In Solution Explorer, right-click the project name, and then click **Properties** to launch the Project Designer.</span></span>  
  
9. <span data-ttu-id="08971-124">En el Diseñador de proyectos, haga clic en el **firma** ficha.</span><span class="sxs-lookup"><span data-stu-id="08971-124">In the Project Designer, click the **Signing** tab.</span></span>  
  
10. <span data-ttu-id="08971-125">Seleccione **firmar el ensamblado** opción, haga clic en la lista desplegable para la **elegir un archivo de clave de nombre seguro**y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="08971-125">Select **Sign the assembly** option, click the drop-down list for the **Choose a strong name key file**, and then click **Browse**.</span></span>  
  
11. <span data-ttu-id="08971-126">Busque y seleccione el archivo de clave de ensamblado y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="08971-126">Browse and select the assembly key file, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="08971-127">En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Versión de compilación**.</span><span class="sxs-lookup"><span data-stu-id="08971-127">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
13. <span data-ttu-id="08971-128">En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="08971-128">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>  
  
### <a name="to-configure-a-send-port-and-receive-location-for-consuming-a-web-service"></a><span data-ttu-id="08971-129">Para configurar un puerto de envío y una ubicación de recepción para consumir un servicio Web</span><span class="sxs-lookup"><span data-stu-id="08971-129">To configure a send port and receive location for consuming a Web service</span></span>  
  
1.  <span data-ttu-id="08971-130">En la Consola de administración de BizTalk Server, cree un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="08971-130">In the BizTalk Server Administration console, create a send port.</span></span> <span data-ttu-id="08971-131">Para obtener más información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).</span><span class="sxs-lookup"><span data-stu-id="08971-131">For more information, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="08971-132">Al crear el puerto de envío, seleccione SOAP como tipo o protocolo de transporte.</span><span class="sxs-lookup"><span data-stu-id="08971-132">When creating the send port, select SOAP as the transport type or transport protocol.</span></span>  
  
2.  <span data-ttu-id="08971-133">Configure el puerto de envío de SOAP con los siguientes valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="08971-133">Configure the SOAP send port with the following settings.</span></span> <span data-ttu-id="08971-134">Para obtener más información, consulte [cómo configurar un puerto de envío SOAP](../core/how-to-configure-a-soap-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="08971-134">For more information, see [How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md).</span></span>  
  
    |<span data-ttu-id="08971-135">Use</span><span class="sxs-lookup"><span data-stu-id="08971-135">Use this</span></span>|<span data-ttu-id="08971-136">Para</span><span class="sxs-lookup"><span data-stu-id="08971-136">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="08971-137">**La siguiente configuración**</span><span class="sxs-lookup"><span data-stu-id="08971-137">**The following settings**</span></span>|<span data-ttu-id="08971-138">Seleccione esta opción para especificar las siguientes propiedades.</span><span class="sxs-lookup"><span data-stu-id="08971-138">Select this option to specify the following properties.</span></span>|  
    |<span data-ttu-id="08971-139">**Nombre del ensamblado**</span><span class="sxs-lookup"><span data-stu-id="08971-139">**Assembly name**</span></span>|<span data-ttu-id="08971-140">Seleccione el ensamblado creado en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="08971-140">Select the assembly created in the previous procedure.</span></span> <span data-ttu-id="08971-141">El nombre completo del ensamblado se escribe en el adaptador de SOAP **AssemblyName** propiedad.</span><span class="sxs-lookup"><span data-stu-id="08971-141">The fully qualified name of the assembly is written to the SOAP adapter **AssemblyName** property.</span></span>|  
    |<span data-ttu-id="08971-142">**Nombre de tipo**</span><span class="sxs-lookup"><span data-stu-id="08971-142">**Type name**</span></span>|<span data-ttu-id="08971-143">Especificar el nombre de la clase que contiene el método Web que se va a invocar.</span><span class="sxs-lookup"><span data-stu-id="08971-143">Specify the name of the class that contains the Web method to be invoked.</span></span> <span data-ttu-id="08971-144">El nombre de tipo se escribe en el adaptador de SOAP **TypeName** propiedad.</span><span class="sxs-lookup"><span data-stu-id="08971-144">The type name is written to the SOAP adapter **TypeName** property.</span></span>|  
    |<span data-ttu-id="08971-145">**Nombre del método**</span><span class="sxs-lookup"><span data-stu-id="08971-145">**Method name**</span></span>|<span data-ttu-id="08971-146">Especificar uno de los métodos del cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="08971-146">Specify one of the methods in the list box.</span></span> <span data-ttu-id="08971-147">El método Web se escribe en el adaptador de Soap **MethodName** propiedad.</span><span class="sxs-lookup"><span data-stu-id="08971-147">The Web method is written to the Soap Adapter **MethodName** property.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="08971-148">Si desea usar Enrutamiento por contenidos (CBR), configure el filtro del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="08971-148">If you want to use Content-Based Routing (CBR), configure the filter of the send port.</span></span> <span data-ttu-id="08971-149">Para obtener más información, consulte [cómo configurar filtros para un puerto de envío](../core/how-to-configure-filters-for-a-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="08971-149">For more information, see [How to Configure Filters for a Send Port](../core/how-to-configure-filters-for-a-send-port.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="08971-150">Si no hay suscriptor para los mensajes de respuesta de los servicios Web invocados, se producirá un error en el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="08971-150">If there is no subscriber to the response messages from the invoked Web services, a routing failure error will occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08971-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="08971-151">See Also</span></span>  
 [<span data-ttu-id="08971-152">Consumo de servicios web</span><span class="sxs-lookup"><span data-stu-id="08971-152">Consuming Web Services</span></span>](../core/consuming-web-services.md)