---
title: Publicación de servicios Web | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- BizTalk Server Web Services Publishing Wizard
ms.assetid: eed0717c-b390-492a-a3b9-ae31024805a2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aca08c1e4fabd833bd6de924e04e6052cd99890b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268548"
---
# <a name="publishing-web-services"></a><span data-ttu-id="4d925-102">Publicar servicios Web</span><span class="sxs-lookup"><span data-stu-id="4d925-102">Publishing Web Services</span></span>
<span data-ttu-id="4d925-103">La publicación de servicios Web le permite crear un servicio Web que pueda enviar mensajes a Microsoft BizTalk Server para que los utilicen las orquestaciones y otros adaptadores de envío.</span><span class="sxs-lookup"><span data-stu-id="4d925-103">Publishing Web services enables you to create a Web service that can submit messages to Microsoft BizTalk Server for use by orchestrations and other send adapters.</span></span> <span data-ttu-id="4d925-104">El Asistente para publicar servicios Web de BizTalk se utiliza para crear servicios Web publicados.</span><span class="sxs-lookup"><span data-stu-id="4d925-104">You create published Web services using the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="4d925-105">Para obtener información acerca de cómo configurar un controlador de envío SOAP, vea [cómo configurar un controlador de envío de SOAP](../core/how-to-configure-a-soap-send-handler.md).</span><span class="sxs-lookup"><span data-stu-id="4d925-105">For information about configuring a SOAP send handler, see [How to Configure a SOAP Send Handler](../core/how-to-configure-a-soap-send-handler.md).</span></span> <span data-ttu-id="4d925-106">Para obtener información acerca de cómo configurar un puerto de envío SOAP, vea [cómo configurar un puerto de envío de SOAP](../core/how-to-configure-a-soap-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="4d925-106">For information about configuring a SOAP send port, see [How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md).</span></span>  
  
 <span data-ttu-id="4d925-107">El Asistente para publicación de servicios Web de BizTalk proporciona dos métodos para publicar servicios Web: publicar una orquestación como un servicio Web y publicar esquemas como servicios Web.</span><span class="sxs-lookup"><span data-stu-id="4d925-107">The BizTalk Web Services Publishing Wizard provides you with two methods to publish Web services: publishing an orchestration as a Web service and publishing schemas as a Web service.</span></span>  
  
 <span data-ttu-id="4d925-108">Debe instalar y habilitar los servicios Microsoft Internet Information Services (IIS) y ASP.NET antes de publicar orquestaciones y esquemas de Microsoft BizTalk Server como servicios Web.</span><span class="sxs-lookup"><span data-stu-id="4d925-108">You must install and enable Microsoft Internet Information Services (IIS) and ASP.NET before you can publish Microsoft BizTalk Server orchestrations and schemas as Web services.</span></span> <span data-ttu-id="4d925-109">Para obtener información acerca de cómo instalar IIS y ASP.NET, vea instalar Internet Information Services (IIS) en la Guía de instalación de BizTalk Server ubicado en [HYPERLINK "http://go.microsoft.com/fwlink/? LinkID = 191321" http://go.microsoft.com/fwlink/? LinkID = 191321](http://go.microsoft.com/fwlink/?LinkID=191321).</span><span class="sxs-lookup"><span data-stu-id="4d925-109">For information about installing IIS and ASP.NET, see Installing Internet Information Services (IIS) in the BizTalk Server Installation Guide located at [HYPERLINK "http://go.microsoft.com/fwlink/?LinkID=191321" http://go.microsoft.com/fwlink/?LinkID=191321](http://go.microsoft.com/fwlink/?LinkID=191321).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4d925-110">Antes de ejecutar el Asistente para publicar servicios Web de BizTalk, debe habilitar los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="4d925-110">Before running the BizTalk Web Services Publishing Wizard, you must enable Web services.</span></span> <span data-ttu-id="4d925-111">Para obtener más información acerca de cómo habilitar los servicios Web para su sistema, consulte [habilitar servicios Web](../core/enabling-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="4d925-111">For more information about enabling Web services for your system, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d925-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4d925-112">In This Section</span></span>  
  
-   [<span data-ttu-id="4d925-113">Planificación para publicar servicios Web</span><span class="sxs-lookup"><span data-stu-id="4d925-113">Planning for Publishing Web Services</span></span>](../core/planning-for-publishing-web-services2.md)  
  
-   [<span data-ttu-id="4d925-114">Habilitar los servicios Web</span><span class="sxs-lookup"><span data-stu-id="4d925-114">Enabling Web Services</span></span>](../core/enabling-web-services.md)  
  
-   [<span data-ttu-id="4d925-115">Publicar una orquestación como servicio Web</span><span class="sxs-lookup"><span data-stu-id="4d925-115">Publishing an Orchestration as a Web Service</span></span>](../core/publishing-an-orchestration-as-a-web-service.md)  
  
-   [<span data-ttu-id="4d925-116">Publicar esquemas como servicios Web</span><span class="sxs-lookup"><span data-stu-id="4d925-116">Publishing Schemas as a Web Service</span></span>](../core/publishing-schemas-as-a-web-service.md)  
  
-   [<span data-ttu-id="4d925-117">Consideraciones al publicar servicios Web</span><span class="sxs-lookup"><span data-stu-id="4d925-117">Considerations When Publishing Web Services</span></span>](../core/considerations-when-publishing-web-services.md)  
  
-   [<span data-ttu-id="4d925-118">Depurar servicios Web publicados</span><span class="sxs-lookup"><span data-stu-id="4d925-118">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)  
  
-   [<span data-ttu-id="4d925-119">Probar los servicios Web publicados</span><span class="sxs-lookup"><span data-stu-id="4d925-119">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)  
  
-   [<span data-ttu-id="4d925-120">Implementar servicios Web publicados en un equipo que no tenga Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4d925-120">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)