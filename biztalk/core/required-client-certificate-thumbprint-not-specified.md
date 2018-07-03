---
title: Requiere la huella digital de certificado de cliente no especificada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19307bdb-29d7-4a79-9472-dda24dd8b263
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bea510fba1a9c4ab972229042e7af1e22cc2ad8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993477"
---
# <a name="required-client-certificate-thumbprint-not-specified"></a><span data-ttu-id="1d3ab-102">Huella digital de certificado de cliente necesaria no especificada</span><span class="sxs-lookup"><span data-stu-id="1d3ab-102">Required client certificate thumbprint not specified</span></span>
## <a name="details"></a><span data-ttu-id="1d3ab-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1d3ab-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="1d3ab-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1d3ab-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="1d3ab-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1d3ab-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="1d3ab-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1d3ab-106">Event ID</span></span>     |                                         <span data-ttu-id="1d3ab-107">0</span><span class="sxs-lookup"><span data-stu-id="1d3ab-107">0</span></span>                                          |
|  <span data-ttu-id="1d3ab-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1d3ab-108">Event Source</span></span>   |                                         <span data-ttu-id="1d3ab-109">0</span><span class="sxs-lookup"><span data-stu-id="1d3ab-109">0</span></span>                                          |
|    <span data-ttu-id="1d3ab-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1d3ab-110">Component</span></span>    |                                         <span data-ttu-id="1d3ab-111">0</span><span class="sxs-lookup"><span data-stu-id="1d3ab-111">0</span></span>                                          |
|  <span data-ttu-id="1d3ab-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1d3ab-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="1d3ab-113">0</span><span class="sxs-lookup"><span data-stu-id="1d3ab-113">0</span></span>                                          |
|  <span data-ttu-id="1d3ab-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1d3ab-114">Message Text</span></span>   |               <span data-ttu-id="1d3ab-115">Huella digital de certificado de cliente necesaria no especificada.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-115">Required client certificate thumbprint not specified.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="1d3ab-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1d3ab-116">Explanation</span></span>  
 <span data-ttu-id="1d3ab-117">No estableció la propiedad de certificado de cliente necesaria para la configuración de seguridad de un puerto de envío WCF.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-117">You did not set the Client certificate property required for the security settings of a WCF send port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d3ab-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1d3ab-118">User Action</span></span>  
 <span data-ttu-id="1d3ab-119">Use el procedimiento siguiente para configurar los valores de seguridad de un puerto de envío WCF.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-119">Use the following procedure to configure security settings of a WCF send port.</span></span>  
  
#### <a name="to-configure-security-settings"></a><span data-ttu-id="1d3ab-120">Para configurar la seguridad</span><span class="sxs-lookup"><span data-stu-id="1d3ab-120">To configure security settings</span></span>  
  
1. <span data-ttu-id="1d3ab-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="1d3ab-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="1d3ab-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="1d3ab-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="1d3ab-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="1d3ab-126">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="1d3ab-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="1d3ab-128">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **seguridad** ficha.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="1d3ab-129">Asegúrese de que el **certificado de cliente** se configura la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1d3ab-129">Ensure that the **Client certificate** property is configured.</span></span>  
  
   <span data-ttu-id="1d3ab-130">Para obtener más información sobre certificados, vea el recurso siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d3ab-130">For additional information on certificates, see the following resource:</span></span>  
  
-   [<span data-ttu-id="1d3ab-131">Instalación de certificados para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="1d3ab-131">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)