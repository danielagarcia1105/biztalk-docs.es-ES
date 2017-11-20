---
title: "Cómo editar el Selector XPath para procesar varios registros | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, editing multiple records
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: ef7e1f8d-2e29-4cef-b558-0090648bffc0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34c9b45e3fce9f4ad5730d7f03d2a568b3701742
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-edit-xpath-selector-to-process-multiple-records"></a><span data-ttu-id="b13a0-102">Cómo editar el selector XPath para procesar varios registros</span><span class="sxs-lookup"><span data-stu-id="b13a0-102">How to Edit XPath Selector to Process Multiple Records</span></span>
<span data-ttu-id="b13a0-103">Secundarios independientes TypedXmlDocuments se crean cuando se impone un TypedXmlDocument en el motor; vea [Assert](../core/assert.md).</span><span class="sxs-lookup"><span data-stu-id="b13a0-103">Separate child TypedXmlDocuments are created when a TypedXmlDocument is asserted into the engine; see [Assert](../core/assert.md).</span></span> <span data-ttu-id="b13a0-104">El motor determina los TypedXmlDocuments secundarios que se van a crear según los selectores XPath que estén definidos en las reglas.</span><span class="sxs-lookup"><span data-stu-id="b13a0-104">The engine determines which child TypedXmlDocuments to create based on the XPath selectors defined in the rules.</span></span> <span data-ttu-id="b13a0-105">Cuando genera reglas en el Compositor, el valor predeterminado del selector XPath es el nodo que hay por encima del nodo seleccionado en la pestaña Esquemas XML en el Explorador de hechos.</span><span class="sxs-lookup"><span data-stu-id="b13a0-105">When you build rules in the Composer, the XPath Selector value defaults to the node above the node selected in the XML Schemas tab in the Facts Explorer.</span></span> <span data-ttu-id="b13a0-106">Valor predeterminado es el valor de XPath Field al nodo seleccionado, en relación con su nodo primario.</span><span class="sxs-lookup"><span data-stu-id="b13a0-106">The XPath Field value defaults to the selected node itself, relative to its parent node.</span></span>  
  
 <span data-ttu-id="b13a0-107">En algunas situaciones tal vez desee personalizar el XPath predeterminado que el Compositor crea cuando genera reglas.</span><span class="sxs-lookup"><span data-stu-id="b13a0-107">In some situations you may want to customize the default XPath that the Composer creates when building rules.</span></span> <span data-ttu-id="b13a0-108">Observe el siguiente documento XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b13a0-108">Assume the following sample XML document.</span></span>  
  
```  
<Order>  
   <Orderline>  
      <Hat style="Baseball">                        
         <Cost>10</Cost>  
      </Hat>  
      <Shirt color="Black">  
         <Cost>20</Cost>  
      </Shirt>  
      <Total></Total>  
   </Orderline>  
   <Orderline>  
      <Hat style="Bowler">                        
         <Cost>20</Cost>  
      </Hat>  
      <Shirt color="Red">  
         <Cost>20</Cost>  
      </Shirt>  
      <Total></Total>  
   </Orderline>  
</Order>  
```  
  
 <span data-ttu-id="b13a0-109">Suponga que desea generar una regla que calcule el valor Total para cada Orderline.</span><span class="sxs-lookup"><span data-stu-id="b13a0-109">Assume that you want to build a rule that calculates the Total value for each Orderline.</span></span> <span data-ttu-id="b13a0-110">Su regla tendría el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="b13a0-110">Your rule would look like the following.</span></span>  
  
 <span data-ttu-id="b13a0-111">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="b13a0-111">IF 1==1</span></span>  
  
 <span data-ttu-id="b13a0-112">A continuación, **/Order/Orderline/**Total = (**/Order/Orderline/Hat/**costo + **/Order/Orderline/camisa/**costo)</span><span class="sxs-lookup"><span data-stu-id="b13a0-112">THEN **/Order/Orderline/**Total = (**/Order/Orderline/Hat/**Cost + **/Order/Orderline/Shirt/**Cost)</span></span>  
  
 <span data-ttu-id="b13a0-113">La parte en negrita de los XPath indica la parte del Selector y el resto representa el XPath de campo.</span><span class="sxs-lookup"><span data-stu-id="b13a0-113">The bold portion of the XPaths indicate the Selector portion and the remainder represents the Field XPath.</span></span> <span data-ttu-id="b13a0-114">Estos son los valores predeterminados que genera el Compositor.</span><span class="sxs-lookup"><span data-stu-id="b13a0-114">These are the defaults built by the Composer.</span></span> <span data-ttu-id="b13a0-115">Ejecute esta directiva, sin embargo, se crearán en la creación de 6 objetos: 2 objetos de Orderline, 2 objetos Hat y 2 objetos camisa.</span><span class="sxs-lookup"><span data-stu-id="b13a0-115">Running this policy, however, would result in the creation of 6 objects—2 Orderline objects, 2 Hat objects, and 2 Shirt objects.</span></span> <span data-ttu-id="b13a0-116">Los totales de Orderline se calcularán para cada combinación de objetos Hat y Shirt, y los totales siempre se establecerán con el mismo valor, que se obtuvo de la última ejecución de la regla.</span><span class="sxs-lookup"><span data-stu-id="b13a0-116">The Orderline totals would be calculated for each combination of Hat and Shirt objects and the totals would always be set to the same value, which resulted from the last execution of the rule.</span></span> <span data-ttu-id="b13a0-117">La regla se activará 8 veces.</span><span class="sxs-lookup"><span data-stu-id="b13a0-117">The rule would fire 8 times.</span></span> <span data-ttu-id="b13a0-118">Esto no es lo que se pretende en este escenario.</span><span class="sxs-lookup"><span data-stu-id="b13a0-118">This is not what is intended in this scenario.</span></span>  
  
 <span data-ttu-id="b13a0-119">Una solución sería editar los valores de XPath de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="b13a0-119">One solution would be to edit the XPath values to be as follows.</span></span>  
  
 <span data-ttu-id="b13a0-120">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="b13a0-120">IF 1==1</span></span>  
  
 <span data-ttu-id="b13a0-121">A continuación, **/Order/Orderline/**Total = (**/Order/Orderline/**Hat/costo + **/Order/Orderline/**camisa/costo)</span><span class="sxs-lookup"><span data-stu-id="b13a0-121">THEN **/Order/Orderline/**Total = (**/Order/Orderline/**Hat/Cost + **/Order/Orderline/**Shirt/Cost)</span></span>  
  
 <span data-ttu-id="b13a0-122">Los valores del selector XPath para los tres campos se han establecido con el mismo valor /Order/Orderline y los valores de XPath de campo se han editado en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="b13a0-122">The Selector XPath values for all three fields have been set to the same /Order/Orderline value and the Field XPath values have been edited accordingly.</span></span> <span data-ttu-id="b13a0-123">Esto se realiza cambiando los valores de campo de selector XPath y XPath en la ventana Propiedades cuando se selecciona un nodo en la pestaña Esquemas XML. Este cambio debe hacerse antes de arrastrar el campo al argumento de la regla.</span><span class="sxs-lookup"><span data-stu-id="b13a0-123">This is done by changing the XPath Selector and XPath Field values in the Properties window when a node is selected in the XML Schemas tab. This should be done prior to dragging the field into a rule argument.</span></span>  
  
 <span data-ttu-id="b13a0-124">Si ejecuta la directiva con este cambio, el valor de Total se calcularía correctamente para cada Orderline según los valores de Cost de los nodos Shirt y Hat dentro de esa Orderline.</span><span class="sxs-lookup"><span data-stu-id="b13a0-124">Executing the policy with this change would result in the Total value being correctly calculated for each Orderline based on the Cost values of the Shirt and Hat nodes within that Orderline.</span></span>