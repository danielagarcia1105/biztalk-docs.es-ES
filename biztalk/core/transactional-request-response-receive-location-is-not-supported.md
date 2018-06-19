---
title: Ubicación de recepción de solicitud-respuesta transaccional no se admite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c89b619-280c-4ab5-b6aa-06b14a075f8e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34de32b338a78b598941d4e828c1a0b736dde4e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278516"
---
# <a name="transactional-request-response-receive-location-is-not-supported"></a><span data-ttu-id="d9c91-102">La ubicación de recepción de solicitud-respuesta transaccional no es compatible</span><span class="sxs-lookup"><span data-stu-id="d9c91-102">Transactional request-response receive location is not supported</span></span>
## <a name="details"></a><span data-ttu-id="d9c91-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d9c91-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9c91-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d9c91-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d9c91-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d9c91-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="d9c91-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d9c91-106">Event ID</span></span>|<span data-ttu-id="d9c91-107">0</span><span class="sxs-lookup"><span data-stu-id="d9c91-107">0</span></span>|  
|<span data-ttu-id="d9c91-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d9c91-108">Event Source</span></span>|<span data-ttu-id="d9c91-109">0</span><span class="sxs-lookup"><span data-stu-id="d9c91-109">0</span></span>|  
|<span data-ttu-id="d9c91-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d9c91-110">Component</span></span>|<span data-ttu-id="d9c91-111">0</span><span class="sxs-lookup"><span data-stu-id="d9c91-111">0</span></span>|  
|<span data-ttu-id="d9c91-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d9c91-112">Symbolic Name</span></span>|<span data-ttu-id="d9c91-113">0</span><span class="sxs-lookup"><span data-stu-id="d9c91-113">0</span></span>|  
|<span data-ttu-id="d9c91-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d9c91-114">Message Text</span></span>|<span data-ttu-id="d9c91-115">La ubicación de recepción de solicitud-respuesta transaccional no es compatible.</span><span class="sxs-lookup"><span data-stu-id="d9c91-115">Transactional request-response receive location is not supported.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d9c91-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="d9c91-116">Explanation</span></span>  
 <span data-ttu-id="d9c91-117">Este error indica que la transacción se estableció para habilitarse para una ubicación de recepción de solicitud-respuesta de WCF.</span><span class="sxs-lookup"><span data-stu-id="d9c91-117">This error indicates that the transaction was set to be enabled for a WCF request-response receive location.</span></span> <span data-ttu-id="d9c91-118">BizTalk no admite las transacciones para una ubicación de recepción de solicitud-respuesta debido a la base de datos de cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d9c91-118">Transactions are not supported in BizTalk for a request-response receive location due to the message box database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d9c91-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d9c91-119">User Action</span></span>  
 <span data-ttu-id="d9c91-120">Para los adaptadores de WCF estándar, vaya al código que configura la ubicación de recepción de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="d9c91-120">For the standard WCF adapters, go to the code configuring the request-response receive location.</span></span> <span data-ttu-id="d9c91-121">Asegúrese de que el **EnableTransaction** elemento de los datos XML para el **TransportTypeData** propiedad de la **ITransportInfo** interfaz se establece en **False** .</span><span class="sxs-lookup"><span data-stu-id="d9c91-121">Ensure that the **EnableTransaction** element in the XML data for the **TransportTypeData** property of the **ITransportInfo** interface is set to **False**.</span></span>  
  
 <span data-ttu-id="d9c91-122">Para los adaptadores de WCF-Custom:</span><span class="sxs-lookup"><span data-stu-id="d9c91-122">For the WCF-Custom adapters:</span></span>  
  
1.  <span data-ttu-id="d9c91-123">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="d9c91-123">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d9c91-124">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="d9c91-124">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="d9c91-125">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="d9c91-125">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="d9c91-126">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="d9c91-126">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="d9c91-127">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d9c91-127">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="d9c91-128">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="d9c91-128">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="d9c91-129">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="d9c91-129">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="d9c91-130">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="d9c91-130">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="d9c91-131">Asegúrese de que la propiedad transactionFlow está establecida en **False**.</span><span class="sxs-lookup"><span data-stu-id="d9c91-131">Ensure that the transactionFlow property is set to **False**.</span></span>