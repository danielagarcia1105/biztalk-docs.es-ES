---
title: "Cómo copiar los datos en el contexto del mensaje como campos distintivos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 004a13ca-a162-4a5e-9f72-8a5c55bbb7a6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ea68bc0b83c5a8f886416107e1dc98ea8ad8d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-data-to-the-message-context-as-distinguished-fields"></a><span data-ttu-id="7fc86-102">Cómo copiar los datos en el contexto del mensaje como campos distintivos</span><span class="sxs-lookup"><span data-stu-id="7fc86-102">How to Copy Data to the Message Context as Distinguished Fields</span></span>
<span data-ttu-id="7fc86-103">Este tema proporciona instrucciones paso a paso para promocionar una propiedad como un **campo distintivo**.</span><span class="sxs-lookup"><span data-stu-id="7fc86-103">This topic provides step-by-step instructions for promoting a property as a **Distinguished Field**.</span></span>  
  
 <span data-ttu-id="7fc86-104">Puede elegir **campo distintivo** promoción sobre **campo de propiedad** promoción por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7fc86-104">You might choose **Distinguished Field** promotion over **Property Field** promotion for the following reasons:</span></span>  
  
-   <span data-ttu-id="7fc86-105">**Campo de propiedad** valores se limitan a 255 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="7fc86-105">**Property Field** values are limited to 255 characters in length.</span></span>  
  
-   <span data-ttu-id="7fc86-106">**Campo de propiedad** valores se almacenan en una base de datos y, por tanto, tienen más sobrecarga que **campos distintivos**.</span><span class="sxs-lookup"><span data-stu-id="7fc86-106">**Property Field** values are stored in a database, and therefore have more overhead than **Distinguished Fields**.</span></span> <span data-ttu-id="7fc86-107">**Campos distintivos** no requieren ningún almacenamiento adicional; son básicamente un alias para una **XPath**, lo cual permite, por tanto, las orquestaciones más acceder fácilmente a los valores relevantes directamente desde el mensaje.</span><span class="sxs-lookup"><span data-stu-id="7fc86-107">**Distinguished Fields** do not require any additional storage; they are essentially an alias for an **XPath**, thereby allowing orchestrations to more easily access the relevant values directly from the message.</span></span>  
  
### <a name="to-promote-a-property-as-a-distinguished-field"></a><span data-ttu-id="7fc86-108">Para promocionar una propiedad como un campo distintivo</span><span class="sxs-lookup"><span data-stu-id="7fc86-108">To promote a property as a Distinguished Field</span></span>  
  
1.  <span data-ttu-id="7fc86-109">En el Editor de BizTalk, abra el esquema para el que desea promocionar una o varias propiedades y, a continuación, seleccione el (primer) **elemento de campo**, **atributo de campo**, o **registro** nodo que desea promover como un **campo distintivo**.</span><span class="sxs-lookup"><span data-stu-id="7fc86-109">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Distinguished Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7fc86-110">Los nodos registro nunca se pueden promocionar como **campos distintivos**, independientemente del tipo de contenido que incluyan.</span><span class="sxs-lookup"><span data-stu-id="7fc86-110">Record nodes can never be promoted as **Distinguished Fields**, regardless of the type of content they contain.</span></span>  
  
2.  <span data-ttu-id="7fc86-111">Haga clic en el nodo seleccionado, haga clic en **promover**y, a continuación, haga clic en **mostrar promociones**.</span><span class="sxs-lookup"><span data-stu-id="7fc86-111">Right-click the selected node, click **Promote**, and then click **Show Promotions**.</span></span>  
  
     <span data-ttu-id="7fc86-112">El **promocionar propiedades** abre el cuadro de diálogo con la muestra el nodo seleccionado en el árbol de esquema en el lado izquierdo del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7fc86-112">The **Promote Properties** dialog box opens with the selected node showing as selected in the schema tree on the left side of the dialog box.</span></span>  
  
3.  <span data-ttu-id="7fc86-113">En el **promocionar propiedades** cuadro de diálogo, seleccione la **campos distintivos** ficha.</span><span class="sxs-lookup"><span data-stu-id="7fc86-113">In the **Promote Properties** dialog box, select the **Distinguished Fields** tab.</span></span>  
  
4.  <span data-ttu-id="7fc86-114">Con el nodo para promocionar todavía seleccionado en el árbol de esquema en el lado izquierdo de la **promocionar propiedades** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7fc86-114">With the node to be promoted still selected in the schema tree on the left side of the **Promote Properties** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="7fc86-115">Si se permite, el nodo seleccionado se agrega a la lista en la **campos distintivos** ficha. En caso de no permitirse, un cuadro de mensajes proporciona una explicación.</span><span class="sxs-lookup"><span data-stu-id="7fc86-115">If allowed, the selected node is added to the list on the **Distinguished Fields** tab. If not allowed, a message box provides an explanation.</span></span>  
  
5.  <span data-ttu-id="7fc86-116">Puede seleccionar nodos adicionales para promocionarlos en el árbol de esquema en el lado izquierdo del cuadro de diálogo, haga clic en **agregar** después de cada selección.</span><span class="sxs-lookup"><span data-stu-id="7fc86-116">You can select additional nodes for promotion in the schema tree on the left side of the dialog box, clicking **Add** after each selection.</span></span>  
  
6.  <span data-ttu-id="7fc86-117">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7fc86-117">When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="7fc86-118">Los nodos seleccionados para promocionar son ahora **campos distintivos**.</span><span class="sxs-lookup"><span data-stu-id="7fc86-118">The nodes that you selected to promote are now **Distinguished Fields**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc86-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fc86-119">See Also</span></span>  
 <span data-ttu-id="7fc86-120">[Promoción de propiedades](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7fc86-120">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="7fc86-121">[Cómo crear esquemas de propiedades](../core/how-to-create-property-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="7fc86-121">[How to Create Property Schemas](../core/how-to-create-property-schemas.md) </span></span>  
 [<span data-ttu-id="7fc86-122">Formas de usar el contenido de mensaje para el procesamiento de mensajes de Control</span><span class="sxs-lookup"><span data-stu-id="7fc86-122">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)