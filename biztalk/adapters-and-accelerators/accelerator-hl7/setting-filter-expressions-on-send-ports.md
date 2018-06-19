---
title: Establecer expresiones de filtro en puertos de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, context properties
- filtering, send ports
- send ports, filtering
- context properties, send ports
- context properties, filtering
- filtering, context properties
ms.assetid: 48c7c83b-9464-4ed9-bd8d-cf5b75e16702
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b94497f4e1412f81c36df3195994aafa32ecc451
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206084"
---
# <a name="setting-filter-expressions-on-send-ports"></a><span data-ttu-id="842b8-102">Expresiones de filtro de la configuración de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="842b8-102">Setting Filter Expressions on Send Ports</span></span>
<span data-ttu-id="842b8-103">Establecer propiedades de contexto en expresiones de filtro en el puerto de envío para controlar el puerto que envía.</span><span class="sxs-lookup"><span data-stu-id="842b8-103">You set context properties in filter expressions on the send port to control what the port sends.</span></span> <span data-ttu-id="842b8-104">Puede establecer las expresiones de filtro con un número de operadores que ofrecen flexibilidad en cómo filtrar la propiedad (igualdad o desigualdad, existe, mayor que, mayor o igual a, menor que y menor o igual que).</span><span class="sxs-lookup"><span data-stu-id="842b8-104">You can set the filter expressions with a number of operators that offer you flexibility in how you filter the property (equality or inequality, exists, greater than, great than or equal to, less than, and less than or equal to).</span></span>  
  
### <a name="to-set-the-filter-expression-on-a-send-port"></a><span data-ttu-id="842b8-105">Para establecer la expresión de filtro en un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="842b8-105">To set the filter expression on a send port</span></span>  
  
1.  <span data-ttu-id="842b8-106">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **aplicación de BizTalk 1** (u otra aplicación).</span><span class="sxs-lookup"><span data-stu-id="842b8-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1** (or another application).</span></span> <span data-ttu-id="842b8-107">Haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="842b8-107">Click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="842b8-108">Haga clic en el puerto de envío que desea establecer la expresión de filtro para y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="842b8-108">Right-click the send port that you want to set the filter expression for, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="842b8-109">En el árbol de consola del cuadro de diálogo Propiedades de puerto de envío, haga clic en **filtros**.</span><span class="sxs-lookup"><span data-stu-id="842b8-109">In the console tree of the Send Port Properties dialog box, click **Filters**.</span></span>  
  
4.  <span data-ttu-id="842b8-110">Haga clic en el cuadro de texto en el **propiedad** columna y, a continuación, seleccione la propiedad de contexto de la **propiedad** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="842b8-110">Click the text box in the **Property** column, and then select the context property from the **Property** drop-down list.</span></span>  
  
5.  <span data-ttu-id="842b8-111">Haga clic en el **operador** cuadro en la fila de la propiedad y seleccione el operador para la propiedad de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="842b8-111">Click the **Operator** box in the row for the property, and select the operator for the property from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="842b8-112">Haga clic en el **valor** cuadro en la fila de la propiedad y escriba una expresión de valor.</span><span class="sxs-lookup"><span data-stu-id="842b8-112">Click the **Value** box in the row for the property, and type a value expression.</span></span>  
  
7.  <span data-ttu-id="842b8-113">Si necesita agregar otra cláusula para la expresión de filtro, haga clic en el **Group By** cuadro en la fila de la propiedad y seleccione **y** o **o** para determinar la relación de la cláusulas.</span><span class="sxs-lookup"><span data-stu-id="842b8-113">If you need to add another  clause for the filter expression, click the **Group By** box in the row for the property, and select **And** or **Or** to determine the relationship of the clauses.</span></span>  
  
8.  <span data-ttu-id="842b8-114">Repita los pasos del 4 al 6 para agregar otra cláusula de filtro.</span><span class="sxs-lookup"><span data-stu-id="842b8-114">Repeat steps 4 through 6 to add another filter clause.</span></span>  
  
9. <span data-ttu-id="842b8-115">Compruebe que la expresión de filtro es correcta en el panel en la parte inferior de la **filtros** panel.</span><span class="sxs-lookup"><span data-stu-id="842b8-115">Verify that the filter expression is correct in the pane at the bottom of the **Filters** pane.</span></span>  
  
10. <span data-ttu-id="842b8-116">Cuando haya agregado todas las cláusulas de filtro, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="842b8-116">When you have added all filter clauses, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842b8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="842b8-117">See Also</span></span>  
 <span data-ttu-id="842b8-118">[Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="842b8-118">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 [<span data-ttu-id="842b8-119">Usar propiedades de contexto</span><span class="sxs-lookup"><span data-stu-id="842b8-119">Using Context Properties</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-context-properties.md)