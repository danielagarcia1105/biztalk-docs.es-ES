---
title: Adaptador de Windows SharePoint Services | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters
ms.assetid: cbfc9bf3-912d-4849-ba8c-07a116888bbd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a6f1365b11ce93717223ec35e395165e8d0e551
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="windows-sharepoint-services-adapter"></a><span data-ttu-id="2002c-102">Adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="2002c-102">Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="2002c-103">El adaptador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para Microsoft Windows SharePoint Services proporciona una mayor integración de BizTalk Server con Windows SharePoint Services y Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="2002c-103">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Microsoft Windows SharePoint Services provides a tighter integration of BizTalk Server with Windows SharePoint Services and Microsoft Office.</span></span> <span data-ttu-id="2002c-104">El uso del adaptador de Windows SharePoint Services en la solución [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite obtener las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2002c-104">Using the Windows SharePoint Services adapter in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution provides you with the following capabilities:</span></span>  
  
-   <span data-ttu-id="2002c-105">Fácil acceso a los mensaje de entrada y salida mediante Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="2002c-105">Easy access to input and output messages through Windows SharePoint Services.</span></span>  
  
-   <span data-ttu-id="2002c-106">Capacidad de editar mensajes XML mediante aplicaciones de Office tales como Microsoft Office InfoPath.</span><span class="sxs-lookup"><span data-stu-id="2002c-106">The ability to edit XML messages by using Office applications such as Microsoft Office InfoPath.</span></span>  
  
-   <span data-ttu-id="2002c-107">Transformaciones bidireccionales de mensajes XML desde y hacia InfoPath.</span><span class="sxs-lookup"><span data-stu-id="2002c-107">Two-way transformations of XML messages to and from InfoPath.</span></span>  
  
 <span data-ttu-id="2002c-108">El adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] consta de los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="2002c-108">The [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adapter consists of the following components:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2002c-109">Adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] de CSOM</span><span class="sxs-lookup"><span data-stu-id="2002c-109">CSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter</span></span>|<span data-ttu-id="2002c-110">Usa el modelo de objetos del cliente de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] (CSOM).</span><span class="sxs-lookup"><span data-stu-id="2002c-110">Uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Client Side Object Model (CSOM).</span></span> <span data-ttu-id="2002c-111">El adaptador se instala con la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2002c-111">The adapter is installed when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed.</span></span> <span data-ttu-id="2002c-112">No es necesario ningún paso de instalación adicional.</span><span class="sxs-lookup"><span data-stu-id="2002c-112">There are no additional installation steps.</span></span><br /><br /> <span data-ttu-id="2002c-113">El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación ***automáticamente*** instala el cliente objeto modelo SharePoint redistribuible, que también está disponible en [http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482).</span><span class="sxs-lookup"><span data-stu-id="2002c-113">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation ***automatically*** installs the SharePoint Client Object Model Redistributable, which is also available at [http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482).</span></span>|  
|<span data-ttu-id="2002c-114">Servicio Web de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] de SSOM</span><span class="sxs-lookup"><span data-stu-id="2002c-114">SSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web Service</span></span>|<span data-ttu-id="2002c-115">**Opción obsoleta**.</span><span class="sxs-lookup"><span data-stu-id="2002c-115">**Deprecated**.</span></span> <span data-ttu-id="2002c-116">Con esta opción, se utiliza el modelo de objetos cliente de servicio (SSOM) de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2002c-116">Uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Service Side Object Model (SSOM).</span></span><br /><br /> <span data-ttu-id="2002c-117">El servicio web se instala en el PC de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], lo que puede ser en el mismo PC que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o en uno distinto.</span><span class="sxs-lookup"><span data-stu-id="2002c-117">The web service is installed on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer, which can be on the same computer as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a separate computer.</span></span><br /><br /> <span data-ttu-id="2002c-118">Para instalar el servicio web, ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación en el [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] equipo y compruebe **adaptador de Windows SharePoint Services**.</span><span class="sxs-lookup"><span data-stu-id="2002c-118">To install the web service, run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer and check **Windows SharePoint Services Adapter**.</span></span>|  
  
 <span data-ttu-id="2002c-119">[Apéndice B: instalar el adaptador de SharePoint de Microsoft](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) proporciona más información sobre la [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="2002c-119">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) provides more information on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] installation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2002c-120">En este momento, no se admite la autenticación federada.</span><span class="sxs-lookup"><span data-stu-id="2002c-120">Currently, federated authentication is not supported.</span></span> <span data-ttu-id="2002c-121">Se admiten únicamente el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="2002c-121">Only Username and Password are supported.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2002c-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2002c-122">In This Section</span></span>  
  
-   [<span data-ttu-id="2002c-123">CSOM: Adaptador de servicios de SharePoint</span><span class="sxs-lookup"><span data-stu-id="2002c-123">CSOM: SharePoint Services Adapter</span></span>](../core/csom-sharepoint-services-adapter.md)  
  
-   [<span data-ttu-id="2002c-124">SSOM: Servicio Web de adaptador SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="2002c-124">SSOM: SharePoint Services Adapter Web Service</span></span>](../core/ssom-sharepoint-services-adapter-web-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="2002c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2002c-125">See Also</span></span>  
 <span data-ttu-id="2002c-126">[Uso de adaptadores](../core/using-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="2002c-126">[Using Adapters](../core/using-adapters.md) </span></span>  
 [<span data-ttu-id="2002c-127">Desarrollar aplicaciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2002c-127">Developing BizTalk Server Applications</span></span>](../core/developing-biztalk-server-applications.md)