---
title: Procesamiento de mensajes de instancia con campos distintivos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b8f3f77-5385-4294-b441-bcb28bdc51b4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4dca22ff1b09a0d1cfb261a9d5726da8b1b17b1
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="instance-message-processing-using-distinguished-fields"></a><span data-ttu-id="4207c-102">Procesar mensajes de instancia con campos distintivos</span><span class="sxs-lookup"><span data-stu-id="4207c-102">Instance Message Processing Using Distinguished Fields</span></span>
<span data-ttu-id="4207c-103">Promocionar propiedades mediante la **campo distintivo** mecanismo no requiere la creación de un esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4207c-103">Promoting properties by using the **Distinguished Field** mechanism does not require the creation of a property schema.</span></span> <span data-ttu-id="4207c-104">Como con la promoción de propiedades, use el **promocionar propiedades** cuadro de diálogo, que es accesible mediante la **promocionar propiedades** propiedad de la **esquema** nodo esquemas de mensaje o mediante el **promover &#124; mostrar promociones** comando el **BizTalk** o menús contextuales.</span><span class="sxs-lookup"><span data-stu-id="4207c-104">As with all property promotion, you use the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node in message schemas, or by using the **Promote &#124; Show Promotions** command on the **BizTalk** or shortcut menus.</span></span>  
  
 <span data-ttu-id="4207c-105">En el **promocionar propiedades** diálogo cuadro, asegúrese del **campos distintivos** ficha está seleccionada en el lado derecho del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4207c-105">In the **Promote Properties** dialog box, ensure the **Distinguished Fields** tab is selected in the right side of the dialog box.</span></span> <span data-ttu-id="4207c-106">A continuación, expanda los nodos del árbol de esquema en el lado izquierdo del cuadro de diálogo para buscar y seleccionar la **elemento de campo** nodo o **atributo de campo** nodo que desea promover como campo distintivo y, a continuación, Haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="4207c-106">Then you expand the nodes in the schema tree on the left side of the dialog box to find and select the **Field Element** node or **Field Attribute** node that you want to promote as a distinguished field, and then click **Add**.</span></span> <span data-ttu-id="4207c-107">Para obtener instrucciones detalladas acerca de la promoción de propiedades para **campos distintivos** mediante la **promocionar propiedades** cuadro de diálogo, vea [copiar datos en el contexto del mensaje como completos Campos](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md).</span><span class="sxs-lookup"><span data-stu-id="4207c-107">For step-by-step instructions about promoting properties to **Distinguished Fields** using the **Promote Properties** dialog, see [Copying Data to the Message Context as Distinguished Fields](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4207c-108">También puede promocionar un **registro** nodo a un nodo de elemento de campo en el esquema de propiedades, pero solo si la **tipo de contenido** propiedad de la **registro** nodo se establece en  **SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="4207c-108">You can also promote a **Record** node to a Field Element node in the property schema, but only if the **Content Type** property of the **Record** node is set to **SimpleContent**.</span></span>  
  
 <span data-ttu-id="4207c-109">Para quitar un nodo del conjunto de propiedades que se va a promocionar como campos distintivos, seleccione la propiedad promocionada en el **campos distintivos** ficha y haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="4207c-109">To remove a node from the set of properties being promoted as distinguished fields, select the promoted property on the **Distinguished Fields** tab, and click **Remove**.</span></span>  
  
 <span data-ttu-id="4207c-110">Si promociona las propiedades con el mecanismo de campo distintivo, se agregará un fragmento del lenguaje de definición de esquemas XML (XSD) dentro del subelemento de anotación del elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="4207c-110">When you promote properties by using the distinguished field mechanism, an XML Schema definition (XSD) language fragment is added within the annotation subelement of the root element.</span></span> <span data-ttu-id="4207c-111">En el siguiente ejemplo, el fragmento muestra dos propiedades promocionadas mediante el mecanismo de campo distintivo.</span><span class="sxs-lookup"><span data-stu-id="4207c-111">In the following example, the fragment shows two properties promoted by using the distinguished field mechanism.</span></span>  
  
```  
<b:properties>  
    <b:property distinguished="true"  
        xpath="/*[local-name()='Record' and namespace-  
         uri()='http://BizTalk_Server_Project1.Schema11']/*[local-  
         name()='test']/*[local-name()='Field1']" />  
    <b:property distinguished="true"  
        xpath="/*[local-name()='Record' and namespace-  
         uri()='http://BizTalk_Server_Project1.Schema11']/*[local-  
         name()='test']/*[local-name()='Field5' and position()='1']" />  
</b:properties>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4207c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4207c-112">See Also</span></span>  
 <span data-ttu-id="4207c-113">[Formas de usar el contenido de mensaje para el procesamiento de mensajes de Control](../core/ways-to-use-message-content-to-control-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="4207c-113">[Ways to Use Message Content to Control Message Processing](../core/ways-to-use-message-content-to-control-message-processing.md) </span></span>  
 [<span data-ttu-id="4207c-114">Cómo copiar los datos en el contexto del mensaje como campos distintivos</span><span class="sxs-lookup"><span data-stu-id="4207c-114">How to Copy Data to the Message Context as Distinguished Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)