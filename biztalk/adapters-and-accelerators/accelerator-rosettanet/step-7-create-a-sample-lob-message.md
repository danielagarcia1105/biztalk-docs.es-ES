---
title: 'Paso 7: Crear un mensaje de LOB de ejemplo | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, LOB
- loopback tutorial, creating LOB message
- creating, LOB messages
- LOBs, creating messages
ms.assetid: 3023bbc0-5bc4-4e5a-a345-c3253874f0d3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acc6b57a78d51d9c132115f387296c48c2e924c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-create-a-sample-lob-message"></a><span data-ttu-id="9333f-102">Paso 7: Crear un mensaje de LOB de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9333f-102">Step 7: Create a Sample LOB Message</span></span>
<span data-ttu-id="9333f-103">En este paso, se utiliza la utilidad de la aplicación de LOB para crear un mensaje de la línea de negocio (LOB) de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9333f-103">In this step, you use the LOB Application utility to create a sample line-of-business (LOB) message.</span></span>  
  
### <a name="to-create-a-sample-message-using-the-lob-application-utility"></a><span data-ttu-id="9333f-104">Para crear un mensaje de ejemplo mediante la utilidad de la aplicación de LOB</span><span class="sxs-lookup"><span data-stu-id="9333f-104">To create a sample message using the LOB Application utility</span></span>  
  
1.  <span data-ttu-id="9333f-105">En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a \< *unidad*>: \Program BizTalk \<versión > Accelerator for RosettaNet\SDK carpeta y, a continuación, haga doble clic en  **LOBApplication.exe**.</span><span class="sxs-lookup"><span data-stu-id="9333f-105">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to \<*drive*>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK folder, and then double-click **LOBApplication.exe**.</span></span>  
  
2.  <span data-ttu-id="9333f-106">En el **aplicación LOB** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9333f-106">In the **LOB Application** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="9333f-107">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="9333f-107">**Use this**</span></span>|<span data-ttu-id="9333f-108">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="9333f-108">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="9333f-109">**Nombre del perfil de inicio**</span><span class="sxs-lookup"><span data-stu-id="9333f-109">**Home Profile Name**</span></span>|<span data-ttu-id="9333f-110">Tipo de **inicio**.</span><span class="sxs-lookup"><span data-stu-id="9333f-110">Type **HOME**.</span></span>|  
    |<span data-ttu-id="9333f-111">**Nombre del socio comercial**</span><span class="sxs-lookup"><span data-stu-id="9333f-111">**Trading Partner Name**</span></span>|<span data-ttu-id="9333f-112">Tipo de **asociado**.</span><span class="sxs-lookup"><span data-stu-id="9333f-112">Type **PARTNER**.</span></span>|  
    |<span data-ttu-id="9333f-113">**Nombre del PIP**</span><span class="sxs-lookup"><span data-stu-id="9333f-113">**PIP Name**</span></span>|<span data-ttu-id="9333f-114">Tipo de **0c1**.</span><span class="sxs-lookup"><span data-stu-id="9333f-114">Type **0C1**.</span></span>|  
    |<span data-ttu-id="9333f-115">**Versión PIP**</span><span class="sxs-lookup"><span data-stu-id="9333f-115">**PIP Version**</span></span>|<span data-ttu-id="9333f-116">Escriba **R01.02**.</span><span class="sxs-lookup"><span data-stu-id="9333f-116">Type **R01.02**.</span></span>|  
    |<span data-ttu-id="9333f-117">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="9333f-117">**File Name**</span></span>|<span data-ttu-id="9333f-118">Haga clic en el botón de puntos suspensivos (**...** ) y mover a \< *unidad*: > \Program BizTalk \<versión > Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances.</span><span class="sxs-lookup"><span data-stu-id="9333f-118">Click the ellipsis button (**...**), and move to \<*drive*:>\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances.</span></span> <span data-ttu-id="9333f-119">Seleccione **0C1_Request.xml** en la lista de archivos y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9333f-119">Select **0C1_Request.xml** from the list of files, and then click **Open**.</span></span>|  
    |<span data-ttu-id="9333f-120">**Categoría de mensaje**</span><span class="sxs-lookup"><span data-stu-id="9333f-120">**Message Category**</span></span>|<span data-ttu-id="9333f-121">Seleccione **acción** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9333f-121">Select **Action** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="9333f-122">En el **aplicación LOB** cuadro de diálogo, haga clic en **enviar mensaje**.</span><span class="sxs-lookup"><span data-stu-id="9333f-122">In the **LOB Application** dialog box, click **Submit Message**.</span></span>  
  
 <span data-ttu-id="9333f-123">La aplicación de LOB genera un mensaje de Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] simulando un mensaje original generado por una aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="9333f-123">The LOB application generates a message for Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] simulating an original message generated by an LOB application.</span></span> <span data-ttu-id="9333f-124">Puede ver el estado del mensaje en la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="9333f-124">You can view the status of the message in the Status window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9333f-125">Los mensajes de ejemplo se supone que los identificadores de empresarial Global (GBI) para "Hogar" y "Asociado" son 123456789 y 987654321, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9333f-125">The sample messages assume that the Global Business Identifiers (GBI) for "HOME" and "PARTNER" are 123456789 and 987654321, respectively.</span></span> <span data-ttu-id="9333f-126">Para usar un GBI diferente, debe modificar el contenido de estos archivos.</span><span class="sxs-lookup"><span data-stu-id="9333f-126">To use a different GBI, you must modify the content of these files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9333f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9333f-127">See Also</span></span>  
 [<span data-ttu-id="9333f-128">Paso 8: Ver los mensajes en las bases de datos BTARN</span><span class="sxs-lookup"><span data-stu-id="9333f-128">Step 8: View Messages in the BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)