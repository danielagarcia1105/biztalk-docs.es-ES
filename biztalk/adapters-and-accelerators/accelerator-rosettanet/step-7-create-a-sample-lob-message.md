---
title: 'Paso 7: Crear un mensaje de LOB de ejemplo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, LOB
- loopback tutorial, creating LOB message
- creating, LOB messages
- LOBs, creating messages
ms.assetid: 3023bbc0-5bc4-4e5a-a345-c3253874f0d3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2b8450f196a1619b55b08a0771508daafa421a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978005"
---
# <a name="step-7-create-a-sample-lob-message"></a><span data-ttu-id="76cc4-102">Paso 7: Crear un mensaje de LOB de ejemplo</span><span class="sxs-lookup"><span data-stu-id="76cc4-102">Step 7: Create a Sample LOB Message</span></span>
<span data-ttu-id="76cc4-103">En este paso, usará la utilidad de la aplicación de LOB para crear un mensaje de la línea de negocio (LOB) de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="76cc4-103">In this step, you use the LOB Application utility to create a sample line-of-business (LOB) message.</span></span>  

### <a name="to-create-a-sample-message-using-the-lob-application-utility"></a><span data-ttu-id="76cc4-104">Para crear un mensaje de ejemplo mediante la utilidad de la aplicación de LOB</span><span class="sxs-lookup"><span data-stu-id="76cc4-104">To create a sample message using the LOB Application utility</span></span>  

1. <span data-ttu-id="76cc4-105">En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, desplácese a \< *unidad*\>: \Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK carpeta y, a continuación, haga doble clic en **LOBApplication.exe**.</span><span class="sxs-lookup"><span data-stu-id="76cc4-105">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to \<*drive*\>:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK folder, and then double-click **LOBApplication.exe**.</span></span>  

2. <span data-ttu-id="76cc4-106">En el **aplicación LOB** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="76cc4-106">In the **LOB Application** dialog box, do the following:</span></span>  


   |       <span data-ttu-id="76cc4-107">**Úselo**</span><span class="sxs-lookup"><span data-stu-id="76cc4-107">**Use this**</span></span>       |                                                                                                                       <span data-ttu-id="76cc4-108">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="76cc4-108">**To do this**</span></span>                                                                                                                       |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="76cc4-109">**Nombre del perfil principal**</span><span class="sxs-lookup"><span data-stu-id="76cc4-109">**Home Profile Name**</span></span>   |                                                                                                                       <span data-ttu-id="76cc4-110">Tipo **inicio**.</span><span class="sxs-lookup"><span data-stu-id="76cc4-110">Type **HOME**.</span></span>                                                                                                                       |
   | <span data-ttu-id="76cc4-111">**Nombre del socio comercial**</span><span class="sxs-lookup"><span data-stu-id="76cc4-111">**Trading Partner Name**</span></span> |                                                                                                                     <span data-ttu-id="76cc4-112">Tipo **asociado**.</span><span class="sxs-lookup"><span data-stu-id="76cc4-112">Type **PARTNER**.</span></span>                                                                                                                      |
   |       <span data-ttu-id="76cc4-113">**Nombre PIP**</span><span class="sxs-lookup"><span data-stu-id="76cc4-113">**PIP Name**</span></span>       |                                                                                                                       <span data-ttu-id="76cc4-114">Tipo **0c1**.</span><span class="sxs-lookup"><span data-stu-id="76cc4-114">Type **0C1**.</span></span>                                                                                                                        |
   |     <span data-ttu-id="76cc4-115">**Versión PIP**</span><span class="sxs-lookup"><span data-stu-id="76cc4-115">**PIP Version**</span></span>      |                                                                                                                      <span data-ttu-id="76cc4-116">Escriba **R01.02**.</span><span class="sxs-lookup"><span data-stu-id="76cc4-116">Type **R01.02**.</span></span>                                                                                                                      |
   |      <span data-ttu-id="76cc4-117">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="76cc4-117">**File Name**</span></span>       | <span data-ttu-id="76cc4-118">Haga clic en el botón de puntos suspensivos (**...** ) y mover a \< *unidad*:\>\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances .</span><span class="sxs-lookup"><span data-stu-id="76cc4-118">Click the ellipsis button (**...**), and move to \<*drive*:\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances.</span></span> <span data-ttu-id="76cc4-119">Seleccione **0C1_Request.xml** en la lista de archivos y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="76cc4-119">Select **0C1_Request.xml** from the list of files, and then click **Open**.</span></span> |
   |   <span data-ttu-id="76cc4-120">**Categoría de mensaje**</span><span class="sxs-lookup"><span data-stu-id="76cc4-120">**Message Category**</span></span>   |                                                                                                         <span data-ttu-id="76cc4-121">Seleccione **acción** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="76cc4-121">Select **Action** from the drop-down list.</span></span>                                                                                                         |


3. <span data-ttu-id="76cc4-122">En el **aplicación LOB** cuadro de diálogo, haga clic en **enviar mensaje**.</span><span class="sxs-lookup"><span data-stu-id="76cc4-122">In the **LOB Application** dialog box, click **Submit Message**.</span></span>  

   <span data-ttu-id="76cc4-123">La aplicación de LOB, genera un mensaje de Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] simulando un mensaje original generado por una aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="76cc4-123">The LOB application generates a message for Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] simulating an original message generated by an LOB application.</span></span> <span data-ttu-id="76cc4-124">Puede ver el estado del mensaje en la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="76cc4-124">You can view the status of the message in the Status window.</span></span>  

> [!NOTE]
>  <span data-ttu-id="76cc4-125">Los mensajes de ejemplo se suponen que los identificadores de negocio Global (GBI) para "Hogar" y "PARTNER" son 123456789 y 987654321, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="76cc4-125">The sample messages assume that the Global Business Identifiers (GBI) for "HOME" and "PARTNER" are 123456789 and 987654321, respectively.</span></span> <span data-ttu-id="76cc4-126">Para usar un GBI diferente, debe modificar el contenido de estos archivos.</span><span class="sxs-lookup"><span data-stu-id="76cc4-126">To use a different GBI, you must modify the content of these files.</span></span>  

## <a name="see-also"></a><span data-ttu-id="76cc4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="76cc4-127">See Also</span></span>  
 [<span data-ttu-id="76cc4-128">Paso 8: Ver los mensajes en las bases de datos de BTARN</span><span class="sxs-lookup"><span data-stu-id="76cc4-128">Step 8: View Messages in the BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)
