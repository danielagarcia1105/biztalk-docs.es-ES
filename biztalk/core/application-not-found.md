---
title: No se encontró la aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c37680b2-b38a-40f3-bb27-7b7281299ec3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98499420c773328d647a9c7fa1c80e3ab09ba1b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003461"
---
# <a name="application-not-found"></a><span data-ttu-id="8944f-102">No se ha encontrado la aplicación</span><span class="sxs-lookup"><span data-stu-id="8944f-102">Application not found</span></span>
## <a name="details"></a><span data-ttu-id="8944f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8944f-103">Details</span></span>  

|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8944f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8944f-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| <span data-ttu-id="8944f-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8944f-105">Product Version</span></span> |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    <span data-ttu-id="8944f-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8944f-106">Event ID</span></span>     |                                                    <span data-ttu-id="8944f-107">0</span><span class="sxs-lookup"><span data-stu-id="8944f-107">0</span></span>                                                    |
|  <span data-ttu-id="8944f-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8944f-108">Event Source</span></span>   |                                                    <span data-ttu-id="8944f-109">0</span><span class="sxs-lookup"><span data-stu-id="8944f-109">0</span></span>                                                    |
|    <span data-ttu-id="8944f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8944f-110">Component</span></span>    |                                                    <span data-ttu-id="8944f-111">0</span><span class="sxs-lookup"><span data-stu-id="8944f-111">0</span></span>                                                    |
|  <span data-ttu-id="8944f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8944f-112">Symbolic Name</span></span>  |                                                    <span data-ttu-id="8944f-113">0</span><span class="sxs-lookup"><span data-stu-id="8944f-113">0</span></span>                                                    |
|  <span data-ttu-id="8944f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8944f-114">Message Text</span></span>   | <span data-ttu-id="8944f-115">Aplicación "{0}" no se encuentra. Compruebe que la aplicación existe en la base de datos de configuración de BizTalk predeterminado</span><span class="sxs-lookup"><span data-stu-id="8944f-115">Application "{0}" not found.Verify the application exists in the default BizTalk configuration database</span></span> |

## <a name="explanation"></a><span data-ttu-id="8944f-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="8944f-116">Explanation</span></span>  
 <span data-ttu-id="8944f-117">Este error indica que BizTalk usa una aplicación que no existe en las bases de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8944f-117">This error indicates BizTalk is using an application that does not exist in the BizTalk databases.</span></span>  

## <a name="user-action"></a><span data-ttu-id="8944f-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8944f-118">User Action</span></span>  
 <span data-ttu-id="8944f-119">Use el procedimiento siguiente para configurar una aplicación válida.</span><span class="sxs-lookup"><span data-stu-id="8944f-119">Use the following procedure to configure a valid application.</span></span>  

#### <a name="to-configure-a-valid-application"></a><span data-ttu-id="8944f-120">Para configurar una aplicación válida</span><span class="sxs-lookup"><span data-stu-id="8944f-120">To configure a valid application</span></span>  

1. <span data-ttu-id="8944f-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="8944f-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="8944f-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="8944f-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  

3. <span data-ttu-id="8944f-123">Asegúrese de que la aplicación exista allí.</span><span class="sxs-lookup"><span data-stu-id="8944f-123">Ensure that the application exists there.</span></span> <span data-ttu-id="8944f-124">Si no existe, seleccione una aplicación válida diferente.</span><span class="sxs-lookup"><span data-stu-id="8944f-124">If not, select a different valid application.</span></span>
