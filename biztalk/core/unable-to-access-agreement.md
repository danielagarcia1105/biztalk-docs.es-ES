---
title: No se puede obtener acceso al acuerdo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72890ee9-54c9-48ed-8c6e-8b329d79c68b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a28b2b3587781d66e8788ca88931c7c5522bac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286540"
---
# <a name="unable-to-access-agreement"></a><span data-ttu-id="66a87-102">No se puede obtener acceso al acuerdo</span><span class="sxs-lookup"><span data-stu-id="66a87-102">Unable to access agreement</span></span>
## <a name="details"></a><span data-ttu-id="66a87-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="66a87-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66a87-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="66a87-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="66a87-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="66a87-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="66a87-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="66a87-106">Event ID</span></span>|-|  
|<span data-ttu-id="66a87-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="66a87-107">Event Source</span></span>|<span data-ttu-id="66a87-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66a87-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="66a87-109">Componente</span><span class="sxs-lookup"><span data-stu-id="66a87-109">Component</span></span>|<span data-ttu-id="66a87-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="66a87-110">EDI Engine</span></span>|  
|<span data-ttu-id="66a87-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="66a87-111">Symbolic Name</span></span>|<span data-ttu-id="66a87-112">UnableToLocateAS2PartyError</span><span class="sxs-lookup"><span data-stu-id="66a87-112">UnableToLocateAS2PartyError</span></span>|  
|<span data-ttu-id="66a87-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="66a87-113">Message Text</span></span>|<span data-ttu-id="66a87-114">No se puede obtener acceso al acuerdo.</span><span class="sxs-lookup"><span data-stu-id="66a87-114">Unable to access agreement.</span></span> <span data-ttu-id="66a87-115">AS2From: {0} AS2To: {1}.</span><span class="sxs-lookup"><span data-stu-id="66a87-115">AS2From: {0} AS2To: {1}.</span></span> <span data-ttu-id="66a87-116">Error: {2}</span><span class="sxs-lookup"><span data-stu-id="66a87-116">Error: {2}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="66a87-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="66a87-117">Explanation</span></span>  
 <span data-ttu-id="66a87-118">Este error indica que BizTalk Server no pudo encontrar una entidad para el calificador y valor dados.</span><span class="sxs-lookup"><span data-stu-id="66a87-118">This error indicates BizTalk Server could not find a party for the given qualifier and value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66a87-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="66a87-119">User Action</span></span>  
 <span data-ttu-id="66a87-120">Para resolver este error, cree un alias de entidad para el calificador dado:</span><span class="sxs-lookup"><span data-stu-id="66a87-120">To resolve this error, create a party alias for the given qualifier:</span></span>  
  
1.  <span data-ttu-id="66a87-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="66a87-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="66a87-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y haga clic en **partes**.</span><span class="sxs-lookup"><span data-stu-id="66a87-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  
  
3.  <span data-ttu-id="66a87-123">Haga clic con el botón secundario en la entidad correcta.</span><span class="sxs-lookup"><span data-stu-id="66a87-123">Right-click the correct party.</span></span>  
  
4.  <span data-ttu-id="66a87-124">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="66a87-124">Click **Properties**.</span></span>  
  
5.  <span data-ttu-id="66a87-125">En el [*nombre de la entidad*] **propiedades de la entidad** diálogo cuadro, escriba **valor From de EDIINT-AS2** en el **nombre** columna.</span><span class="sxs-lookup"><span data-stu-id="66a87-125">In the [*party name*] **Party Properties** dialog box, enter **EDIINT-AS2 From Value** in the **Name** column.</span></span>  
  
6.  <span data-ttu-id="66a87-126">Escriba el nombre de entidad en el **valor** columna.</span><span class="sxs-lookup"><span data-stu-id="66a87-126">Enter the party name in the **Value** column.</span></span>  
  
7.  <span data-ttu-id="66a87-127">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="66a87-127">Click **OK**.</span></span>