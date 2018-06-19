---
title: No se puede obtener acceso a la entidad usando el puerto de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffacba77-76e8-4f03-be26-134a9999d6c1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aa582319226b114720ef234b8e3f65e416a94d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286532"
---
# <a name="unable-to-access-party-using-send-port"></a><span data-ttu-id="3e345-102">No se pudo obtener acceso a la entidad usando el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="3e345-102">Unable to access party using send port</span></span>
## <a name="details"></a><span data-ttu-id="3e345-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3e345-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e345-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3e345-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3e345-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3e345-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3e345-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3e345-106">Event ID</span></span>|-|  
|<span data-ttu-id="3e345-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3e345-107">Event Source</span></span>|<span data-ttu-id="3e345-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e345-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="3e345-109">Componente</span><span class="sxs-lookup"><span data-stu-id="3e345-109">Component</span></span>|<span data-ttu-id="3e345-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="3e345-110">AS2 Engine</span></span>|  
|<span data-ttu-id="3e345-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3e345-111">Symbolic Name</span></span>|<span data-ttu-id="3e345-112">UnableToLocateAS2PartyBySendPortNameError</span><span class="sxs-lookup"><span data-stu-id="3e345-112">UnableToLocateAS2PartyBySendPortNameError</span></span>|  
|<span data-ttu-id="3e345-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3e345-113">Message Text</span></span>|<span data-ttu-id="3e345-114">No se puede obtener acceso a la entidad usando el puerto de envío: {0}</span><span class="sxs-lookup"><span data-stu-id="3e345-114">Unable to access party using send port: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3e345-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="3e345-115">Explanation</span></span>  
 <span data-ttu-id="3e345-116">Este error indica que la canalización de envío no encontró una entidad asociada con el puerto de envío especificado para el mensaje AS2 saliente.</span><span class="sxs-lookup"><span data-stu-id="3e345-116">This error indicates the send pipeline could not find a party associated with the specified send port for the outgoing AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3e345-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3e345-117">User Action</span></span>  
 <span data-ttu-id="3e345-118">Para resolver este error, asocie una entidad con el puerto de envío especificado:</span><span class="sxs-lookup"><span data-stu-id="3e345-118">To resolve this error, associate a party with the specified send port:</span></span>  
  
1.  <span data-ttu-id="3e345-119">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="3e345-119">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3e345-120">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y haga clic en **partes**.</span><span class="sxs-lookup"><span data-stu-id="3e345-120">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  
  
3.  <span data-ttu-id="3e345-121">Haga clic con el botón secundario en la entidad correcta.</span><span class="sxs-lookup"><span data-stu-id="3e345-121">Right-click the correct party.</span></span>  
  
4.  <span data-ttu-id="3e345-122">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3e345-122">Click **Properties**.</span></span>  
  
5.  <span data-ttu-id="3e345-123">En el [*nombre de la entidad*] **propiedades de la entidad** cuadro de diálogo, en el panel izquierdo, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="3e345-123">In the [*party name*] **Party Properties** dialog box, in the left pane, click **Send Ports**.</span></span>  
  
6.  <span data-ttu-id="3e345-124">Escriba el nombre de puerto de envío en el **puertos de envío** lista.</span><span class="sxs-lookup"><span data-stu-id="3e345-124">Enter the Send port name in the **Send Ports** list.</span></span>  
  
7.  <span data-ttu-id="3e345-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3e345-125">Click **OK**.</span></span>