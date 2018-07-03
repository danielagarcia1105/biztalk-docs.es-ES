---
title: Dirección no válida (uri relativo) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a953f3e-3768-4e61-8f25-ea958a5a701a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd362112a8edff37650aaa83da9c6ab33d0d697a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017402"
---
# <a name="invalid-address-relative-uri"></a><span data-ttu-id="fe458-102">Dirección no válida (uri relativo)</span><span class="sxs-lookup"><span data-stu-id="fe458-102">Invalid address (relative uri)</span></span>
## <a name="details"></a><span data-ttu-id="fe458-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fe458-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="fe458-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fe458-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="fe458-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fe458-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="fe458-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fe458-106">Event ID</span></span>     |                                        <span data-ttu-id="fe458-107">000</span><span class="sxs-lookup"><span data-stu-id="fe458-107">000</span></span>                                         |
|  <span data-ttu-id="fe458-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fe458-108">Event Source</span></span>   |                                         <span data-ttu-id="fe458-109">0</span><span class="sxs-lookup"><span data-stu-id="fe458-109">0</span></span>                                          |
|    <span data-ttu-id="fe458-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fe458-110">Component</span></span>    |                                         <span data-ttu-id="fe458-111">0</span><span class="sxs-lookup"><span data-stu-id="fe458-111">0</span></span>                                          |
|  <span data-ttu-id="fe458-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fe458-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="fe458-113">0</span><span class="sxs-lookup"><span data-stu-id="fe458-113">0</span></span>                                          |
|  <span data-ttu-id="fe458-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fe458-114">Message Text</span></span>   |                  <span data-ttu-id="fe458-115">Esquema de dirección no válida. se esperaba "{0}" esquema.</span><span class="sxs-lookup"><span data-stu-id="fe458-115">Invalid address scheme; expecting "{0}" scheme.</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="fe458-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="fe458-116">Explanation</span></span>  
 <span data-ttu-id="fe458-117">No proporcionó una ubicación de recepción WCF aislada con una dirección relativa bien formada.</span><span class="sxs-lookup"><span data-stu-id="fe458-117">You did not provide an isolated WCF receive location with a well-formed relative address.</span></span> <span data-ttu-id="fe458-118">Por ejemplo, http://localhost/svc no funcionará como una dirección relativa.</span><span class="sxs-lookup"><span data-stu-id="fe458-118">For example, http://localhost/svc will not work as a relative address.</span></span> <span data-ttu-id="fe458-119">No puede establecer la propiedad Dirección de la ubicación de recepción WCF aislada en una dirección absoluta.</span><span class="sxs-lookup"><span data-stu-id="fe458-119">You cannot set the Address property of the isolated WCF receive location to a absolute address.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fe458-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fe458-120">User Action</span></span>  
 <span data-ttu-id="fe458-121">Use el procedimiento siguiente para configurar la dirección de ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="fe458-121">Use the following procedure to configure the receive location address.</span></span>  
  
#### <a name="to-configure-the-receive-location-address"></a><span data-ttu-id="fe458-122">Para configurar la dirección de ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="fe458-122">To configure the receive location address</span></span>  
  
1. <span data-ttu-id="fe458-123">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="fe458-123">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="fe458-124">En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="fe458-124">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="fe458-125">Busque la aplicación y el icono buscar su transporte.</span><span class="sxs-lookup"><span data-stu-id="fe458-125">Locate your application and the locate your transport.</span></span>  
  
4. <span data-ttu-id="fe458-126">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="fe458-126">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="fe458-127">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fe458-127">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="fe458-128">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="fe458-128">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="fe458-129">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="fe458-129">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="fe458-130">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="fe458-130">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="fe458-131">En el **dirección (URI)** texto, cambie la dirección para que comience con una barra diagonal ("/").</span><span class="sxs-lookup"><span data-stu-id="fe458-131">In the **Address (URI)** text box, change the address so that it starts with a forward slash ("/").</span></span>  
  
   <span data-ttu-id="fe458-132">Para obtener más información sobre las ubicaciones de recepción, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="fe458-132">For additional information on receive locations, see the following resources:</span></span>  
  
-   [<span data-ttu-id="fe458-133">Cómo configurar ubicación de recepción de un WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="fe458-133">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="fe458-134">Cómo configurar ubicación de recepción de un WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="fe458-134">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="fe458-135">Cómo configurar ubicación de recepción de un WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="fe458-135">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)