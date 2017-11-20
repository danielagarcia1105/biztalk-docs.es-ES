---
title: "Cómo agregar formas a orquestaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes, orchestrations
- orchestrations, shapes
- Construct Message shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Scope shape [Orchestration Designer]
ms.assetid: d39eb12c-cdc6-4918-93d9-536db1dfb889
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9fa6634adb20ffcf927da0af6f58e9daa2800ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-shapes-to-orchestrations"></a><span data-ttu-id="5e108-102">Cómo agregar formas a orquestaciones</span><span class="sxs-lookup"><span data-stu-id="5e108-102">How to Add Shapes to Orchestrations</span></span>
<span data-ttu-id="5e108-103">En esta sección se describen los procedimientos para agregar y quitar formas en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="5e108-103">This section describes the procedures for adding and removing shapes in your orchestration.</span></span> <span data-ttu-id="5e108-104">Para obtener más información acerca de las formas disponibles, consulte [formas de orquestación](../core/orchestration-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="5e108-104">For more information about the available shapes, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
### <a name="to-add-a-shape-to-an-orchestration"></a><span data-ttu-id="5e108-105">Para agregar una forma a una orquestación</span><span class="sxs-lookup"><span data-stu-id="5e108-105">To add a shape to an orchestration</span></span>  
  
1.  <span data-ttu-id="5e108-106">En el cuadro de herramientas, en la **orquestaciones de BizTalk** ficha, arrastre la forma hasta una línea de conexión en la superficie de diseño de orquestación.</span><span class="sxs-lookup"><span data-stu-id="5e108-106">In the Toolbox, on the **BizTalk Orchestrations** tab, drag the shape onto a connecting line on the Orchestration Design Surface.</span></span>  
  
     <span data-ttu-id="5e108-107">: "O":</span><span class="sxs-lookup"><span data-stu-id="5e108-107">—Or—</span></span>  
  
2.  <span data-ttu-id="5e108-108">Haga clic en la línea de conexión o el marcador de posición de la forma en la que desea agregar la forma, seleccione **Insertar forma**y, a continuación, haga clic en el nombre de la forma que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="5e108-108">Right-click the connecting line or the shape placeholder where you want to add the shape, point to **Insert Shape**, and then click the shape name you want to add.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e108-109">Si una forma aún no está completamente configurada, aparece una etiqueta inteligente sobre ella.</span><span class="sxs-lookup"><span data-stu-id="5e108-109">A Smart Tag appears on shapes that are not yet fully configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e108-110">**Transformar** formas y **asignación de mensajes** solo pueden existir dentro de un **construir mensaje** forma.</span><span class="sxs-lookup"><span data-stu-id="5e108-110">**Transform** shapes and **Message Assignment** shapes can only exist within a **Construct Message** shape.</span></span> <span data-ttu-id="5e108-111">Si agrega una de estas formas a la orquestación fuera de un **construir mensaje** forma, se colocará automáticamente dentro de una nueva **construir mensaje** forma.</span><span class="sxs-lookup"><span data-stu-id="5e108-111">If you add one of these shapes to your orchestration outside of a **Construct Message** shape, it is placed automatically inside a new **Construct Message** shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e108-112">**Detectar excepciones** y **compensación** bloques solo pueden existir a continuación un **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="5e108-112">**Catch Exception** and **Compensation** blocks can only exist following a **Scope** shape.</span></span>  
  
### <a name="to-remove-a-shape-from-an-orchestration"></a><span data-ttu-id="5e108-113">Para quitar una forma de una orquestación</span><span class="sxs-lookup"><span data-stu-id="5e108-113">To remove a shape from an orchestration</span></span>  
  
1.  <span data-ttu-id="5e108-114">Haga clic en la forma en la superficie de diseño y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5e108-114">Right-click the shape on the design surface, and then click **Delete**.</span></span>  
  
     <span data-ttu-id="5e108-115">: "O":</span><span class="sxs-lookup"><span data-stu-id="5e108-115">—Or—</span></span>  
  
2.  <span data-ttu-id="5e108-116">Seleccione la forma y presione la **eliminar** clave.</span><span class="sxs-lookup"><span data-stu-id="5e108-116">Select the shape and press the **DELETE** key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e108-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e108-117">See Also</span></span>  
 [<span data-ttu-id="5e108-118">Crear orquestaciones</span><span class="sxs-lookup"><span data-stu-id="5e108-118">Creating Orchestrations</span></span>](../core/creating-orchestrations.md)