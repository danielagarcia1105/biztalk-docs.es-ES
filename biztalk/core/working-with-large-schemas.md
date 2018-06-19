---
title: Trabajar con esquemas grandes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8348036d-6edb-46a3-badd-0223cfe0a92f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5c5ef679070009b5dfb5fdd403d238cfe243cb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289716"
---
# <a name="working-with-large-schemas"></a><span data-ttu-id="298d2-102">Trabajar con esquemas grandes</span><span class="sxs-lookup"><span data-stu-id="298d2-102">Working with Large Schemas</span></span>
<span data-ttu-id="298d2-103">Cuando los esquemas lleguen a ser muy grandes, tal vez note una mayor lentitud al actualizar la vista XSD, así como que la respuesta de otros aspectos de la interfaz de usuario también se pueden haber visto afectados.</span><span class="sxs-lookup"><span data-stu-id="298d2-103">When your schemas become very large, you may find that refreshing the XSD view is increasingly slow and that the response of other aspects of the user interface can be impacted as well.</span></span> <span data-ttu-id="298d2-104">La solución a este problema consiste en desactivar la característica de actualización automática y utilice en su lugar el manual **actualizar** vínculo en la vista XSD para actualizar periódicamente la vista XSD.</span><span class="sxs-lookup"><span data-stu-id="298d2-104">The solution to this issue is to turn off the auto-refresh feature and instead use the manual **Refresh** link in the XSD view to periodically refresh the XSD view.</span></span> <span data-ttu-id="298d2-105">Para obtener instrucciones paso a paso sobre cómo activar la característica de actualización automática en una desactivados, vea el procedimiento "para activar y desactivar la actualización automática de la vista XSD" en [administrar la vista XSD](../core/how-to-manage-the-xsd-view.md).</span><span class="sxs-lookup"><span data-stu-id="298d2-105">For step-by-step instructions about how turn the auto-refresh feature on an off, see the procedure "To turn automatic refresh of the XSD view on and off" in [Managing the XSD View](../core/how-to-manage-the-xsd-view.md).</span></span>  
  
 <span data-ttu-id="298d2-106">Rendimiento también puede ser lento en esquemas grandes con varias raíces conectadas a la **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="298d2-106">Performance may also be slow in large schemas with multiple roots attached to the **schema** node.</span></span> <span data-ttu-id="298d2-107">Establecer el **referencia raíz** propiedad puede aumentar el rendimiento de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="298d2-107">Setting the **Root Reference** property may increase performance in the user interface.</span></span> <span data-ttu-id="298d2-108">Establecer **referencia raíz** mejora el rendimiento porque el compilador crea clases de C# para todos los esquemas de raíz.</span><span class="sxs-lookup"><span data-stu-id="298d2-108">Setting **Root Reference** improves performance because the compiler creates C# classes for all root schemas.</span></span> <span data-ttu-id="298d2-109">Una única raíz implica la creación de menos clases.</span><span class="sxs-lookup"><span data-stu-id="298d2-109">A single root means the creation of fewer classes.</span></span>  
  
 <span data-ttu-id="298d2-110">**Validar instancia** puede parecer lento en la interfaz de usuario porque la validación se realiza siempre en el esquema antes de validar la instancia.</span><span class="sxs-lookup"><span data-stu-id="298d2-110">**Validate Instance** may appear slow in the user interface because a validation is always done on the schema before validating the instance.</span></span> <span data-ttu-id="298d2-111">La validación del esquema solo tiene lugar en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="298d2-111">Schema validation occurs only in the user interface.</span></span> <span data-ttu-id="298d2-112">Establecer el **referencia raíz** propiedad también mejora el rendimiento de la interfaz de usuario en este caso.</span><span class="sxs-lookup"><span data-stu-id="298d2-112">Setting the **Root Reference** property also improves user interface performance in this case.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="298d2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="298d2-113">See Also</span></span>  
 [<span data-ttu-id="298d2-114">Usar el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="298d2-114">Using BizTalk Editor</span></span>](../core/using-biztalk-editor.md)