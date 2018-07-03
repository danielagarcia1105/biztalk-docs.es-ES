---
title: Dirección no válida (uri absoluto) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5db292ad-9105-492d-a6c5-a7108159901a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 933897545d47e2a68c1911474a3549931edd4512
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001253"
---
# <a name="invalid-address-absolute-uri"></a><span data-ttu-id="5b725-102">Dirección no válida (uri absoluto)</span><span class="sxs-lookup"><span data-stu-id="5b725-102">Invalid address (absolute uri)</span></span>
## <a name="details"></a><span data-ttu-id="5b725-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5b725-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="5b725-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5b725-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="5b725-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5b725-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="5b725-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5b725-106">Event ID</span></span>     |                                         <span data-ttu-id="5b725-107">0</span><span class="sxs-lookup"><span data-stu-id="5b725-107">0</span></span>                                          |
|  <span data-ttu-id="5b725-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5b725-108">Event Source</span></span>   |                                         <span data-ttu-id="5b725-109">0</span><span class="sxs-lookup"><span data-stu-id="5b725-109">0</span></span>                                          |
|    <span data-ttu-id="5b725-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5b725-110">Component</span></span>    |                                         <span data-ttu-id="5b725-111">0</span><span class="sxs-lookup"><span data-stu-id="5b725-111">0</span></span>                                          |
|  <span data-ttu-id="5b725-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5b725-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="5b725-113">0</span><span class="sxs-lookup"><span data-stu-id="5b725-113">0</span></span>                                          |
|  <span data-ttu-id="5b725-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5b725-114">Message Text</span></span>   |              <span data-ttu-id="5b725-115">Dirección no válida; "{0}" no es un uri absoluto bien formado</span><span class="sxs-lookup"><span data-stu-id="5b725-115">Invalid address; "{0}" is not a well-formed absolute uri</span></span>              |

## <a name="explanation"></a><span data-ttu-id="5b725-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="5b725-116">Explanation</span></span>  
 <span data-ttu-id="5b725-117">Este evento de error indica que no proporcionó un transporte WCF en curso con una dirección absoluta bien formada.</span><span class="sxs-lookup"><span data-stu-id="5b725-117">This error event indicates that you did not provide an in-process WCF transport with a well-formed absolute address.</span></span> <span data-ttu-id="5b725-118">Por ejemplo, no puede establecer la propiedad Dirección del transporte WCF en curso en una dirección relativa, tal como /path/service.svc.</span><span class="sxs-lookup"><span data-stu-id="5b725-118">For example, you cannot set the Address property of the in-process WCF transport to a relative address, such as /path/service.svc.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5b725-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5b725-119">User Action</span></span>  
 <span data-ttu-id="5b725-120">Cambie la dirección del transporte WCF en curso por una dirección absoluta bien formada.</span><span class="sxs-lookup"><span data-stu-id="5b725-120">Change the address of the in-process WCF transport to a well-formed absolute address.</span></span>  

1. <span data-ttu-id="5b725-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="5b725-121">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="5b725-122">En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="5b725-122">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="5b725-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="5b725-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="5b725-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="5b725-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="5b725-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5b725-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="5b725-126">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="5b725-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="5b725-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="5b725-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="5b725-128">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="5b725-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  

9. <span data-ttu-id="5b725-129">En el **dirección (URI)** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="5b725-129">In the **Address (URI)** text box.</span></span> <span data-ttu-id="5b725-130">Cambie la dirección.</span><span class="sxs-lookup"><span data-stu-id="5b725-130">change the address.</span></span> <span data-ttu-id="5b725-131">Un ejemplo de una dirección absoluta bien formada es http://localhost/path/service.svc</span><span class="sxs-lookup"><span data-stu-id="5b725-131">An example of a well-formed absolute address is http://localhost/path/service.svc</span></span>
