---
title: No se encontró el certificado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 629b199f-1884-4e88-beaa-a2e5c5e792e9
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e636d37f6b8758934a25e3b45338ca7b19a4d076
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005701"
---
# <a name="certificate-not-found"></a><span data-ttu-id="07ddb-102">No se encontró el certificado</span><span class="sxs-lookup"><span data-stu-id="07ddb-102">Certificate not found</span></span>
## <a name="details"></a><span data-ttu-id="07ddb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="07ddb-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="07ddb-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="07ddb-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="07ddb-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="07ddb-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="07ddb-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="07ddb-106">Event ID</span></span>     |                                         <span data-ttu-id="07ddb-107">0</span><span class="sxs-lookup"><span data-stu-id="07ddb-107">0</span></span>                                          |
|  <span data-ttu-id="07ddb-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="07ddb-108">Event Source</span></span>   |                                         <span data-ttu-id="07ddb-109">0</span><span class="sxs-lookup"><span data-stu-id="07ddb-109">0</span></span>                                          |
|    <span data-ttu-id="07ddb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="07ddb-110">Component</span></span>    |                                         <span data-ttu-id="07ddb-111">0</span><span class="sxs-lookup"><span data-stu-id="07ddb-111">0</span></span>                                          |
|  <span data-ttu-id="07ddb-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="07ddb-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="07ddb-113">0</span><span class="sxs-lookup"><span data-stu-id="07ddb-113">0</span></span>                                          |
|  <span data-ttu-id="07ddb-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="07ddb-114">Message Text</span></span>   |                               <span data-ttu-id="07ddb-115">No se encontró el certificado.</span><span class="sxs-lookup"><span data-stu-id="07ddb-115">Certificate not found.</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="07ddb-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="07ddb-116">Explanation</span></span>  
 <span data-ttu-id="07ddb-117">No se encontró un certificado para los criterios de búsqueda dados.</span><span class="sxs-lookup"><span data-stu-id="07ddb-117">A certificate could not be found for the given search criteria.</span></span>  

#### <a name="user-action"></a><span data-ttu-id="07ddb-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="07ddb-118">User Action</span></span>
<span data-ttu-id="07ddb-119">Comprobar los criterios de búsqueda para los certificados.</span><span class="sxs-lookup"><span data-stu-id="07ddb-119">Verify search criteria for certificates.</span></span> 
  
## <a name="verify-search-criteria"></a><span data-ttu-id="07ddb-120">Comprobar los criterios de búsqueda</span><span class="sxs-lookup"><span data-stu-id="07ddb-120">Verify search criteria</span></span>  
  
1. <span data-ttu-id="07ddb-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="07ddb-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="07ddb-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="07ddb-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="07ddb-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="07ddb-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="07ddb-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="07ddb-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="07ddb-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="07ddb-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="07ddb-126">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="07ddb-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="07ddb-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="07ddb-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="07ddb-128">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="07ddb-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="07ddb-129">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="07ddb-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="07ddb-130">En el **Editor de identidad** diálogo cuadro, asegúrese de que los criterios de búsqueda en el **referencia de certificado** sección está configurada correctamente para indicar certificados válidos.</span><span class="sxs-lookup"><span data-stu-id="07ddb-130">In the **Identity Editor** dialog box, make sure that the search criteria in the **Certificate Reference** section is configured properly to indicate valid certificates.</span></span>  
  
    <span data-ttu-id="07ddb-131">Personalizada de WCF y los adaptadores de WCF-CustomIsolated, asegúrese de que los criterios de búsqueda en el **referencia de certificado** sección está configurada correctamente para indicar un certificado válido en el certificado **nombre Store** .</span><span class="sxs-lookup"><span data-stu-id="07ddb-131">For the WCF-Custom and the WCF-CustomIsolated adapters, ensure that the search criteria in the **Certificate Reference** section is configured properly to indicate a valid certificate in the certificate **Store name**.</span></span>  
  
## <a name="verify-search-criteria-for-standard-wcf-adapters"></a><span data-ttu-id="07ddb-132">Comprobar los criterios de búsqueda para adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="07ddb-132">Verify search criteria for standard WCF adapters</span></span>  
  
1. <span data-ttu-id="07ddb-133">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="07ddb-133">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="07ddb-134">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="07ddb-134">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3. <span data-ttu-id="07ddb-135">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="07ddb-135">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="07ddb-136">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="07ddb-136">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="07ddb-137">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="07ddb-137">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="07ddb-138">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="07ddb-138">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="07ddb-139">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="07ddb-139">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="07ddb-140">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **seguridad** ficha.</span><span class="sxs-lookup"><span data-stu-id="07ddb-140">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="07ddb-141">Asegúrese de que el **huella digital** propiedades para los certificados de servicio y cliente indiquen certificados válidos en almacenes de certificados.</span><span class="sxs-lookup"><span data-stu-id="07ddb-141">Ensure that the **Thumbprint** properties for the service and client certificates indicate valid certificates in certificate stores.</span></span>  
  
10. <span data-ttu-id="07ddb-142">En el complemento Certificado, asegúrese de que están instalados certificados válidos para el transporte WCF.</span><span class="sxs-lookup"><span data-stu-id="07ddb-142">In the Certificate snap-in, make sure that valid certificates are installed for the WCF transport.</span></span>  

## <a name="see-also"></a><span data-ttu-id="07ddb-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="07ddb-143">See also</span></span> 
  
-   [<span data-ttu-id="07ddb-144">Instalación de certificados para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="07ddb-144">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
  
