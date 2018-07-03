---
title: Conjunto de algoritmos de seguridad no admitida | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11696fed-c3a8-4b11-8249-9f99f7abc8f2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32b00fea76b95a76cbb6b88f18056bba798e1381
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990989"
---
# <a name="unsupported-security-algorithm-suite"></a><span data-ttu-id="f2eaf-102">Conjunto de algoritmos de seguridad no compatible</span><span class="sxs-lookup"><span data-stu-id="f2eaf-102">Unsupported security algorithm suite</span></span>
## <a name="details"></a><span data-ttu-id="f2eaf-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f2eaf-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="f2eaf-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f2eaf-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="f2eaf-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f2eaf-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="f2eaf-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f2eaf-106">Event ID</span></span>     |                                         <span data-ttu-id="f2eaf-107">0</span><span class="sxs-lookup"><span data-stu-id="f2eaf-107">0</span></span>                                          |
|  <span data-ttu-id="f2eaf-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f2eaf-108">Event Source</span></span>   |                                         <span data-ttu-id="f2eaf-109">0</span><span class="sxs-lookup"><span data-stu-id="f2eaf-109">0</span></span>                                          |
|    <span data-ttu-id="f2eaf-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f2eaf-110">Component</span></span>    |                                         <span data-ttu-id="f2eaf-111">0</span><span class="sxs-lookup"><span data-stu-id="f2eaf-111">0</span></span>                                          |
|  <span data-ttu-id="f2eaf-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f2eaf-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="f2eaf-113">0</span><span class="sxs-lookup"><span data-stu-id="f2eaf-113">0</span></span>                                          |
|  <span data-ttu-id="f2eaf-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f2eaf-114">Message Text</span></span>   |                     <span data-ttu-id="f2eaf-115">Conjunto de algoritmos de seguridad no compatible: {0}</span><span class="sxs-lookup"><span data-stu-id="f2eaf-115">Unsupported security algorithm suite: {0}</span></span>                      |

## <a name="explanation"></a><span data-ttu-id="f2eaf-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="f2eaf-116">Explanation</span></span>  
 <span data-ttu-id="f2eaf-117">Este error se produce cuando la propiedad del conjunto de algoritmos de seguridad de una ubicación de recepción o un puerto de envío se establece en un valor incorrecto.</span><span class="sxs-lookup"><span data-stu-id="f2eaf-117">This error occurs when the security algorithm suite property of a receive location or send port is set to an incorrect value.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f2eaf-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f2eaf-118">User Action</span></span>  
 <span data-ttu-id="f2eaf-119">Asegúrese de que la propiedad de protocolo de transacción está establecida en un valor válido.</span><span class="sxs-lookup"><span data-stu-id="f2eaf-119">Ensure that transaction protocol property is set to a valid value.</span></span>  

1. <span data-ttu-id="f2eaf-120">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="f2eaf-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f2eaf-121">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="f2eaf-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="f2eaf-122">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="f2eaf-122">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="f2eaf-123">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="f2eaf-123">Right-click the transport name.</span></span>  

5. <span data-ttu-id="f2eaf-124">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f2eaf-124">Click **Properties**.</span></span>  

6. <span data-ttu-id="f2eaf-125">En el puerto **tipo** lista, seleccione **WCF-NetTcp**.</span><span class="sxs-lookup"><span data-stu-id="f2eaf-125">In the port **Type** list, select **WCF-NetTcp**.</span></span>  

7. <span data-ttu-id="f2eaf-126">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="f2eaf-126">Click **Configure**.</span></span>  

8. <span data-ttu-id="f2eaf-127">En el **propiedades de transporte WCF-NetTcp** cuadro de diálogo, haga clic en el **seguridad** ficha.</span><span class="sxs-lookup"><span data-stu-id="f2eaf-127">In the **WCF-NetTcp Transport Properties** dialog box, click the **Security** tab.</span></span>  

9. <span data-ttu-id="f2eaf-128">En el **la seguridad de mensaje** sección, asegúrese de que los valores de **algorithmsuite** son correctos.</span><span class="sxs-lookup"><span data-stu-id="f2eaf-128">In the **Message security** section, ensure that the values for **Algorithm suite** are correct.</span></span>
