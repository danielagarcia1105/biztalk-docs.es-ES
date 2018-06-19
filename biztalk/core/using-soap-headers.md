---
title: Usar encabezados SOAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers
- SOAP headers, about SOAP headers
- Web services, SOAP headers
ms.assetid: 816618ff-ecd8-4f12-b9a9-dbe4203411d8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0671dabe7547d3f55b937a1de58241a35cb70b39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287124"
---
# <a name="using-soap-headers"></a><span data-ttu-id="80678-102">Utilizar encabezados SOAP</span><span class="sxs-lookup"><span data-stu-id="80678-102">Using SOAP Headers</span></span>
<span data-ttu-id="80678-103">Microsoft BizTalk Server proporciona compatibilidad para encabezados SOAP definidos y desconocidos.</span><span class="sxs-lookup"><span data-stu-id="80678-103">Microsoft BizTalk Server provides support for defined and unknown SOAP headers.</span></span> <span data-ttu-id="80678-104">Los encabezados SOAP definidos son encabezados de Lenguaje de descripción de servicios Web (WSDL) que se encuentran indicados explícitamente en el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="80678-104">Defined SOAP headers are headers in the Web Service Description Language (WSDL) that are explicity stated in the Web service.</span></span> <span data-ttu-id="80678-105">Los encabezados SOAP desconocidos son encabezados de WSDL que no se encuentran indicados explícitamente en el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="80678-105">Unknown SOAP headers are headers that in the WSDL that are not explicity stated in the Web service.</span></span> <span data-ttu-id="80678-106">Para obtener más información sobre el uso de encabezados SOAP, consulte "Using SOAP Headers" en la documentación de Microsoft .NET Framework en [http://go.microsoft.com/fwlink/?LinkId=25363](http://go.microsoft.com/fwlink/?LinkId=25363).</span><span class="sxs-lookup"><span data-stu-id="80678-106">For more information about using SOAP headers, see "Using SOAP Headers" in the Microsoft .NET Framework documentation at [http://go.microsoft.com/fwlink/?LinkId=25363](http://go.microsoft.com/fwlink/?LinkId=25363).</span></span>  
  
 <span data-ttu-id="80678-107">BizTalk Server crea una propiedad de contexto para cada encabezado SOAP definido en el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="80678-107">BizTalk Server creates a context property for each defined SOAP header in the Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80678-108">Los servicios Web consumidos sólo admiten encabezados SOAP definidos. No puede establecer encabezados desconocidos al consumir servicios Web.</span><span class="sxs-lookup"><span data-stu-id="80678-108">Consumed Web services support only defined SOAP headers.You cannot set unknown headers when consuming Web services.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80678-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="80678-109">In This Section</span></span>  
  
-   [<span data-ttu-id="80678-110">Encabezados SOAP con servicios Web consumidos</span><span class="sxs-lookup"><span data-stu-id="80678-110">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)  
  
-   [<span data-ttu-id="80678-111">Encabezados SOAP con servicios Web publicados</span><span class="sxs-lookup"><span data-stu-id="80678-111">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)