---
title: No se pudo crear X509CertificateIdentity a partir de certificado codificado en base 64 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a13112bd-e0e8-4b49-ad2f-ea82b2e8162f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31cf07660b939beb3ea1a79fd0f34390f873d5cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="failed-to-create-x509certificateidentity-from-base-64-encoded-certificate"></a><span data-ttu-id="33792-102">No se pudo crear X509CertificateIdentity a partir de un certificado codificado base 64.</span><span class="sxs-lookup"><span data-stu-id="33792-102">Failed to create X509CertificateIdentity from base-64 encoded certificate</span></span>
## <a name="details"></a><span data-ttu-id="33792-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="33792-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33792-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="33792-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="33792-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="33792-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="33792-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="33792-106">Event ID</span></span>|<span data-ttu-id="33792-107">0</span><span class="sxs-lookup"><span data-stu-id="33792-107">0</span></span>|  
|<span data-ttu-id="33792-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="33792-108">Event Source</span></span>|<span data-ttu-id="33792-109">0</span><span class="sxs-lookup"><span data-stu-id="33792-109">0</span></span>|  
|<span data-ttu-id="33792-110">Componente</span><span class="sxs-lookup"><span data-stu-id="33792-110">Component</span></span>|<span data-ttu-id="33792-111">0</span><span class="sxs-lookup"><span data-stu-id="33792-111">0</span></span>|  
|<span data-ttu-id="33792-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="33792-112">Symbolic Name</span></span>|<span data-ttu-id="33792-113">0</span><span class="sxs-lookup"><span data-stu-id="33792-113">0</span></span>|  
|<span data-ttu-id="33792-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="33792-114">Message Text</span></span>|<span data-ttu-id="33792-115">No se pudo crear X509CertificateIdentity a partir de un certificado codificado base 64.</span><span class="sxs-lookup"><span data-stu-id="33792-115">Failed to create X509CertificateIdentity from base-64 encoded certificate</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="33792-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="33792-116">Explanation</span></span>  
 <span data-ttu-id="33792-117">Este error indica que el adaptador no pudo crear la identifidad de extremo X509Certificate debido a una opción de configuración de certificado no válida.</span><span class="sxs-lookup"><span data-stu-id="33792-117">This error indicates the adapter failed to create the X509Certificate endpoint identity because of an invalid certificate setting.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="33792-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="33792-118">User Action</span></span>  
 <span data-ttu-id="33792-119">Use el procedimiento siguiente para configurar certificados.</span><span class="sxs-lookup"><span data-stu-id="33792-119">Use the following procedure to configure certificates.</span></span>  
  
#### <a name="to-configure-certificates"></a><span data-ttu-id="33792-120">Para configurar certificados</span><span class="sxs-lookup"><span data-stu-id="33792-120">To configure certificates</span></span>  
  
1.  <span data-ttu-id="33792-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="33792-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="33792-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="33792-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="33792-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="33792-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="33792-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="33792-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="33792-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="33792-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="33792-126">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="33792-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="33792-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="33792-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="33792-128">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **seguridad** ficha.</span><span class="sxs-lookup"><span data-stu-id="33792-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="33792-129">Asegúrese de que la configuración es correcta para el **huella digital del certificado de cliente** y **huella digital del certificado de servicio**.</span><span class="sxs-lookup"><span data-stu-id="33792-129">Ensure that the settings are correct for the **Client Certificate Thumbprint** and the **Service Certificate Thumbprint**.</span></span>