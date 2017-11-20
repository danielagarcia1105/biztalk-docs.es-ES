---
title: Encabezados SOAP con servicios Web consumidos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers, code samples
- Web services, consuming
- Web services, SOAP headers
- SOAP headers, Web services
- Web services, code samples
ms.assetid: 7be2eee1-ce1c-4611-985c-91dbc8492d6e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b486517e062067b76cd7598a7d8117b92ff83e39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="soap-headers-with-consumed-web-services"></a><span data-ttu-id="47778-102">Encabezados SOAP con servicios Web consumidos</span><span class="sxs-lookup"><span data-stu-id="47778-102">SOAP Headers with Consumed Web Services</span></span>
<span data-ttu-id="47778-103">Después de agregar servicios Web a la orquestación por medio del **Agregar referencia Web** cuadro de diálogo, puede utilizar los encabezados SOAP que define el lenguaje de descripción de servicios Web (WSDL) en el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="47778-103">After you add Web services to your orchestration using the **Add Web Reference** dialog box, you can use the SOAP headers that the Web Services Description Language (WSDL) defines in the Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47778-104">Los servicios Web consumidos no admiten encabezados SOAP desconocidos.</span><span class="sxs-lookup"><span data-stu-id="47778-104">Consumed Web services do not support unknown SOAP headers.</span></span>  
  
 <span data-ttu-id="47778-105">El WSDL para el servicio Web consumido enumera los encabezados SOAP definidos en el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="47778-105">The WSDL for the consumed Web service lists the defined SOAP headers in the binding element.</span></span> <span data-ttu-id="47778-106">En el ejemplo siguiente se muestra un elemento de enlace en el archivo WSDL para el servicio Web consumido:</span><span class="sxs-lookup"><span data-stu-id="47778-106">The following example shows a binding element in the WSDL file for the consumed Web service:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<definitions xmlns:http="http://schemas.xmlsoap.org/wsdl/http/" xmlns:soap="http://schemas.xmlsoap.org/wsdl/soap/" xmlns:s="http://www.w3.org/2001/XMLSchema" xmlns:s0="http://SOAPHeaderWS.ItemAvailability" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:tm="http://microsoft.com/wsdl/mime/textMatching/" xmlns:mime="http://schemas.xmlsoap.org/wsdl/mime/" targetNamespace="http://SOAPHeaderWS.ItemAvailability" xmlns="http://schemas.xmlsoap.org/wsdl/">  
       <types>  
             <s:schema elementFormDefault="qualified" targetNamespace="http://SOAPHeaderWS.ItemAvailability">  
  
                    <s:element name="OrigDest" type="s0:OrigDest"/>  
                    <s:complexType name="OrigDest">  
                           <s:sequence>  
                                 <s:element minOccurs="0" maxOccurs="1" name="Origination" type="s:string"/>  
                                 <s:element minOccurs="0" maxOccurs="1" name="Destination" type="s:string"/>  
                           </s:sequence>  
                    </s:complexType>  
             </s:schema>  
       </types>  
  
       <binding name="ItemAvailabilityServiceSoap" type="s0:ItemAvailabilityServiceSoap">  
             <soap:binding transport="http://schemas.xmlsoap.org/soap/http" style="document"/>  
             <operation name="ItemAvailability">  
                    <soap:operation soapAction="http://SOAPHeaderWS.ItemAvailability/ItemAvailability" style="document"/>  
                    <input>  
                           <soap:body use="literal"/>  
                           <soap:header message="s0:ItemAvailabilityOrigDest" part="OrigDest" use="literal"/>  
                    </input>  
                    <output>  
                           <soap:body use="literal"/>  
                           <soap:header message="s0:ItemAvailabilityOrigDest" part="OrigDest" use="literal"/>  
                    </output>  
             </operation>  
       </binding>  
       <service name="ItemAvailabilityService">  
             <port name="ItemAvailabilityServiceSoap" binding="s0:ItemAvailabilityServiceSoap">  
                    <soap:address location="http://localhost/SOAPHeaderWS/ItemAvailability.asmx"/>  
             </port>  
       </service>  
</definitions>  
```  
  
 <span data-ttu-id="47778-107">Para obtener más información sobre el uso de encabezados SOAP, consulte "Using SOAP Headers" en la documentación de .NET Framework en [http://go.microsoft.com/fwlink/?LinkId=62266](http://go.microsoft.com/fwlink/?LinkId=62266).</span><span class="sxs-lookup"><span data-stu-id="47778-107">For more information about using SOAP headers, see "Using SOAP Headers" in .NET Framework documentation at [http://go.microsoft.com/fwlink/?LinkId=62266](http://go.microsoft.com/fwlink/?LinkId=62266).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47778-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="47778-108">In This Section</span></span>  
  
-   [<span data-ttu-id="47778-109">Consumir servicios Web con encabezados SOAP</span><span class="sxs-lookup"><span data-stu-id="47778-109">Consuming Web Services with SOAP Headers</span></span>](../core/consuming-web-services-with-soap-headers.md)  
  
-   [<span data-ttu-id="47778-110">Usar encabezados SOAP en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="47778-110">Using SOAP Headers in Orchestrations</span></span>](../core/using-soap-headers-in-orchestrations.md)  
  
-   [<span data-ttu-id="47778-111">Usar encabezados SOAP en componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="47778-111">Using SOAP Headers in Pipeline Components</span></span>](../core/using-soap-headers-in-pipeline-components.md)