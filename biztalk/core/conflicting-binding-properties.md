---
title: En conflicto propiedades de enlace | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b08c317e-a617-464b-9ee4-007fb41d99b2
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6202385127a676d1f2714b2c3644d135a3d6a7a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="conflicting-binding-properties"></a><span data-ttu-id="9d32b-102">Propiedades de enlace conflictivas</span><span class="sxs-lookup"><span data-stu-id="9d32b-102">Conflicting binding properties</span></span>
## <a name="details"></a><span data-ttu-id="9d32b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9d32b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d32b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9d32b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9d32b-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9d32b-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="9d32b-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9d32b-106">Event ID</span></span>|<span data-ttu-id="9d32b-107">0</span><span class="sxs-lookup"><span data-stu-id="9d32b-107">0</span></span>|  
|<span data-ttu-id="9d32b-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9d32b-108">Event Source</span></span>|<span data-ttu-id="9d32b-109">0</span><span class="sxs-lookup"><span data-stu-id="9d32b-109">0</span></span>|  
|<span data-ttu-id="9d32b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9d32b-110">Component</span></span>|<span data-ttu-id="9d32b-111">0</span><span class="sxs-lookup"><span data-stu-id="9d32b-111">0</span></span>|  
|<span data-ttu-id="9d32b-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9d32b-112">Symbolic Name</span></span>|<span data-ttu-id="9d32b-113">0</span><span class="sxs-lookup"><span data-stu-id="9d32b-113">0</span></span>|  
|<span data-ttu-id="9d32b-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9d32b-114">Message Text</span></span>|<span data-ttu-id="9d32b-115">En conflicto propiedades de enlace: MsmqAuthenticationMode = {0} y MsmqProtectionLevel = \ {1\\} no es válido.</span><span class="sxs-lookup"><span data-stu-id="9d32b-115">Conflicting binding properties: MsmqAuthenticationMode={0} and MsmqProtectionLevel={1} is invalid.</span></span> <span data-ttu-id="9d32b-116">Cambie una de las propiedades para resolver el conflicto.</span><span class="sxs-lookup"><span data-stu-id="9d32b-116">Change one of the properties to resolve the conflict</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9d32b-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="9d32b-117">Explanation</span></span>  
 <span data-ttu-id="9d32b-118">La propiedad de nivel de protección de MSMQ de un transporte de WCF-NetMsmq se estableció en **inicio de sesión** o **EncryptAndSign** para el modo de autenticación de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9d32b-118">The MSMQ protection level property of a WCF-NetMsmq transport was set to **Sign** or **EncryptAndSign** for the None MSMQ authentication mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9d32b-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9d32b-119">User Action</span></span>  
 <span data-ttu-id="9d32b-120">Cambie las propiedades de nivel de protección de MSMQ o modo de autenticación de MSMQ para que sea coherente con la propiedad de nivel de protección de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9d32b-120">Change the MSMQ protection level or the MSMQ authentication mode property to be consistent with the MSMQ protection level property.</span></span>  
  
1.  <span data-ttu-id="9d32b-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="9d32b-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9d32b-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9d32b-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="9d32b-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="9d32b-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="9d32b-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="9d32b-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="9d32b-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9d32b-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="9d32b-126">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="9d32b-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="9d32b-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="9d32b-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="9d32b-128">En el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, haga clic en el **seguridad** ficha.</span><span class="sxs-lookup"><span data-stu-id="9d32b-128">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="9d32b-129">Compruebe los valores de MSMQ **modo de autenticación** lista y **nivel de protección de MSMQ** lista.</span><span class="sxs-lookup"><span data-stu-id="9d32b-129">Check the values in the MSMQ **authentication mode** list and the **MSMQ protection level** list.</span></span>  
  
 <span data-ttu-id="9d32b-130">Para obtener más información, vea los recursos siguientes en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9d32b-130">For further information, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="9d32b-131">Cómo configurar un puerto de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="9d32b-131">How to Configure a WCF-NetMsmq Send Port</span></span>](../core/how-to-configure-a-wcf-netmsmq-send-port.md)  
  
-   [<span data-ttu-id="9d32b-132">Cómo configurar un WCF-NetMsmq ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="9d32b-132">How to Configure a WCF-NetMsmq Receive Location</span></span>](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)