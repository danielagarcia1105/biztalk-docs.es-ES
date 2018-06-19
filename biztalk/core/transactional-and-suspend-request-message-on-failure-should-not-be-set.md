---
title: Opción de transacciones &quot;transaccional&quot; y la opción de control de errores &quot;suspender el mensaje de solicitud en caso de error&quot; deben no establecerse ambas como false | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc6c66cc-6713-4396-b0d4-ac6a0e72164f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8c47e364fccdb310167e56c6556423c2d4b39d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278932"
---
# <a name="transactions-option-quottransactionalquot-and-the-error-handling-option-quotsuspend-request-message-on-failurequot-should-not-both-be-set-to-false"></a><span data-ttu-id="6190c-102">Opción de transacciones &quot;transaccional&quot; y la opción de control de errores &quot;suspender el mensaje de solicitud en caso de error&quot; deben no establecerse ambas como false</span><span class="sxs-lookup"><span data-stu-id="6190c-102">Transactions option &quot;Transactional&quot; and the error handling option &quot;Suspend request message on failure&quot; should not both be set to false</span></span>
## <a name="details"></a><span data-ttu-id="6190c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6190c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6190c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6190c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="6190c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6190c-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="6190c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6190c-106">Event ID</span></span>|<span data-ttu-id="6190c-107">0</span><span class="sxs-lookup"><span data-stu-id="6190c-107">0</span></span>|  
|<span data-ttu-id="6190c-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6190c-108">Event Source</span></span>|<span data-ttu-id="6190c-109">0</span><span class="sxs-lookup"><span data-stu-id="6190c-109">0</span></span>|  
|<span data-ttu-id="6190c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6190c-110">Component</span></span>|<span data-ttu-id="6190c-111">0</span><span class="sxs-lookup"><span data-stu-id="6190c-111">0</span></span>|  
|<span data-ttu-id="6190c-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6190c-112">Symbolic Name</span></span>|<span data-ttu-id="6190c-113">0</span><span class="sxs-lookup"><span data-stu-id="6190c-113">0</span></span>|  
|<span data-ttu-id="6190c-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6190c-114">Message Text</span></span>|<span data-ttu-id="6190c-115">La opción de transacciones "Transaccional" y la opción de control de errores "Suspender mensaje de solicitud en caso de error" no deben establecerse ambas como False, ya que el mensaje podría perderse.</span><span class="sxs-lookup"><span data-stu-id="6190c-115">The transactions option "Transactional" and the error handling option "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="6190c-116">Establezca una o ambas opciones como true.</span><span class="sxs-lookup"><span data-stu-id="6190c-116">Please set one or both options to true.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6190c-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="6190c-117">Explanation</span></span>  
 <span data-ttu-id="6190c-118">En el adaptador de WCF-NetMsmq, las opciones de **transaccional** y **suspender el mensaje de solicitud en caso de error** deben no establecerse ambas como false (desactivada).</span><span class="sxs-lookup"><span data-stu-id="6190c-118">In the WCF-NetMsmq adapter, the options **Transactional** and **Suspend request message on failure** should not both be set to false (unchecked).</span></span> <span data-ttu-id="6190c-119">Se puede perder el mensaje si el envío de mensaje con el error no se deshace como una transacción, mientras el mensaje no está suspendido y almacenado en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="6190c-119">Message loss may occur if the failed message submission does not roll back as a transaction, while the message is not suspended and stored in the Message Box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6190c-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6190c-120">User Action</span></span>  
 <span data-ttu-id="6190c-121">Use el procedimiento siguiente para comprobar la configuración del adaptador.</span><span class="sxs-lookup"><span data-stu-id="6190c-121">Use the following procedure to verify adapter settings.</span></span>  
  
#### <a name="to-verify-adapter-settings"></a><span data-ttu-id="6190c-122">Para comprobar la configuración del adaptador</span><span class="sxs-lookup"><span data-stu-id="6190c-122">To verify adapter settings</span></span>  
  
1.  <span data-ttu-id="6190c-123">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="6190c-123">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6190c-124">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6190c-124">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="6190c-125">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="6190c-125">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="6190c-126">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="6190c-126">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="6190c-127">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6190c-127">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="6190c-128">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="6190c-128">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="6190c-129">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="6190c-129">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="6190c-130">En el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="6190c-130">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="6190c-131">En el **transacciones** sección, determine si **transaccional** está activada.</span><span class="sxs-lookup"><span data-stu-id="6190c-131">In the **Transactions** section, determine if **Transactional** is checked.</span></span>  
  
10. <span data-ttu-id="6190c-132">Haga clic en el **mensajes** ficha.</span><span class="sxs-lookup"><span data-stu-id="6190c-132">Click the **Messages** tab.</span></span>  
  
11. <span data-ttu-id="6190c-133">Determinar si **suspender el mensaje de solicitud en caso de error** está activada.</span><span class="sxs-lookup"><span data-stu-id="6190c-133">Determine if **Suspend request message on failure** is checked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6190c-134">Estos pasos únicamente se aplican a ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="6190c-134">These steps only apply to receive locations.</span></span>