---
title: En conflicto las propiedades de enlace | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b08c317e-a617-464b-9ee4-007fb41d99b2
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 271b9efa9d30d5c315bfd6061bfbf011289ea620
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012085"
---
# <a name="conflicting-binding-properties"></a><span data-ttu-id="6b1d7-102">Propiedades de enlace conflictivas</span><span class="sxs-lookup"><span data-stu-id="6b1d7-102">Conflicting binding properties</span></span>
## <a name="details"></a><span data-ttu-id="6b1d7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6b1d7-103">Details</span></span>  
  
|                 |                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6b1d7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6b1d7-104">Product Name</span></span>   |                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                    |
| <span data-ttu-id="6b1d7-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6b1d7-105">Product Version</span></span> |                                               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                |
|    <span data-ttu-id="6b1d7-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6b1d7-106">Event ID</span></span>     |                                                                            <span data-ttu-id="6b1d7-107">0</span><span class="sxs-lookup"><span data-stu-id="6b1d7-107">0</span></span>                                                                            |
|  <span data-ttu-id="6b1d7-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6b1d7-108">Event Source</span></span>   |                                                                            <span data-ttu-id="6b1d7-109">0</span><span class="sxs-lookup"><span data-stu-id="6b1d7-109">0</span></span>                                                                            |
|    <span data-ttu-id="6b1d7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6b1d7-110">Component</span></span>    |                                                                            <span data-ttu-id="6b1d7-111">0</span><span class="sxs-lookup"><span data-stu-id="6b1d7-111">0</span></span>                                                                            |
|  <span data-ttu-id="6b1d7-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6b1d7-112">Symbolic Name</span></span>  |                                                                            <span data-ttu-id="6b1d7-113">0</span><span class="sxs-lookup"><span data-stu-id="6b1d7-113">0</span></span>                                                                            |
|  <span data-ttu-id="6b1d7-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6b1d7-114">Message Text</span></span>   | <span data-ttu-id="6b1d7-115">En conflicto las propiedades de enlace: MsmqAuthenticationMode ={0} y MsmqProtectionLevel ={1} no es válido.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-115">Conflicting binding properties: MsmqAuthenticationMode={0} and MsmqProtectionLevel={1} is invalid.</span></span> <span data-ttu-id="6b1d7-116">Cambie una de las propiedades para resolver el conflicto.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-116">Change one of the properties to resolve the conflict</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6b1d7-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="6b1d7-117">Explanation</span></span>  
 <span data-ttu-id="6b1d7-118">La propiedad de nivel de protección de MSMQ de un transporte WCF-NetMsmq se estableció en **sesión** o **EncryptAndSign** para el modo de autenticación de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-118">The MSMQ protection level property of a WCF-NetMsmq transport was set to **Sign** or **EncryptAndSign** for the None MSMQ authentication mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6b1d7-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6b1d7-119">User Action</span></span>  
 <span data-ttu-id="6b1d7-120">Cambie las propiedades de nivel de protección de MSMQ o modo de autenticación de MSMQ para que sea coherente con la propiedad de nivel de protección de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-120">Change the MSMQ protection level or the MSMQ authentication mode property to be consistent with the MSMQ protection level property.</span></span>  
  
1. <span data-ttu-id="6b1d7-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="6b1d7-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3. <span data-ttu-id="6b1d7-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="6b1d7-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="6b1d7-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="6b1d7-126">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="6b1d7-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="6b1d7-128">En el **propiedades de transporte WCF-NetMsmq** cuadro de diálogo, haga clic en el **seguridad** ficha.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-128">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="6b1d7-129">Compruebe los valores de MSMQ **modo de autenticación** lista y **nivel de protección de MSMQ** lista.</span><span class="sxs-lookup"><span data-stu-id="6b1d7-129">Check the values in the MSMQ **authentication mode** list and the **MSMQ protection level** list.</span></span>  
  
   <span data-ttu-id="6b1d7-130">Para obtener más información, vea los recursos siguientes en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6b1d7-130">For further information, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="6b1d7-131">Cómo configurar un puerto de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="6b1d7-131">How to Configure a WCF-NetMsmq Send Port</span></span>](../core/how-to-configure-a-wcf-netmsmq-send-port.md)  
  
-   [<span data-ttu-id="6b1d7-132">Cómo configurar ubicación de recepción de un WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="6b1d7-132">How to Configure a WCF-NetMsmq Receive Location</span></span>](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)