---
title: Coincidencia de nodos de esquema en un mapa | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 584f85d2-6198-4ef3-90d9-a322f1457d9a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1e2ce880489ca49b0b55d2e6f45b9e887d719a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-match-schema-nodes-in-a-map"></a><span data-ttu-id="ba729-102">Coincidencia de nodos de esquema en una asignación</span><span class="sxs-lookup"><span data-stu-id="ba729-102">How to Match Schema Nodes in a Map</span></span>
<span data-ttu-id="ba729-103">Si los esquemas de origen o destino son complejos, puede resultar difícil asignar los elementos.</span><span class="sxs-lookup"><span data-stu-id="ba729-103">When the source or destination schemas are complex, it can be difficult to map the elements.</span></span> <span data-ttu-id="ba729-104">El asignador de BizTalk presenta la **coincidencia indicativa** característica, que le permite asignar elementos de esquema complejos sugiriendo las mejores coincidencias.</span><span class="sxs-lookup"><span data-stu-id="ba729-104">The BizTalk Mapper introduces the **Indicative Match** feature, which enables you to map complex schema elements by suggesting the best possible matches.</span></span> <span data-ttu-id="ba729-105">Este tema proporciona información acerca de cómo realizar esta operación.</span><span class="sxs-lookup"><span data-stu-id="ba729-105">This topic provides information about how to perform this operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba729-106">El Asignador de BizTalk sugiere posibles coincidencias para un nodo de esquema.</span><span class="sxs-lookup"><span data-stu-id="ba729-106">The BizTalk Mapper suggests possible matches for a schema node.</span></span> <span data-ttu-id="ba729-107">Esta característica es compatible actualmente solo para nombres en inglés.</span><span class="sxs-lookup"><span data-stu-id="ba729-107">This feature is currently supported only for English names.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ba729-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ba729-108">Prerequisites</span></span>  
 <span data-ttu-id="ba729-109">Estas instrucciones requieren que el Asignador de BizTalk esté en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ba729-109">These instructions require that the BizTalk Mapper is running.</span></span>  
  
### <a name="to-match-relevant-schema-nodes"></a><span data-ttu-id="ba729-110">Procedimiento para hacer coincidir nodos de esquemas relevantes</span><span class="sxs-lookup"><span data-stu-id="ba729-110">To match relevant schema nodes</span></span>  
  
1.  <span data-ttu-id="ba729-111">Seleccione y haga clic en el elemento de esquema para el que necesite conocer las mejores coincidencias y, a continuación, haga clic en **indicar coincidencias**.</span><span class="sxs-lookup"><span data-stu-id="ba729-111">Select and right-click the schema element for which you need to know the best matches, and then click **Indicate Matches**.</span></span> <span data-ttu-id="ba729-112">El Asignador de BizTalk destaca las mejores coincidencias (siete como máximo), con las óptimas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="ba729-112">The BizTalk Mapper highlights the best matches (restricted to seven), with the most optimum match selected.</span></span>  
  
     <span data-ttu-id="ba729-113">Como alternativa, puede seleccionar **indicar coincidencias** desde el menú BizTalk o presione MAYÚS + BARRA ESPACIADORA.</span><span class="sxs-lookup"><span data-stu-id="ba729-113">Alternatively, you can select **Indicate Matches** from the BizTalk menu, or press SHIFT + SPACE keys.</span></span>  
  
     <span data-ttu-id="ba729-114">En la siguiente figura se muestran coincidencias sugeridas para el nodo seleccionado en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="ba729-114">The following figure shows suggestive matches for the selected node in destination schema.</span></span>  
  
     <span data-ttu-id="ba729-115">![Asignación sugestiva](../core/media/suggestive-mapping.gif "Suggestive_Mapping")</span><span class="sxs-lookup"><span data-stu-id="ba729-115">![Suggestive mapping](../core/media/suggestive-mapping.gif "Suggestive_Mapping")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba729-116">Mantenga presionada la tecla MAYÚS para desplazarse por las coincidencias sugeridas.</span><span class="sxs-lookup"><span data-stu-id="ba729-116">Hold down the SHIFT key to traverse among the suggestive matches.</span></span>  
  
2.  <span data-ttu-id="ba729-117">Ahora, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba729-117">You can now do the following:</span></span>  
  
    -   <span data-ttu-id="ba729-118">Presione INTRO para confirmar la coincidencia resaltada (la mejor posible).</span><span class="sxs-lookup"><span data-stu-id="ba729-118">Press ENTER to confirm the highlighted (best possible) match.</span></span>  
  
    -   <span data-ttu-id="ba729-119">Use las teclas ARRIBA/ABAJO para desplazarse por las coincidencias resaltadas por orden de preferencia.</span><span class="sxs-lookup"><span data-stu-id="ba729-119">Use the UP/DOWN ARROW keys to cycle through the highlighted matches in the order of preference.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ba729-120">Presione la tecla ABAJO para pasar a la coincidencia siguiente; la tecla ARRIBA resalta la mejor coincidencia anterior.</span><span class="sxs-lookup"><span data-stu-id="ba729-120">Press the DOWN ARROW key to traverse to the next best match, and the UP ARROW key highlights the previous best match.</span></span>  
  
    -   <span data-ttu-id="ba729-121">Presione la tecla INICIO para volver a la coincidencia superior.</span><span class="sxs-lookup"><span data-stu-id="ba729-121">Press the HOME key to return to the top match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba729-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba729-122">See Also</span></span>  
 [<span data-ttu-id="ba729-123">Uso de características mejoradas en el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ba729-123">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)