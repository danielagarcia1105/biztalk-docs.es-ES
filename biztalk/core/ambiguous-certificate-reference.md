---
title: Referencia de certificado ambigua | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7a6a60d-97e6-4c60-86be-83efb4a50f99
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 304ded9572ba6598f7f2132a678a14b2b3301c10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230708"
---
# <a name="ambiguous-certificate-reference"></a><span data-ttu-id="5e187-102">Referencia de certificado ambigua</span><span class="sxs-lookup"><span data-stu-id="5e187-102">Ambiguous certificate reference</span></span>
## <a name="details"></a><span data-ttu-id="5e187-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5e187-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e187-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5e187-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5e187-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5e187-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="5e187-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5e187-106">Event ID</span></span>|<span data-ttu-id="5e187-107">0</span><span class="sxs-lookup"><span data-stu-id="5e187-107">0</span></span>|  
|<span data-ttu-id="5e187-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5e187-108">Event Source</span></span>|<span data-ttu-id="5e187-109">0</span><span class="sxs-lookup"><span data-stu-id="5e187-109">0</span></span>|  
|<span data-ttu-id="5e187-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5e187-110">Component</span></span>|<span data-ttu-id="5e187-111">0</span><span class="sxs-lookup"><span data-stu-id="5e187-111">0</span></span>|  
|<span data-ttu-id="5e187-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5e187-112">Symbolic Name</span></span>|<span data-ttu-id="5e187-113">0</span><span class="sxs-lookup"><span data-stu-id="5e187-113">0</span></span>|  
|<span data-ttu-id="5e187-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5e187-114">Message Text</span></span>|<span data-ttu-id="5e187-115">Referencia de certificado ambigua; se ha encontrado más de un certificado válido.</span><span class="sxs-lookup"><span data-stu-id="5e187-115">Ambiguous certificate reference; more than one valid certificate found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5e187-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="5e187-116">Explanation</span></span>  
 <span data-ttu-id="5e187-117">Se ha encontrado más de un certificado válido.</span><span class="sxs-lookup"><span data-stu-id="5e187-117">More than one valid certificate was found.</span></span>  
  
#### <a name="user-action"></a><span data-ttu-id="5e187-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5e187-118">User action</span></span>  
 <span data-ttu-id="5e187-119">Comprobar solo un certificado válido configurado.</span><span class="sxs-lookup"><span data-stu-id="5e187-119">Verify only one valid certificate is configured.</span></span>  
  
## <a name="verify-certificate"></a><span data-ttu-id="5e187-120">Comprobar el certificado</span><span class="sxs-lookup"><span data-stu-id="5e187-120">Verify certificate</span></span> 
  
1.  <span data-ttu-id="5e187-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="5e187-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5e187-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="5e187-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="5e187-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="5e187-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="5e187-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="5e187-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="5e187-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5e187-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="5e187-126">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="5e187-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="5e187-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="5e187-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="5e187-128">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="5e187-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="5e187-129">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5e187-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="5e187-130">En el **Editor de identidad** diálogo cuadro, asegúrese de que los criterios de búsqueda en el **referencia de certificado** sección está configurada correctamente para indicar únicamente un certificado en el certificado **almacén nombre**.</span><span class="sxs-lookup"><span data-stu-id="5e187-130">In the **Identity Editor** dialog box, make sure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
## <a name="verify-a-certificate-for-the-wcf-custom-and-the-wcf-customisolated-adapters"></a><span data-ttu-id="5e187-131">Comprobar que un certificado de WCF-Custom y los adaptadores de WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="5e187-131">Verify a certificate for the WCF-Custom and the WCF-CustomIsolated adapters</span></span>  
  
1.  <span data-ttu-id="5e187-132">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e187-132">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="5e187-133">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="5e187-133">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="5e187-134">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="5e187-134">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="5e187-135">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="5e187-135">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="5e187-136">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5e187-136">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="5e187-137">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="5e187-137">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="5e187-138">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="5e187-138">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="5e187-139">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **comportamiento** ficha.</span><span class="sxs-lookup"><span data-stu-id="5e187-139">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
9. <span data-ttu-id="5e187-140">Asegúrese de los criterios de búsqueda en el **referencia de certificado** sección está configurada correctamente para indicar únicamente un certificado en el certificado **nombre del almacén**.</span><span class="sxs-lookup"><span data-stu-id="5e187-140">Ensure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
10. <span data-ttu-id="5e187-141">En el complemento Certificado, asegúrese de que únicamente esté instalado un certificado para los criterios de búsqueda que configuró para el transporte WCF.</span><span class="sxs-lookup"><span data-stu-id="5e187-141">In the Certificate snap-in, make sure only one certificate is installed for the search criteria you configured to the WCF transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e187-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e187-142">See also</span></span>
[<span data-ttu-id="5e187-143">Instalación de certificados para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="5e187-143">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
 