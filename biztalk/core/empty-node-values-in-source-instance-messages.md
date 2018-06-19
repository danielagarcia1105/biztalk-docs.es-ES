---
title: Mensajes de instancia de valores de nodos vacíos en origen | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76f9d7c8-5a82-41e9-9077-7b1ddd80a837
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2a36271f5e9d66efc8ef0c50cdc9582f4de1261
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240084"
---
# <a name="empty-node-values-in-source-instance-messages"></a><span data-ttu-id="3fef0-102">Valores de nodos vacíos en mensajes de instancia de origen</span><span class="sxs-lookup"><span data-stu-id="3fef0-102">Empty Node Values in Source Instance Messages</span></span>
<span data-ttu-id="3fef0-103">En ocasiones puede que no desee tener contenido en todos los nodos de esquema cuando está comprobando una asignación.</span><span class="sxs-lookup"><span data-stu-id="3fef0-103">There may be times when you do not want content in all of the schema nodes when you test a map.</span></span>  
  
## <a name="ceate-empty-node-values"></a><span data-ttu-id="3fef0-104">Valores de cree nodos vacíos</span><span class="sxs-lookup"><span data-stu-id="3fef0-104">Ceate empty node values</span></span>  
  
1.  <span data-ttu-id="3fef0-105">Genere datos de instancia con el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="3fef0-105">Generate instance data using BizTalk Editor.</span></span> <span data-ttu-id="3fef0-106">Para obtener más información acerca de la generación de datos de instancia, consulte [cómo generar mensajes de instancia](../core/how-to-generate-instance-messages.md).</span><span class="sxs-lookup"><span data-stu-id="3fef0-106">For more information about generating instance data, see [How to Generate Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  
  
2.  <span data-ttu-id="3fef0-107">Abra el mensaje de instancia de entrada en un editor de texto, elimine los datos de elementos y atributos que desee que estén vacíos y, a continuación, guarde el archivo de instancia modificado.</span><span class="sxs-lookup"><span data-stu-id="3fef0-107">Open the input instance message in a text editor, delete the data from elements and attributes that you want to be empty, and then save the modified instance file.</span></span>  
  
3.  <span data-ttu-id="3fef0-108">Configure el Asignador de BizTalk para utilizar el archivo que acaba de modificar cuando se valida y comprueba el esquema.</span><span class="sxs-lookup"><span data-stu-id="3fef0-108">Configure BizTalk Mapper to use the file you just modified when the schema is validated and tested.</span></span> <span data-ttu-id="3fef0-109">Establezca el archivo en la ventana Propiedades para el esquema.</span><span class="sxs-lookup"><span data-stu-id="3fef0-109">You set the file in the Properties window for the schema.</span></span> <span data-ttu-id="3fef0-110">Para obtener más información acerca de las propiedades de configuración, consulte **propiedades de archivo de mapa** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="3fef0-110">For more information about setting properties, see **Map File Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3fef0-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fef0-111">See Also</span></span>  
-  [<span data-ttu-id="3fef0-112">Cómo generar mensajes de instancia</span><span class="sxs-lookup"><span data-stu-id="3fef0-112">How to Generate Instance Messages</span></span>](../core/how-to-generate-instance-messages.md)   
-  <span data-ttu-id="3fef0-113">**Referencia de esquema de propiedad**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="3fef0-113">**Schema Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>