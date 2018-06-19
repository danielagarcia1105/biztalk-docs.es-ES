---
title: Vistas personalizadas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9084cc07-be98-4c57-afea-4fa369a38bad
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184f49330374126f4afc0bd4bb376ea31a5ca681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238172"
---
# <a name="custom-views"></a><span data-ttu-id="e065a-102">Vistas personalizadas</span><span class="sxs-lookup"><span data-stu-id="e065a-102">Custom Views</span></span>
<span data-ttu-id="e065a-103">Una vista personalizada es normalmente un objeto de control de ventana de sólo lectura (derivado de **System.Windows.Forms.Control**) y se proporciona una extensión para representar el esquema en un formato de presentación personalizado para el tipo de archivo o archivos compatible mediante la extensión del Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e065a-103">A custom view is typically a read-only window control object (derived from **System.Windows.Forms.Control**), and is provided by an extension to represent the schema in a display format customized for the type of file or files supported by the BizTalk Editor extension.</span></span> <span data-ttu-id="e065a-104">Una extensión puede implementar varias vistas personalizadas, aunque no necesita tener ninguna vista personalizada.</span><span class="sxs-lookup"><span data-stu-id="e065a-104">An extension can implement multiple custom views, though it need not have any custom view.</span></span>  
  
 <span data-ttu-id="e065a-105">Una vista personalizada se muestra como una vista adicional en el mismo panel del Editor de BizTalk que la vista XSD y se puede tener acceso a ella a través de las pestañas situadas en la parte inferior de las vistas.</span><span class="sxs-lookup"><span data-stu-id="e065a-105">A custom view is displayed as an additional view in the same BizTalk Editor pane as the XSD view, accessible by using tabs at the bottom of the views.</span></span> <span data-ttu-id="e065a-106">Por ejemplo, Extensión de archivo sin formato agrega una nueva vista con una pestaña con la etiqueta Archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="e065a-106">For example, the Flat File Extension adds a new view with a tab labeled Flat File.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e065a-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="e065a-107">See Also</span></span>  
 [<span data-ttu-id="e065a-108">Extender el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e065a-108">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)