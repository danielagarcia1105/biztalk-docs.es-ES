---
title: No se puede encontrar ninguna coincidencia para la expresión de ruta de acceso del cuerpo de entrada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0382348-96c4-414c-9dda-a390d491dee8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69ae115eef4440490fd4fc5ed4f40c5600b6cdb2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016977"
---
# <a name="unable-to-find-match-for-inbound-body-path-expression"></a><span data-ttu-id="ac372-102">No se puede encontrar ninguna coincidencia para la expresión de ruta del cuerpo de entrada</span><span class="sxs-lookup"><span data-stu-id="ac372-102">Unable to find match for inbound body path expression</span></span>
## <a name="details"></a><span data-ttu-id="ac372-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ac372-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="ac372-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ac372-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="ac372-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ac372-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="ac372-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ac372-106">Event ID</span></span>     |                                         <span data-ttu-id="ac372-107">0</span><span class="sxs-lookup"><span data-stu-id="ac372-107">0</span></span>                                          |
|  <span data-ttu-id="ac372-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ac372-108">Event Source</span></span>   |                                         <span data-ttu-id="ac372-109">0</span><span class="sxs-lookup"><span data-stu-id="ac372-109">0</span></span>                                          |
|    <span data-ttu-id="ac372-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ac372-110">Component</span></span>    |                                         <span data-ttu-id="ac372-111">0</span><span class="sxs-lookup"><span data-stu-id="ac372-111">0</span></span>                                          |
|  <span data-ttu-id="ac372-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ac372-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="ac372-113">0</span><span class="sxs-lookup"><span data-stu-id="ac372-113">0</span></span>                                          |
|  <span data-ttu-id="ac372-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ac372-114">Message Text</span></span>   |       <span data-ttu-id="ac372-115">No se puede encontrar ninguna coincidencia para la expresión de ruta de acceso del cuerpo de entrada "{0}" en el mensaje</span><span class="sxs-lookup"><span data-stu-id="ac372-115">Unable to find match for inbound body path expression "{0}" in message</span></span>       |

## <a name="explanation"></a><span data-ttu-id="ac372-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ac372-116">Explanation</span></span>  
 <span data-ttu-id="ac372-117">La expresión de ruta del cuerpo del mensaje entrante no devolvió ninguna coincidencia.</span><span class="sxs-lookup"><span data-stu-id="ac372-117">The body path expression executed on the incoming message did not return any match.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ac372-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ac372-118">User Action</span></span>  
 <span data-ttu-id="ac372-119">Asegúrese de que la expresión de ruta de cuerpo sea correcta y que el mensaje entrante tenga los datos correctos.</span><span class="sxs-lookup"><span data-stu-id="ac372-119">Make sure that body path expression is correct, and the incoming message has the correct data.</span></span>  

1. <span data-ttu-id="ac372-120">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="ac372-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="ac372-121">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="ac372-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="ac372-122">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="ac372-122">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="ac372-123">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="ac372-123">Right-click the transport name.</span></span>  

5. <span data-ttu-id="ac372-124">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ac372-124">Click **Properties**.</span></span>  

6. <span data-ttu-id="ac372-125">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="ac372-125">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="ac372-126">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ac372-126">Click **Configure**.</span></span>  

8. <span data-ttu-id="ac372-127">En WCF **[**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **mensajes** ficha.</span><span class="sxs-lookup"><span data-stu-id="ac372-127">In the WCF **[**<em>transport type</em>**] Transport Properties** dialog box, click the **Messages** tab.</span></span>  

9. <span data-ttu-id="ac372-128">En el **cuerpo del mensaje entrante de BizTalk** sección, compruebe la información de **expresión de ruta de cuerpo**.</span><span class="sxs-lookup"><span data-stu-id="ac372-128">In the **Inbound BizTalk message body** section, check the information for **Body path expression**.</span></span>
