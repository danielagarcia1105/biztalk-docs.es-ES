---
title: No se pudieron obtener los nombres de servidor o la base de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0590f43b-0aec-491f-bca5-c50ab12552a5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16c694acdc78b704eb6f2578df99239442fd897e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237852"
---
# <a name="could-not-get-the-database-or-the-server-names"></a><span data-ttu-id="2056a-102">No se han podido obtener los nombres de base de datos o servidor.</span><span class="sxs-lookup"><span data-stu-id="2056a-102">Could not get the database or the server names</span></span>
## <a name="details"></a><span data-ttu-id="2056a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2056a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2056a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2056a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2056a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2056a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2056a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2056a-106">Event ID</span></span>|-|  
|<span data-ttu-id="2056a-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2056a-107">Event Source</span></span>|<span data-ttu-id="2056a-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2056a-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="2056a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="2056a-109">Component</span></span>|<span data-ttu-id="2056a-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="2056a-110">EDI Engine</span></span>|  
|<span data-ttu-id="2056a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2056a-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="2056a-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2056a-112">Message Text</span></span>|<span data-ttu-id="2056a-113">No se han podido obtener los nombres de base de datos o servidor.</span><span class="sxs-lookup"><span data-stu-id="2056a-113">Could not get the database or the server names</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2056a-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="2056a-114">Explanation</span></span>  
 <span data-ttu-id="2056a-115">Este error indica que BizTalk no pudo leer el nombre de BizTalkMgmtDb ni el nombre del servidor desde el Registro.</span><span class="sxs-lookup"><span data-stu-id="2056a-115">This error indicates BizTalk could not read the BizTalkMgmtDb name and Server name from registry.</span></span> <span data-ttu-id="2056a-116">Una posible razón para este error es que el grupo de BizTalk no esté configurado.</span><span class="sxs-lookup"><span data-stu-id="2056a-116">One possible reason for this error is the BizTalk Group is not configured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2056a-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2056a-117">User Action</span></span>  
 <span data-ttu-id="2056a-118">Para resolver este error, configure el Grupo de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="2056a-118">To resolve this error, configure the BizTalk Group:</span></span>  
  
1.  <span data-ttu-id="2056a-119">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2056a-119">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2056a-120">En la Raíz de la consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2056a-120">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
3.  <span data-ttu-id="2056a-121">Haga clic en **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="2056a-121">Right-click **BizTalk Group**.</span></span>  
  
4.  <span data-ttu-id="2056a-122">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2056a-122">Click **Properties**.</span></span>  
  
5.  <span data-ttu-id="2056a-123">En el panel izquierdo, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="2056a-123">In the left pane, click **General**.</span></span>  
  
6.  <span data-ttu-id="2056a-124">Compruebe el **Server** nombre y **base de datos** el nombre son correctos.</span><span class="sxs-lookup"><span data-stu-id="2056a-124">Verify the **Server** name and **Database** name are correct.</span></span>