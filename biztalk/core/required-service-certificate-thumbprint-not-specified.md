---
title: Requiere la huella digital de certificado de servicio no se especifica | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca853667-83b5-41f2-9b54-8117b87e27d3
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba137cd221d6cfa0ac373213d0c43dd49eafd756
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003765"
---
# <a name="required-service-certificate-thumbprint-not-specified"></a><span data-ttu-id="650c3-102">Huella digital de certificado de servicio necesaria no especificada.</span><span class="sxs-lookup"><span data-stu-id="650c3-102">Required service certificate thumbprint not specified</span></span>
## <a name="details"></a><span data-ttu-id="650c3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="650c3-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="650c3-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="650c3-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="650c3-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="650c3-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="650c3-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="650c3-106">Event ID</span></span>     |                                         <span data-ttu-id="650c3-107">0</span><span class="sxs-lookup"><span data-stu-id="650c3-107">0</span></span>                                          |
|  <span data-ttu-id="650c3-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="650c3-108">Event Source</span></span>   |                                         <span data-ttu-id="650c3-109">0</span><span class="sxs-lookup"><span data-stu-id="650c3-109">0</span></span>                                          |
|    <span data-ttu-id="650c3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="650c3-110">Component</span></span>    |                                         <span data-ttu-id="650c3-111">0</span><span class="sxs-lookup"><span data-stu-id="650c3-111">0</span></span>                                          |
|  <span data-ttu-id="650c3-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="650c3-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="650c3-113">0</span><span class="sxs-lookup"><span data-stu-id="650c3-113">0</span></span>                                          |
|  <span data-ttu-id="650c3-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="650c3-114">Message Text</span></span>   |               <span data-ttu-id="650c3-115">Huella digital de certificado de servicio necesaria no especificada.</span><span class="sxs-lookup"><span data-stu-id="650c3-115">Required service certificate thumbprint not specified</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="650c3-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="650c3-116">Explanation</span></span>  
 <span data-ttu-id="650c3-117">No estableció la propiedad de certificado de servicio necesaria para la configuración de seguridad de un puerto de envío WCF.</span><span class="sxs-lookup"><span data-stu-id="650c3-117">You did not set the Service certificate property required for the security settings of a WCF send port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="650c3-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="650c3-118">User Action</span></span>  
 <span data-ttu-id="650c3-119">Use el procedimiento siguiente para configurar la propiedad de certificado de servicio.</span><span class="sxs-lookup"><span data-stu-id="650c3-119">Use the following procedure to configure the Service certificate property.</span></span>  
  
#### <a name="to-configure-the-service-certificate-property"></a><span data-ttu-id="650c3-120">Para configurar la propiedad de certificado de servicio</span><span class="sxs-lookup"><span data-stu-id="650c3-120">To configure the Service certificate property</span></span>  
  
1. <span data-ttu-id="650c3-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="650c3-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="650c3-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="650c3-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="650c3-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="650c3-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="650c3-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="650c3-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="650c3-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="650c3-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="650c3-126">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="650c3-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="650c3-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="650c3-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="650c3-128">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **seguridad** ficha.</span><span class="sxs-lookup"><span data-stu-id="650c3-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="650c3-129">Asegúrese de que el **certificado de servicio** se configura la propiedad.</span><span class="sxs-lookup"><span data-stu-id="650c3-129">Ensure that the **Service certificate** property is configured.</span></span>  
  
   <span data-ttu-id="650c3-130">Para obtener más información sobre certificados, vea el recurso siguiente:</span><span class="sxs-lookup"><span data-stu-id="650c3-130">For additional information on certificates, see the following resource:</span></span>  
  
-   [<span data-ttu-id="650c3-131">Instalación de certificados para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="650c3-131">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)