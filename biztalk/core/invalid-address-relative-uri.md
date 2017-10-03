---
title: "Dirección no válida (uri relativo) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a953f3e-3768-4e61-8f25-ea958a5a701a
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 101a4544a83eb02438478d6d526dba422c44ae7b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-relative-uri"></a><span data-ttu-id="7b068-102">Dirección no válida (uri relativo)</span><span class="sxs-lookup"><span data-stu-id="7b068-102">Invalid address (relative uri)</span></span>
## <a name="details"></a><span data-ttu-id="7b068-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7b068-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b068-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7b068-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7b068-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7b068-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="7b068-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7b068-106">Event ID</span></span>|<span data-ttu-id="7b068-107">000</span><span class="sxs-lookup"><span data-stu-id="7b068-107">000</span></span>|  
|<span data-ttu-id="7b068-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7b068-108">Event Source</span></span>|<span data-ttu-id="7b068-109">0</span><span class="sxs-lookup"><span data-stu-id="7b068-109">0</span></span>|  
|<span data-ttu-id="7b068-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7b068-110">Component</span></span>|<span data-ttu-id="7b068-111">0</span><span class="sxs-lookup"><span data-stu-id="7b068-111">0</span></span>|  
|<span data-ttu-id="7b068-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7b068-112">Symbolic Name</span></span>|<span data-ttu-id="7b068-113">0</span><span class="sxs-lookup"><span data-stu-id="7b068-113">0</span></span>|  
|<span data-ttu-id="7b068-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7b068-114">Message Text</span></span>|<span data-ttu-id="7b068-115">Esquema de dirección no válido; se esperaba el esquema "{0}".</span><span class="sxs-lookup"><span data-stu-id="7b068-115">Invalid address scheme; expecting "{0}" scheme.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7b068-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="7b068-116">Explanation</span></span>  
 <span data-ttu-id="7b068-117">No proporcionó una ubicación de recepción WCF aislada con una dirección relativa bien formada.</span><span class="sxs-lookup"><span data-stu-id="7b068-117">You did not provide an isolated WCF receive location with a well-formed relative address.</span></span> <span data-ttu-id="7b068-118">Por ejemplo, http://localhost/svc no funcionará como dirección relativa.</span><span class="sxs-lookup"><span data-stu-id="7b068-118">For example, http://localhost/svc will not work as a relative address.</span></span> <span data-ttu-id="7b068-119">No puede establecer la propiedad Dirección de la ubicación de recepción WCF aislada en una dirección absoluta.</span><span class="sxs-lookup"><span data-stu-id="7b068-119">You cannot set the Address property of the isolated WCF receive location to a absolute address.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b068-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7b068-120">User Action</span></span>  
 <span data-ttu-id="7b068-121">Use el procedimiento siguiente para configurar la dirección de ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="7b068-121">Use the following procedure to configure the receive location address.</span></span>  
  
#### <a name="to-configure-the-receive-location-address"></a><span data-ttu-id="7b068-122">Para configurar la dirección de ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="7b068-122">To configure the receive location address</span></span>  
  
1.  <span data-ttu-id="7b068-123">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="7b068-123">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7b068-124">En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="7b068-124">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="7b068-125">Busque la aplicación y el icono buscar su transporte.</span><span class="sxs-lookup"><span data-stu-id="7b068-125">Locate your application and the locate your transport.</span></span>  
  
4.  <span data-ttu-id="7b068-126">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="7b068-126">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="7b068-127">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7b068-127">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="7b068-128">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="7b068-128">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="7b068-129">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7b068-129">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="7b068-130">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="7b068-130">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="7b068-131">En el **dirección (URI)** texto, cambie la dirección para que se inicie con una barra diagonal ("/").</span><span class="sxs-lookup"><span data-stu-id="7b068-131">In the **Address (URI)** text box, change the address so that it starts with a forward slash ("/").</span></span>  
  
 <span data-ttu-id="7b068-132">Para obtener más información sobre las ubicaciones de recepción, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="7b068-132">For additional information on receive locations, see the following resources:</span></span>  
  
-   [<span data-ttu-id="7b068-133">Cómo configurar un WCF-CustomIsolated ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="7b068-133">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="7b068-134">Cómo configurar un WCF-WSHttp ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="7b068-134">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="7b068-135">Cómo configurar un WCF-BasicHttp ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="7b068-135">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)