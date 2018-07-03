---
title: Longitud de dirección no válida | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8e16eb6-e77e-4361-ac91-0730004c4433
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8da5e041ad861557817491695f0d7972a207864a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008477"
---
# <a name="invalid-address-length"></a><span data-ttu-id="3cd04-102">Longitud de dirección no válida</span><span class="sxs-lookup"><span data-stu-id="3cd04-102">Invalid address length</span></span>
## <a name="details"></a><span data-ttu-id="3cd04-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3cd04-103">Details</span></span>  

|                 |                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3cd04-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3cd04-104">Product Name</span></span>   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
| <span data-ttu-id="3cd04-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3cd04-105">Product Version</span></span> |                 [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                  |
|    <span data-ttu-id="3cd04-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3cd04-106">Event ID</span></span>     |                                              <span data-ttu-id="3cd04-107">0</span><span class="sxs-lookup"><span data-stu-id="3cd04-107">0</span></span>                                              |
|  <span data-ttu-id="3cd04-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3cd04-108">Event Source</span></span>   |                                              <span data-ttu-id="3cd04-109">0</span><span class="sxs-lookup"><span data-stu-id="3cd04-109">0</span></span>                                              |
|    <span data-ttu-id="3cd04-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3cd04-110">Component</span></span>    |                                              <span data-ttu-id="3cd04-111">0</span><span class="sxs-lookup"><span data-stu-id="3cd04-111">0</span></span>                                              |
|  <span data-ttu-id="3cd04-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3cd04-112">Symbolic Name</span></span>  |                                              <span data-ttu-id="3cd04-113">0</span><span class="sxs-lookup"><span data-stu-id="3cd04-113">0</span></span>                                              |
|  <span data-ttu-id="3cd04-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3cd04-114">Message Text</span></span>   | <span data-ttu-id="3cd04-115">Longitud de dirección no válida; Especifica la longitud de la dirección es {0} límite es de caracteres, {1} caracteres adicionales.</span><span class="sxs-lookup"><span data-stu-id="3cd04-115">Invalid address length; specified address length is {0} characters, limit is {1} characters</span></span> |

## <a name="explanation"></a><span data-ttu-id="3cd04-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="3cd04-116">Explanation</span></span>  
 <span data-ttu-id="3cd04-117">Proporcionó una dirección que excede de la longitud máxima de 255 caracteres para un transporte WCF.</span><span class="sxs-lookup"><span data-stu-id="3cd04-117">You provided an address that exceeds the maximum length of 255 characters for a WCF transport.</span></span> <span data-ttu-id="3cd04-118">Este límite lo impone BizTalk Server, no WCF.</span><span class="sxs-lookup"><span data-stu-id="3cd04-118">This is a limitation imposed by BizTalk Server, not by WCF.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3cd04-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3cd04-119">User Action</span></span>  
 <span data-ttu-id="3cd04-120">Use el procedimiento siguiente para configurar una dirección válida.</span><span class="sxs-lookup"><span data-stu-id="3cd04-120">Use the following procedure to configure a valid address.</span></span>  

#### <a name="to-configure-a-valid-address"></a><span data-ttu-id="3cd04-121">Para configurar una dirección válida</span><span class="sxs-lookup"><span data-stu-id="3cd04-121">To configure a valid address</span></span>  

1. <span data-ttu-id="3cd04-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="3cd04-122">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="3cd04-123">En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="3cd04-123">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="3cd04-124">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="3cd04-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="3cd04-125">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="3cd04-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="3cd04-126">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3cd04-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="3cd04-127">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="3cd04-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="3cd04-128">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="3cd04-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="3cd04-129">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="3cd04-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  

9. <span data-ttu-id="3cd04-130">En el **dirección (URI)** texto, asegúrese de que la dirección no supera la longitud máxima de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="3cd04-130">In the **Address (URI)** text box, ensure the address does not exceed the maximum length of 255 characters.</span></span>
