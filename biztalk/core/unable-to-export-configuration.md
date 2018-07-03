---
title: No se puede exportar la configuración | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64f09af4-00a0-47cb-889e-d9aeb7266eb2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bb3eb733dcf7c7199282ad4e5512e8d590e8c41
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018786"
---
# <a name="unable-to-export-configuration"></a><span data-ttu-id="2ac3a-102">No se puede exportar la configuración</span><span class="sxs-lookup"><span data-stu-id="2ac3a-102">Unable to export configuration</span></span>
## <a name="details"></a><span data-ttu-id="2ac3a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2ac3a-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="2ac3a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2ac3a-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="2ac3a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2ac3a-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="2ac3a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2ac3a-106">Event ID</span></span>     |                                         <span data-ttu-id="2ac3a-107">0</span><span class="sxs-lookup"><span data-stu-id="2ac3a-107">0</span></span>                                          |
|  <span data-ttu-id="2ac3a-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2ac3a-108">Event Source</span></span>   |                                         <span data-ttu-id="2ac3a-109">0</span><span class="sxs-lookup"><span data-stu-id="2ac3a-109">0</span></span>                                          |
|    <span data-ttu-id="2ac3a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2ac3a-110">Component</span></span>    |                                         <span data-ttu-id="2ac3a-111">0</span><span class="sxs-lookup"><span data-stu-id="2ac3a-111">0</span></span>                                          |
|  <span data-ttu-id="2ac3a-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2ac3a-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="2ac3a-113">0</span><span class="sxs-lookup"><span data-stu-id="2ac3a-113">0</span></span>                                          |
|  <span data-ttu-id="2ac3a-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2ac3a-114">Message Text</span></span>   |                    <span data-ttu-id="2ac3a-115">No se puede exportar la configuración al archivo "{0}"</span><span class="sxs-lookup"><span data-stu-id="2ac3a-115">Unable to export configuration to file "{0}"</span></span>                    |

## <a name="explanation"></a><span data-ttu-id="2ac3a-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="2ac3a-116">Explanation</span></span>  
 <span data-ttu-id="2ac3a-117">Algunas de las propiedades necesarias no se especificaron correctamente, tal como Dirección (URI) o Tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-117">Some required properties were not correctly specified, such as Address (URI) and Binding Type.</span></span>  

## <a name="user-action"></a><span data-ttu-id="2ac3a-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2ac3a-118">User Action</span></span>  
 <span data-ttu-id="2ac3a-119">Use el procedimiento siguiente para comprobar que las propiedades sean correctas.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-119">Use the following procedure to verify properties are correct.</span></span>  

#### <a name="to-verify-properties"></a><span data-ttu-id="2ac3a-120">Para comprobar las propiedades</span><span class="sxs-lookup"><span data-stu-id="2ac3a-120">To verify properties</span></span>  

1. <span data-ttu-id="2ac3a-121">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="2ac3a-122">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="2ac3a-123">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="2ac3a-124">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="2ac3a-125">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="2ac3a-126">En el puerto **tipo** lista, seleccione el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="2ac3a-127">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="2ac3a-128">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **Import/Export** ficha.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Import/Export** tab.</span></span>  

9. <span data-ttu-id="2ac3a-129">Haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-129">Click **Export**.</span></span>  

10. <span data-ttu-id="2ac3a-130">Asegúrese de que las propiedades necesarias se han especificado correctamente.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-130">Ensure the required properties have been correctly specified.</span></span> <span data-ttu-id="2ac3a-131">El esquema de la Dirección (URI) debe coincidir correctamente con el tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="2ac3a-131">The scheme of the Address (URI) must correctly match the Binding type.</span></span>
