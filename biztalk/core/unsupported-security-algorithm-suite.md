---
title: Conjunto de algoritmos de seguridad no admitida | Documentos de Microsoft
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
ms.openlocfilehash: 43cce7cd315c3bdfa3835014c2cf1f6a8c7077f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286908"
---
# <a name="unsupported-security-algorithm-suite"></a><span data-ttu-id="a6af4-102">Conjunto de algoritmos de seguridad no compatible</span><span class="sxs-lookup"><span data-stu-id="a6af4-102">Unsupported security algorithm suite</span></span>
## <a name="details"></a><span data-ttu-id="a6af4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a6af4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6af4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a6af4-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a6af4-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a6af4-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="a6af4-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a6af4-106">Event ID</span></span>|<span data-ttu-id="a6af4-107">0</span><span class="sxs-lookup"><span data-stu-id="a6af4-107">0</span></span>|  
|<span data-ttu-id="a6af4-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a6af4-108">Event Source</span></span>|<span data-ttu-id="a6af4-109">0</span><span class="sxs-lookup"><span data-stu-id="a6af4-109">0</span></span>|  
|<span data-ttu-id="a6af4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a6af4-110">Component</span></span>|<span data-ttu-id="a6af4-111">0</span><span class="sxs-lookup"><span data-stu-id="a6af4-111">0</span></span>|  
|<span data-ttu-id="a6af4-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a6af4-112">Symbolic Name</span></span>|<span data-ttu-id="a6af4-113">0</span><span class="sxs-lookup"><span data-stu-id="a6af4-113">0</span></span>|  
|<span data-ttu-id="a6af4-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a6af4-114">Message Text</span></span>|<span data-ttu-id="a6af4-115">Conjunto de algoritmos de seguridad no compatible: {0}</span><span class="sxs-lookup"><span data-stu-id="a6af4-115">Unsupported security algorithm suite: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a6af4-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a6af4-116">Explanation</span></span>  
 <span data-ttu-id="a6af4-117">Este error se produce cuando la propiedad del conjunto de algoritmos de seguridad de una ubicación de recepción o un puerto de envío se establece en un valor incorrecto.</span><span class="sxs-lookup"><span data-stu-id="a6af4-117">This error occurs when the security algorithm suite property of a receive location or send port is set to an incorrect value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6af4-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a6af4-118">User Action</span></span>  
 <span data-ttu-id="a6af4-119">Asegúrese de que la propiedad de protocolo de transacción está establecida en un valor válido.</span><span class="sxs-lookup"><span data-stu-id="a6af4-119">Ensure that transaction protocol property is set to a valid value.</span></span>  
  
1.  <span data-ttu-id="a6af4-120">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a6af4-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a6af4-121">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a6af4-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="a6af4-122">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="a6af4-122">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="a6af4-123">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="a6af4-123">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="a6af4-124">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a6af4-124">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="a6af4-125">En el puerto **tipo** lista, seleccione **WCF-NetTcp**.</span><span class="sxs-lookup"><span data-stu-id="a6af4-125">In the port **Type** list, select **WCF-NetTcp**.</span></span>  
  
7.  <span data-ttu-id="a6af4-126">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="a6af4-126">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="a6af4-127">En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, haga clic en el **seguridad** ficha.</span><span class="sxs-lookup"><span data-stu-id="a6af4-127">In the **WCF-NetTcp Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="a6af4-128">En el **seguridad de mensaje** sección, asegúrese de que los valores de **algorithmsuite** son correctos.</span><span class="sxs-lookup"><span data-stu-id="a6af4-128">In the **Message security** section, ensure that the values for **Algorithm suite** are correct.</span></span>