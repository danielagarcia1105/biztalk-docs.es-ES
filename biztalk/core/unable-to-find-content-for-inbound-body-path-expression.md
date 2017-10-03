---
title: "No se puede encontrar contenido para la expresión de ruta de acceso de entrada cuerpo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed294662-a94e-4fbb-b125-878a27107eab
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 879b846900441cfced9e4a875d7c2ad74310e701
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-find-content-for-inbound-body-path-expression"></a><span data-ttu-id="e4742-102">No se encuentra el contenido para la expresión de ruta del cuerpo de entrada</span><span class="sxs-lookup"><span data-stu-id="e4742-102">Unable to find content for inbound body path expression</span></span>
## <a name="details"></a><span data-ttu-id="e4742-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e4742-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e4742-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e4742-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e4742-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e4742-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="e4742-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e4742-106">Event ID</span></span>|<span data-ttu-id="e4742-107">0</span><span class="sxs-lookup"><span data-stu-id="e4742-107">0</span></span>|  
|<span data-ttu-id="e4742-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e4742-108">Event Source</span></span>|<span data-ttu-id="e4742-109">0</span><span class="sxs-lookup"><span data-stu-id="e4742-109">0</span></span>|  
|<span data-ttu-id="e4742-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e4742-110">Component</span></span>|<span data-ttu-id="e4742-111">0</span><span class="sxs-lookup"><span data-stu-id="e4742-111">0</span></span>|  
|<span data-ttu-id="e4742-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e4742-112">Symbolic Name</span></span>|<span data-ttu-id="e4742-113">0</span><span class="sxs-lookup"><span data-stu-id="e4742-113">0</span></span>|  
|<span data-ttu-id="e4742-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e4742-114">Message Text</span></span>|<span data-ttu-id="e4742-115">No se puede encontrar contenido para la expresión de ruta del cuerpo de entrada "{0}" en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4742-115">Unable to find content for inbound body path expression "{0}" in message</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e4742-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="e4742-116">Explanation</span></span>  
 <span data-ttu-id="e4742-117">El contenido extraído del mensaje de entrada mediante la ejecución de la expresión de ruta del cuerpo no contiene ningún dato.</span><span class="sxs-lookup"><span data-stu-id="e4742-117">The content extracted from the incoming message by executing the body path expression does not contain any data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e4742-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e4742-118">User Action</span></span>  
 <span data-ttu-id="e4742-119">Asegúrese de que la expresión de ruta de cuerpo sea correcta y que el mensaje entrante tenga los datos correctos.</span><span class="sxs-lookup"><span data-stu-id="e4742-119">Make sure that body path expression is correct, and the incoming message has the correct data.</span></span>  
  
1.  <span data-ttu-id="e4742-120">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="e4742-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e4742-121">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="e4742-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="e4742-122">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="e4742-122">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="e4742-123">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="e4742-123">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="e4742-124">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e4742-124">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="e4742-125">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="e4742-125">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="e4742-126">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="e4742-126">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="e4742-127">En WCF **[***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **mensajes** ficha.</span><span class="sxs-lookup"><span data-stu-id="e4742-127">In the WCF **[***transport type***] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="e4742-128">En el **cuerpo del mensaje entrante de BizTalk** sección, compruebe la información de **cuerpo de la expresión de ruta de acceso**.</span><span class="sxs-lookup"><span data-stu-id="e4742-128">In the **Inbound BizTalk message body** section, check the information for **Body path expression**.</span></span>