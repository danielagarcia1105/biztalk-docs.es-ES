---
title: No se pudo crear X509CertificateIdentity a partir de la referencia de certificado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3acee8e-c035-4e58-8bfc-397885b4d185
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b991f9acb2b5cc193d24d36e1a5de8650e7af72b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988933"
---
# <a name="failed-to-create-x509certificateidentity-from-certificate-reference"></a><span data-ttu-id="49a71-102">No se pudo crear X509CertificateIdentity a partir de la referencia de certificado</span><span class="sxs-lookup"><span data-stu-id="49a71-102">Failed to create X509CertificateIdentity from certificate reference</span></span>
## <a name="details"></a><span data-ttu-id="49a71-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="49a71-103">Details</span></span>  

|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="49a71-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="49a71-104">Product Name</span></span>   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| <span data-ttu-id="49a71-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="49a71-105">Product Version</span></span> |                                         [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                         |
|    <span data-ttu-id="49a71-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="49a71-106">Event ID</span></span>     |                                                                     <span data-ttu-id="49a71-107">0</span><span class="sxs-lookup"><span data-stu-id="49a71-107">0</span></span>                                                                      |
|  <span data-ttu-id="49a71-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="49a71-108">Event Source</span></span>   |                                                                     <span data-ttu-id="49a71-109">0</span><span class="sxs-lookup"><span data-stu-id="49a71-109">0</span></span>                                                                      |
|    <span data-ttu-id="49a71-110">Componente</span><span class="sxs-lookup"><span data-stu-id="49a71-110">Component</span></span>    |                                                                     <span data-ttu-id="49a71-111">0</span><span class="sxs-lookup"><span data-stu-id="49a71-111">0</span></span>                                                                      |
|  <span data-ttu-id="49a71-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="49a71-112">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="49a71-113">0</span><span class="sxs-lookup"><span data-stu-id="49a71-113">0</span></span>                                                                      |
|  <span data-ttu-id="49a71-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="49a71-114">Message Text</span></span>   | <span data-ttu-id="49a71-115">No se pudo crear X509CertificateIdentity a partir de la referencia de certificado.</span><span class="sxs-lookup"><span data-stu-id="49a71-115">Failed to create X509CertificateIdentity from certificate reference.</span></span> <span data-ttu-id="49a71-116">(StoreName ={0}, StoreLocation ={1}, X509FindType ={2}, FindValue = "{3}")</span><span class="sxs-lookup"><span data-stu-id="49a71-116">(StoreName={0}, StoreLocation={1}, X509FindType={2}, FindValue="{3}")</span></span> |

## <a name="explanation"></a><span data-ttu-id="49a71-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="49a71-117">Explanation</span></span>  
 <span data-ttu-id="49a71-118">Este error indica que el adaptador no pudo crear el X509Certificate especificado en la configuración de identidad de extremo.</span><span class="sxs-lookup"><span data-stu-id="49a71-118">This error indicates the adapter failed to create the X509Certificate specified in the endpoint identity configuration.</span></span>  

## <a name="user-action"></a><span data-ttu-id="49a71-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="49a71-119">User Action</span></span>  
 <span data-ttu-id="49a71-120">Use el procedimiento siguiente para comprobar las opciones de referencia de certificado.</span><span class="sxs-lookup"><span data-stu-id="49a71-120">Use the following procedure to verify the certificate reference settings.</span></span>  

#### <a name="to-configure-the-certificate-reference-settings"></a><span data-ttu-id="49a71-121">Para configurar las opciones de referencia de certificado</span><span class="sxs-lookup"><span data-stu-id="49a71-121">To configure the certificate reference settings</span></span>  

1. <span data-ttu-id="49a71-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="49a71-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="49a71-123">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="49a71-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="49a71-124">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="49a71-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="49a71-125">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="49a71-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="49a71-126">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="49a71-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="49a71-127">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="49a71-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="49a71-128">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="49a71-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="49a71-129">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="49a71-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  

9. <span data-ttu-id="49a71-130">En el **identidad de extremo** sección, haga clic en **editar.**</span><span class="sxs-lookup"><span data-stu-id="49a71-130">In the **Endpoint Identity** section, click **Edit.**</span></span>  

10. <span data-ttu-id="49a71-131">En el **Editor de identidad** diálogo cuadro, asegúrese de que el **referencia de certificado** configuración es válida.</span><span class="sxs-lookup"><span data-stu-id="49a71-131">In the **Identity Editor** dialog box, ensure that the **Certificate Reference** settings are valid.</span></span>
