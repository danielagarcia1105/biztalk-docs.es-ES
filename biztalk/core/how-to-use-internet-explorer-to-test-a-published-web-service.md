---
title: Probar el servicio web de BizTalk | Documentos de Microsoft
description: Configurar ubicaciones de recepción y web.config para probar el servicio web de BizTalk en un explorador web
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dc2171d-4abe-43db-b4bc-e484048c6430
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48a35373735102bd75d1c388da29b06d4392ba18
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "26008853"
---
# <a name="test-a-biztalk-web-service"></a><span data-ttu-id="ccb73-103">Probar un servicio Web de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ccb73-103">Test a BizTalk Web Service</span></span>

## <a name="overview"></a><span data-ttu-id="ccb73-104">Información general</span><span class="sxs-lookup"><span data-stu-id="ccb73-104">Overview</span></span>
<span data-ttu-id="ccb73-105">Puede probar el servicio Web publicado sin escribir una aplicación cliente Web.</span><span class="sxs-lookup"><span data-stu-id="ccb73-105">You can test your published Web service without writing a Web client application.</span></span> <span data-ttu-id="ccb73-106">Se puede utilizar un explorador Web, por ejemplo Internet Explorer, para probar el servicio Web publicado.</span><span class="sxs-lookup"><span data-stu-id="ccb73-106">You can use a Web browser, such as Internet Explorer, to test your published Web service.</span></span> <span data-ttu-id="ccb73-107">Aunque es posible obtener acceso a cualquier servicio Web publicado mediante un explorador Web, sólo puede probar los servicios Web con métodos Web que contienen parámetros de tipo simple.</span><span class="sxs-lookup"><span data-stu-id="ccb73-107">Although you can access any published Web service using a Web browser, you can only test Web services with Web methods that contain simple type parameters.</span></span> <span data-ttu-id="ccb73-108">Para probar el método Web en un explorador Web, los elementos de mensaje para los mensajes de solicitud y respuesta que se usan en el puerto de recepción sólo puede un tipo simple, como **System.String** o **System.Int32**.</span><span class="sxs-lookup"><span data-stu-id="ccb73-108">To test your Web method in a Web browser, your message parts for the request and response messages that are used in the receive port can only be a simple type, such as **System.String** or **System.Int32**.</span></span> <span data-ttu-id="ccb73-109">Si la parte de mensaje utiliza un esquema como tipo de mensaje, no puede probar el método Web con un explorador.</span><span class="sxs-lookup"><span data-stu-id="ccb73-109">If any message part uses a schema as a message type, you cannot test the Web method with a browser.</span></span>  
  
 <span data-ttu-id="ccb73-110">Si desea probar los servicios Web publicados que usan HTTP-GET o HTTP-POST, debe configurar la ubicación de recepción de BizTalk para el adaptador de SOAP y modificar el archivo Web.config para el servicio Web publicado.</span><span class="sxs-lookup"><span data-stu-id="ccb73-110">If you want to test your published Web services using HTTP-GET or HTTP-POST, you must configure your BizTalk receive location for the SOAP adapter and modify the Web.config file for your published Web service.</span></span>  
  
 <span data-ttu-id="ccb73-111">**Modificar las ubicaciones de recepción**</span><span class="sxs-lookup"><span data-stu-id="ccb73-111">**Modifying the Receive Locations**</span></span>  
  
 <span data-ttu-id="ccb73-112">Si el adaptador de SOAP configura las ubicaciones de recepción, éste establece normalmente el URI de la ubicación de recepción proporcionando el nombre del archivo .asmx al directorio virtual y al servicio Web:</span><span class="sxs-lookup"><span data-stu-id="ccb73-112">When the SOAP adapter configures receive locations, the SOAP adapter normally sets the URI of the receive location by giving the virtual directory and the Web service .asmx file name:</span></span>  
  
```  
/PurchaseOrder/POOrchestration.asmx  
```  
  
 <span data-ttu-id="ccb73-113">Esto permite al adaptador de SOAP recibir las solicitudes del servicio Web a través del protocolo HTTP-SOAP.</span><span class="sxs-lookup"><span data-stu-id="ccb73-113">This allows the SOAP adapter to receive Web service requests using the HTTP-SOAP protocol.</span></span> <span data-ttu-id="ccb73-114">Para configurar la ubicación de recepción con el fin de usar el protocolo HTTP-GET o HTTP-POST, debe anexar el nombre del método al URI:</span><span class="sxs-lookup"><span data-stu-id="ccb73-114">To configure the receive location to use the HTTP-GET or HTTP-POST protocol, you must append the method name to the URI:</span></span>  
  
```  
/PurchaseOrder/POOrchestration.asmx/Operation_1  
```  
  
 <span data-ttu-id="ccb73-115">El nombre del método es el mismo que el nombre de operación del puerto en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ccb73-115">The method name is the same as the port operation name in the orchestration.</span></span>  
  
 <span data-ttu-id="ccb73-116">**Modificar el archivo Web.config**</span><span class="sxs-lookup"><span data-stu-id="ccb73-116">**Modifying the Web.config file**</span></span>  
  
 <span data-ttu-id="ccb73-117">De forma predeterminada, el asistente configura los servicios Web para usar el protocolo HTTP-SOAP.</span><span class="sxs-lookup"><span data-stu-id="ccb73-117">By default, the wizard configures the Web services to use the HTTP-SOAP protocol.</span></span> <span data-ttu-id="ccb73-118">HTTP-GET y HTTP-POST se deshabilitan de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="ccb73-118">HTTP-GET and HTTP-POST are explicitly disabled.</span></span> <span data-ttu-id="ccb73-119">Para probar un servicio Web con un explorador Web, debe habilitar HTTP-GET.</span><span class="sxs-lookup"><span data-stu-id="ccb73-119">To test a Web service with a Web browser, you must enable HTTP-GET.</span></span>  
  
## <a name="update-the-webconfig"></a><span data-ttu-id="ccb73-120">Actualizar el archivo Web.config</span><span class="sxs-lookup"><span data-stu-id="ccb73-120">Update the Web.config</span></span>
  
1.  <span data-ttu-id="ccb73-121">Abra el archivo Web.config del servicio Web publicado.</span><span class="sxs-lookup"><span data-stu-id="ccb73-121">Open the Web.config file for the published Web service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ccb73-122">Puede buscar el archivo Web.config en el directorio que ha configurado para la raíz virtual de IIS que contiene el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="ccb73-122">You can find the Web.config file in the directory that you configured for the IIS virtual root that contains the Web service.</span></span>  
  
2.  <span data-ttu-id="ccb73-123">Buscar el \<protocolos\> sección:</span><span class="sxs-lookup"><span data-stu-id="ccb73-123">Find the \<protocols\> section:</span></span>  
  
    ```  
    <webServices>  
       <protocols>  
         <remove name="HttpPost" />  
         <remove name="HttpGet" />  
         <remove name="HttpPostLocalhost" />  
       </protocols>  
  
    </webServices>  
    ```  
  
3.  <span data-ttu-id="ccb73-124">Para probar HTTP-GET, HTTP-POST o HTTP-POST en el equipo local, quite la línea correspondiente de la \<protocolos\> sección.</span><span class="sxs-lookup"><span data-stu-id="ccb73-124">For testing HTTP-GET, HTTP-POST, or HTTP-POST from the local computer, remove the corresponding line from the \<protocols\> section.</span></span>  
  
 <span data-ttu-id="ccb73-125">Para obtener más información acerca de las opciones de configuración, consulte [opciones de configuración de servicios Web XML creados con ASP.NET](https://msdn.microsoft.com/library/b2c0ew36.aspx).</span><span class="sxs-lookup"><span data-stu-id="ccb73-125">For more information about the configuration options, see [Configuration Options for XML Web Services Created Using ASP.NET](https://msdn.microsoft.com/library/b2c0ew36.aspx).</span></span> 
  
#### <a name="access-a-web-service-with-internet-explorer"></a><span data-ttu-id="ccb73-126">Obtener acceso a un servicio Web con Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="ccb73-126">Access a Web service with Internet Explorer</span></span>  
  
-   <span data-ttu-id="ccb73-127">En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para el servicio Web con el formato **http://*servername*/*apppath* / *webservicename*.asmx**.</span><span class="sxs-lookup"><span data-stu-id="ccb73-127">In Internet Explorer, in the **Address** box, type the URL for the Web service using the format **http://*servername*/*apppath*/*webservicename*.asmx**.</span></span>  
  
    |<span data-ttu-id="ccb73-128">Parámetro</span><span class="sxs-lookup"><span data-stu-id="ccb73-128">Parameter</span></span>|<span data-ttu-id="ccb73-129">Value</span><span class="sxs-lookup"><span data-stu-id="ccb73-129">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="ccb73-130">***servername***</span><span class="sxs-lookup"><span data-stu-id="ccb73-130">***servername***</span></span>|<span data-ttu-id="ccb73-131">El nombre del servidor en el que ha implementado el servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="ccb73-131">The name of the server that you have deployed your XML Web service.</span></span>|  
    |<span data-ttu-id="ccb73-132">***Apppath***</span><span class="sxs-lookup"><span data-stu-id="ccb73-132">***Apppath***</span></span>|<span data-ttu-id="ccb73-133">El nombre del directorio virtual y la ruta de aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="ccb73-133">The name of your virtual directory and the Web application path.</span></span>|  
    |<span data-ttu-id="ccb73-134">***webservicename.asmx***</span><span class="sxs-lookup"><span data-stu-id="ccb73-134">***webservicename.asmx***</span></span>|<span data-ttu-id="ccb73-135">El nombre del archivo .asmx del servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="ccb73-135">The name of the XML Web service .asmx file.</span></span>|  
  
 <span data-ttu-id="ccb73-136">La descripción del servicio Web muestra todos los métodos del servicio Web que admite el servicio Web concreto.</span><span class="sxs-lookup"><span data-stu-id="ccb73-136">The description for the Web service shows you all the Web service methods that the particular Web service supports.</span></span> <span data-ttu-id="ccb73-137">La página de descripción del servicio Web contiene vínculos para los métodos Web disponibles y la descripción del servicio del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="ccb73-137">The Web service description page contains links for each available Web method and the service description of the Web service.</span></span>  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get"></a><span data-ttu-id="ccb73-138">Probar un servicio Web con Internet Explorer mediante HTTP-GET</span><span class="sxs-lookup"><span data-stu-id="ccb73-138">Test a Web service with Internet Explorer using HTTP-GET</span></span>  
  
1.  <span data-ttu-id="ccb73-139">Tras obtener acceso a la página de descripción del servicio Web, haga clic en uno de los métodos Web enumerados en la página de descripción del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="ccb73-139">After accessing the Web service description page, click one of the Web methods listed in the Web service description page.</span></span>  
  
2.  <span data-ttu-id="ccb73-140">Escriba los parámetros necesarios para el método Web y, a continuación, haga clic en **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="ccb73-140">Type the necessary parameters for the Web method, and then click **Invoke**.</span></span>  
  
3.  <span data-ttu-id="ccb73-141">El servidor devuelve una respuesta XML en el explorador.</span><span class="sxs-lookup"><span data-stu-id="ccb73-141">The server returns an XML response in the browser.</span></span> <span data-ttu-id="ccb73-142">Si el tipo de datos de retorno del servicio Web es un número de punto flotante de doble precisión, el resultado podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="ccb73-142">If the return data type for the Web service is a double-precision floating-point number, the result might look like the following:</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <double>74.5</double>  
    ```  
  
#### <a name="test-a-web-service-with-internet-explorer-using-http-get-alternate-method"></a><span data-ttu-id="ccb73-143">Probar un servicio Web con Internet Explorer mediante HTTP-GET (método alternativo)</span><span class="sxs-lookup"><span data-stu-id="ccb73-143">Test a Web service with Internet Explorer using HTTP-GET (alternate method)</span></span>  
  
1.  <span data-ttu-id="ccb73-144">En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para el servicio Web con el formato ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***.</span><span class="sxs-lookup"><span data-stu-id="ccb73-144">In Internet Explorer, in the **Address** box, type the URL for the Web service using the format ***http://servername/vdir/webservicename.asmx/Methodname?parameter=value***.</span></span>  
  
    |<span data-ttu-id="ccb73-145">Parámetro</span><span class="sxs-lookup"><span data-stu-id="ccb73-145">Parameter</span></span>|<span data-ttu-id="ccb73-146">Value</span><span class="sxs-lookup"><span data-stu-id="ccb73-146">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="ccb73-147">***servername***</span><span class="sxs-lookup"><span data-stu-id="ccb73-147">***servername***</span></span>|<span data-ttu-id="ccb73-148">El nombre del servidor en el que ha implementado el servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="ccb73-148">The name of the server that you have deployed your XML Web service.</span></span>|  
    |<span data-ttu-id="ccb73-149">***Apppath***</span><span class="sxs-lookup"><span data-stu-id="ccb73-149">***Apppath***</span></span>|<span data-ttu-id="ccb73-150">El nombre del directorio virtual y la ruta de aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="ccb73-150">The name of your virtual directory and the Web application path.</span></span>|  
    |<span data-ttu-id="ccb73-151">***webservicename.asmx***</span><span class="sxs-lookup"><span data-stu-id="ccb73-151">***webservicename.asmx***</span></span>|<span data-ttu-id="ccb73-152">El nombre del archivo .asmx del servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="ccb73-152">The name of the XML Web service .asmx file.</span></span>|  
    |<span data-ttu-id="ccb73-153">***Methodname***</span><span class="sxs-lookup"><span data-stu-id="ccb73-153">***Methodname***</span></span>|<span data-ttu-id="ccb73-154">El nombre de un método público que expone el servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="ccb73-154">The name of a public method that the XML Web service exposes.</span></span> <span data-ttu-id="ccb73-155">Si se deja en blanco, aparecerá la página de descripción del servicio Web XML, que enumera los métodos públicos disponibles en el archivo .asmx.</span><span class="sxs-lookup"><span data-stu-id="ccb73-155">If left blank, the description page for the XML Web service appears, listing each public method available in the .asmx file.</span></span> <span data-ttu-id="ccb73-156">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="ccb73-156">(Optional)</span></span>|  
    |<span data-ttu-id="ccb73-157">***parameter***</span><span class="sxs-lookup"><span data-stu-id="ccb73-157">***parameter***</span></span>|<span data-ttu-id="ccb73-158">El nombre y el valor del parámetro correspondiente para los parámetros que requiere el método.</span><span class="sxs-lookup"><span data-stu-id="ccb73-158">The appropriate parameter name and value for any parameters required by your method.</span></span> <span data-ttu-id="ccb73-159">Si se deja en blanco, aparecerá la página de descripción del servicio Web XML, que enumera los métodos públicos disponibles en el archivo .asmx.</span><span class="sxs-lookup"><span data-stu-id="ccb73-159">If left blank, the description page for the XML Web service appears, listing each public method available in the .asmx file.</span></span> <span data-ttu-id="ccb73-160">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="ccb73-160">(Optional)</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="ccb73-161">El nombre del método del servicio Web XML con esta sintaxis distingue mayúsculas de minúsculas, pero los nombres del servidor, proyecto y servicio Web XML no hacen esta distinción.</span><span class="sxs-lookup"><span data-stu-id="ccb73-161">The XML Web service method name in this syntax is case sensitive, but the server, project, and XML Web service names are not.</span></span>  
  
2.  <span data-ttu-id="ccb73-162">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ccb73-162">Press Enter.</span></span> <span data-ttu-id="ccb73-163">El explorador Web muestra una respuesta XML en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ccb73-163">The Web browser displays an XML response from the server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ccb73-164">Además, puede usar HTTP-POST para llamar al servicio Web.</span><span class="sxs-lookup"><span data-stu-id="ccb73-164">You can also use HTTP-POST to call the Web service.</span></span> <span data-ttu-id="ccb73-165">Para obtener información y ejemplos sobre cómo llamar a servicios Web XML desde un explorador Web, consulte [acceso a los servicios Web XML desde un explorador](https://msdn.microsoft.com/library/45fez2a8.aspx).</span><span class="sxs-lookup"><span data-stu-id="ccb73-165">For information and samples about calling XML Web services from a Web browser, see [Access XML Web Services from a Browser](https://msdn.microsoft.com/library/45fez2a8.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb73-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccb73-166">See Also</span></span>  
 [<span data-ttu-id="ccb73-167">Probar servicios web publicados</span><span class="sxs-lookup"><span data-stu-id="ccb73-167">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)