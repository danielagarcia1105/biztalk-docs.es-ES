---
title: "Creación de servicios Web y métodos Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, schemas
- orchestrations, naming conventions
- Web services, naming conventions
- schemas, Web services
ms.assetid: a7c47000-501c-47b1-bafa-82370585c1db
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74065489e427ae0612897f1f333e3c8e154a535f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-web-services-and-web-methods"></a><span data-ttu-id="f19b3-102">Creación de servicios Web y métodos Web</span><span class="sxs-lookup"><span data-stu-id="f19b3-102">Creating Web Services and Web Methods</span></span>
<span data-ttu-id="f19b3-103">Al publicar esquemas como servicio Web, controla la creación de servicios y métodos Web en el Asistente para publicar servicios Web de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f19b3-103">When you publish schemas as a Web service, you control the creation of Web services and Web methods in the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="f19b3-104">Se puede cambiar el nombre de la descripción del servicio Web, el servicio y el método Web dentro del árbol disponible en la página Servicios Web.</span><span class="sxs-lookup"><span data-stu-id="f19b3-104">You can rename the Web service description, Web service and Web method inside the tree available on the Web Services page.</span></span> <span data-ttu-id="f19b3-105">Puede agregar y quitar servicios y métodos Web.</span><span class="sxs-lookup"><span data-stu-id="f19b3-105">You can add and remove Web services and Web methods.</span></span> <span data-ttu-id="f19b3-106">El asistente usa los nombres de elementos raíz de los esquemas de solicitud seleccionados como el nombre del parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="f19b3-106">The wizard uses the root element names of the selected request schemas as the input parameter name.</span></span> <span data-ttu-id="f19b3-107">El valor de retorno del método Web devuelve el esquema de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f19b3-107">The Web method return value returns the response schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f19b3-108">Los clientes Web ASP.NET pueden cambiar la firma del método Web mediante la combinación de parámetros de entrada y salida del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="f19b3-108">ASP.NET Web clients may change the Web method signature by combining the in and out parameters of the same type.</span></span> <span data-ttu-id="f19b3-109">Por ejemplo, un cliente Web de ASP.NET puede cambiar un método Web de BizTalk desde **string myService (parte de la cadena)** a **void myService (parte de cadena ref)**.</span><span class="sxs-lookup"><span data-stu-id="f19b3-109">For example, an ASP.NET Web client may change a BizTalk Web method from **string myService(string part)** to **void myService(ref string part)**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f19b3-110">Si la recepción puerto está definido como unidireccional, el tipo de respuesta de método Web es **void** y no se devuelve información al cliente Web.</span><span class="sxs-lookup"><span data-stu-id="f19b3-110">If your receive port is defined as one-way, the Web method response type is **void** and no information is returned to the Web client.</span></span> <span data-ttu-id="f19b3-111">La orquestación y el adaptador de SOAP no devuelven excepciones iniciadas al cliente Web.</span><span class="sxs-lookup"><span data-stu-id="f19b3-111">The SOAP adapter and orchestration do not return thrown exceptions to the Web client.</span></span>  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a><span data-ttu-id="f19b3-112">Convenciones de nomenclatura de servicios Web para orquestaciones publicadas</span><span class="sxs-lookup"><span data-stu-id="f19b3-112">Web services naming conventions for published orchestrations</span></span>  
 <span data-ttu-id="f19b3-113">El Asistente para publicar servicios Web de BizTalk genera nombres de archivos de servicios Web (.asmx) basados en las descripciones que haya definido en la página Servicio Web.</span><span class="sxs-lookup"><span data-stu-id="f19b3-113">The BizTalk Web Services Publishing Wizard generates Web service (.asmx) file names based on the Web services description that you define in the Web Service page.</span></span> <span data-ttu-id="f19b3-114">La siguiente tabla muestra los valores predeterminados para los nombres de archivos de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="f19b3-114">The following table shows the default values for the Web service file names.</span></span>  
  
|<span data-ttu-id="f19b3-115">Servicio Web generado</span><span class="sxs-lookup"><span data-stu-id="f19b3-115">Generated Web service</span></span>|<span data-ttu-id="f19b3-116">Nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="f19b3-116">File name</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="f19b3-117">BizTalkWebService</span><span class="sxs-lookup"><span data-stu-id="f19b3-117">BizTalkWebService</span></span>|<span data-ttu-id="f19b3-118">Nombre de proyecto del servicio Web de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f19b3-118">Visual Studio Web Service project name</span></span>|  
|<span data-ttu-id="f19b3-119">WebService1</span><span class="sxs-lookup"><span data-stu-id="f19b3-119">WebService1</span></span>|<span data-ttu-id="f19b3-120">Nombre del archivo del servicio Web (.asmx)</span><span class="sxs-lookup"><span data-stu-id="f19b3-120">Web service (.asmx) file name</span></span>|  
|<span data-ttu-id="f19b3-121">WebMethod1</span><span class="sxs-lookup"><span data-stu-id="f19b3-121">WebMethod1</span></span>|<span data-ttu-id="f19b3-122">Nombre del método Web</span><span class="sxs-lookup"><span data-stu-id="f19b3-122">Web method name</span></span>|  
  
 <span data-ttu-id="f19b3-123">El servicio Web generado no refleja los nombres de los nodos restantes.</span><span class="sxs-lookup"><span data-stu-id="f19b3-123">The generated Web service does not reflect the names of the remaining nodes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f19b3-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f19b3-124">See Also</span></span>  
 <span data-ttu-id="f19b3-125">[Publicar esquemas como servicios Web](../core/publishing-schemas-as-a-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="f19b3-125">[Publishing Schemas as a Web Service](../core/publishing-schemas-as-a-web-service.md) </span></span>  
 [<span data-ttu-id="f19b3-126">Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar esquemas como servicios Web</span><span class="sxs-lookup"><span data-stu-id="f19b3-126">How to Use the BizTalk Web Services Publishing Wizard to Publish Schemas as a Web Service</span></span>](../core/publish-schemas-as-web-services-with-biztalk-web-services-publishing-wizard.md)