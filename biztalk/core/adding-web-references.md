---
title: Agregar referencias Web | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- orchestrations, BPEL
- Web services, ports
- orchestrations, exporting
- Web services, projects
- Web services, references
- projects, Web services
ms.assetid: 7e40f215-f11a-4151-bcc6-e107bf36b6f6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bcdeb4966da4a4b54fea826590f867e4125d2ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adding-web-references"></a><span data-ttu-id="42b3f-102">Agregar referencias web</span><span class="sxs-lookup"><span data-stu-id="42b3f-102">Adding Web References</span></span>
<span data-ttu-id="42b3f-103">Antes de que pueda agregar un puerto Web, necesitará agregar una referencia Web a su proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="42b3f-103">Before you can add a Web port, you need to add a Web reference to your BizTalk project.</span></span> <span data-ttu-id="42b3f-104">Una referencia Web es una descripción de un servicio Web que se encuentra disponible en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="42b3f-104">A Web reference is a description of a Web service that is available to your project.</span></span> <span data-ttu-id="42b3f-105">Cuando se agrega una referencia Web al proyecto, el proyecto de BizTalk crea una orquestación Web tipo de puerto, tipos de mensajes Web, Reference.map (archivo de asignación), Reference.odx (archivo de orquestación), \< *WebService*> .disco ( archivo de detección), y \< *WebService*> .wsdl (archivo de lenguaje de descripción de servicios Web) a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="42b3f-105">When you add a Web reference to your project, BizTalk project creates an orchestration Web port type, Web message types, Reference.map (map file), Reference.odx (orchestration file), \<*WebService*>.disco (discovery file), and \<*WebService*>.wsdl (Web Service Description Language file) to your project.</span></span> <span data-ttu-id="42b3f-106">Si su archivo de Lenguaje de descripción de servicios Web (WSDL) contiene tipos de esquemas de mensaje Web, el proyecto de BizTalk agregará Reference.xsd a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="42b3f-106">If your Web Service Description Language (WSDL) file contains schema Web message types, BizTalk project adds Reference.xsd to your project.</span></span>  
  
 <span data-ttu-id="42b3f-107">Una referencia Web incluye:</span><span class="sxs-lookup"><span data-stu-id="42b3f-107">A Web reference includes:</span></span>  
  
-   <span data-ttu-id="42b3f-108">Un Localizador uniforme de recursos (URL) para el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="42b3f-108">A Universal Resource Locator (URL) for the Web service.</span></span>  
  
-   <span data-ttu-id="42b3f-109">Un archivo WSDL que ofrece información sobre el servicio, como los métodos disponibles, puertos y tipos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="42b3f-109">A WSDL file that offers information about the service such as available methods, ports, and message types.</span></span>  
  
-   <span data-ttu-id="42b3f-110">Una asignación de referencias (Reference.map).</span><span class="sxs-lookup"><span data-stu-id="42b3f-110">A reference map (Reference.map).</span></span>  
  
 <span data-ttu-id="42b3f-111">Al agregar una referencia Web, todos los métodos Web para ese servicio Web deben ser compatibles con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="42b3f-111">When you add a Web reference, all the Web methods for that Web service must be compatible with BizTalk Server.</span></span> <span data-ttu-id="42b3f-112">No puede especificar atributos condicionales para los métodos Web específicos de un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="42b3f-112">You cannot specify conditional attributes for specific Web methods in a Web service.</span></span>  
  
 <span data-ttu-id="42b3f-113">Agregar una referencia Web al proyecto mediante el **Agregar referencia Web** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="42b3f-113">You add a Web reference to your project by using the **Add Web Reference** dialog box.</span></span> <span data-ttu-id="42b3f-114">Para obtener más información acerca de cómo agregar referencias Web, vea [en Visual Studio](../core/using-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="42b3f-114">For more information about adding Web references, see [Using Visual Studio](../core/using-visual-studio.md).</span></span>  
  
 <span data-ttu-id="42b3f-115">Si planea exportar su orquestación usando el proceso de exportación del lenguaje de ejecución de procesos empresariales (BPEL), no puede hacer referencia a una referencia Web desde un proyecto existente de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="42b3f-115">If you are planning to export your orchestration using the Business Process Execution Language (BPEL) export process, you cannot reference a Web reference from an existing BizTalk project.</span></span> <span data-ttu-id="42b3f-116">Cuando hace referencia a una referencia Web desde un proyecto existente de BizTalk, el proceso de exportación BPEL autogenerará un segundo archivo WSDL y perderá la información de enlace.</span><span class="sxs-lookup"><span data-stu-id="42b3f-116">When you reference a Web reference from an existing BizTalk project, the BPEL export process will auto-generate a second WSDL file and you will lose your binding information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b3f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="42b3f-117">See Also</span></span>  
 <span data-ttu-id="42b3f-118">[Creación de puertos Web](../core/creating-web-ports.md) </span><span class="sxs-lookup"><span data-stu-id="42b3f-118">[Creating Web Ports](../core/creating-web-ports.md) </span></span>  
 [<span data-ttu-id="42b3f-119">Consumir servicios Web</span><span class="sxs-lookup"><span data-stu-id="42b3f-119">Consuming Web Services</span></span>](../core/consuming-web-services.md)