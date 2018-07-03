---
title: Esquema de dirección no válida | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b059289-654e-40d6-a092-2a685e6e10f7
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c9a0e7a9c200d2efc7d0e6e81158379200d55af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981005"
---
# <a name="invalid-address-scheme"></a><span data-ttu-id="ba320-102">Esquema de dirección no válido</span><span class="sxs-lookup"><span data-stu-id="ba320-102">Invalid address scheme</span></span>
## <a name="details"></a><span data-ttu-id="ba320-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ba320-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="ba320-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ba320-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="ba320-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ba320-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="ba320-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ba320-106">Event ID</span></span>     |                                        <span data-ttu-id="ba320-107">000</span><span class="sxs-lookup"><span data-stu-id="ba320-107">000</span></span>                                         |
|  <span data-ttu-id="ba320-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ba320-108">Event Source</span></span>   |                                         <span data-ttu-id="ba320-109">0</span><span class="sxs-lookup"><span data-stu-id="ba320-109">0</span></span>                                          |
|    <span data-ttu-id="ba320-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ba320-110">Component</span></span>    |                                         <span data-ttu-id="ba320-111">0</span><span class="sxs-lookup"><span data-stu-id="ba320-111">0</span></span>                                          |
|  <span data-ttu-id="ba320-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ba320-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="ba320-113">0</span><span class="sxs-lookup"><span data-stu-id="ba320-113">0</span></span>                                          |
|  <span data-ttu-id="ba320-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ba320-114">Message Text</span></span>   |                  <span data-ttu-id="ba320-115">Esquema de dirección no válida. se esperaba "{0}" esquema.</span><span class="sxs-lookup"><span data-stu-id="ba320-115">Invalid address scheme; expecting "{0}" scheme.</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="ba320-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ba320-116">Explanation</span></span>  
 <span data-ttu-id="ba320-117">Ha proporcionado un esquema de protocolo que no coincide con el tipo definido por el enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="ba320-117">You provided a protocol scheme that does not match the type defined by your transport binding.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ba320-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ba320-118">User Action</span></span>  
 <span data-ttu-id="ba320-119">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba320-119">To resolve this error, do the following:</span></span>  
  
1. <span data-ttu-id="ba320-120">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="ba320-120">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="ba320-121">En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="ba320-121">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="ba320-122">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="ba320-122">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="ba320-123">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="ba320-123">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="ba320-124">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ba320-124">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="ba320-125">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="ba320-125">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="ba320-126">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ba320-126">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="ba320-127">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="ba320-127">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="ba320-128">En el **dirección (URI)** texto, asegúrese de que el valor de dirección coincide con el tipo del adaptador WCF que se está usando.</span><span class="sxs-lookup"><span data-stu-id="ba320-128">In the **Address (URI)** text box, ensure that address value matches the type of the WCF adapter that is being used.</span></span>  
  
   <span data-ttu-id="ba320-129">Además, si usa el adaptador WCF-Custom con un tipo de enlace proporcionado por el sistema, compruebe el valor de la **tipo de enlace** lista el **enlace** ficha. Si el **tipo de enlace** está configurado para **customBinding**, la dirección debe coincidir con el elemento de enlace de transporte que aparecen en la **tipo de enlace** lista en el **Enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="ba320-129">Also, if you use the WCF-Custom adapter with a system-provided binding type, check the value of the **Binding Type** list on the **Binding** tab. If the **Binding Type** is configured to **customBinding**, the address should match the transport binding element listed in the **Binding Type** list on the **Binding** tab.</span></span>