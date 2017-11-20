---
title: "Dirección no válida (uri absoluto) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5db292ad-9105-492d-a6c5-a7108159901a
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af2cb19c793bdcd7ab4a1dc18eb0ea1c98a991ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-absolute-uri"></a><span data-ttu-id="fa3ce-102">Dirección no válida (uri absoluto)</span><span class="sxs-lookup"><span data-stu-id="fa3ce-102">Invalid address (absolute uri)</span></span>
## <a name="details"></a><span data-ttu-id="fa3ce-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa3ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa3ce-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fa3ce-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="fa3ce-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fa3ce-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="fa3ce-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fa3ce-106">Event ID</span></span>|<span data-ttu-id="fa3ce-107">0</span><span class="sxs-lookup"><span data-stu-id="fa3ce-107">0</span></span>|  
|<span data-ttu-id="fa3ce-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fa3ce-108">Event Source</span></span>|<span data-ttu-id="fa3ce-109">0</span><span class="sxs-lookup"><span data-stu-id="fa3ce-109">0</span></span>|  
|<span data-ttu-id="fa3ce-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fa3ce-110">Component</span></span>|<span data-ttu-id="fa3ce-111">0</span><span class="sxs-lookup"><span data-stu-id="fa3ce-111">0</span></span>|  
|<span data-ttu-id="fa3ce-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fa3ce-112">Symbolic Name</span></span>|<span data-ttu-id="fa3ce-113">0</span><span class="sxs-lookup"><span data-stu-id="fa3ce-113">0</span></span>|  
|<span data-ttu-id="fa3ce-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fa3ce-114">Message Text</span></span>|<span data-ttu-id="fa3ce-115">Dirección no válida; "{0}" no es un uri absoluto bien formado.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-115">Invalid address; "{0}" is not a well-formed absolute uri</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fa3ce-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="fa3ce-116">Explanation</span></span>  
 <span data-ttu-id="fa3ce-117">Este evento de error indica que no proporcionó un transporte WCF en curso con una dirección absoluta bien formada.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-117">This error event indicates that you did not provide an in-process WCF transport with a well-formed absolute address.</span></span> <span data-ttu-id="fa3ce-118">Por ejemplo, no puede establecer la propiedad Dirección del transporte WCF en curso en una dirección relativa, tal como /path/service.svc.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-118">For example, you cannot set the Address property of the in-process WCF transport to a relative address, such as /path/service.svc.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa3ce-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fa3ce-119">User Action</span></span>  
 <span data-ttu-id="fa3ce-120">Cambie la dirección del transporte WCF en curso por una dirección absoluta bien formada.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-120">Change the address of the in-process WCF transport to a well-formed absolute address.</span></span>  
  
1.  <span data-ttu-id="fa3ce-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-121">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="fa3ce-122">En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-122">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="fa3ce-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="fa3ce-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="fa3ce-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="fa3ce-126">En el puerto **tipo** , seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="fa3ce-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="fa3ce-128">En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="fa3ce-129">En el **dirección (URI)** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-129">In the **Address (URI)** text box.</span></span> <span data-ttu-id="fa3ce-130">Cambie la dirección.</span><span class="sxs-lookup"><span data-stu-id="fa3ce-130">change the address.</span></span> <span data-ttu-id="fa3ce-131">Un ejemplo de una dirección absoluta bien formada es http://localhost/path/service.svc</span><span class="sxs-lookup"><span data-stu-id="fa3ce-131">An example of a well-formed absolute address is http://localhost/path/service.svc</span></span>