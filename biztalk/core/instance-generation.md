---
title: "Generación de la instancia | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14060dca-5e14-474a-bf2c-4e8bc56e3c61
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46bd3d2bc6852ec0c73fbbe4ffc55924a8012ce5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="instance-generation"></a><span data-ttu-id="a4d45-102">Generación de instancias</span><span class="sxs-lookup"><span data-stu-id="a4d45-102">Instance Generation</span></span>
<span data-ttu-id="a4d45-103">El Editor de BizTalk, se invoca el **IInstanceGenerator.GenerateInstance** método de una extensión cuando se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4d45-103">BizTalk Editor invokes the **IInstanceGenerator.GenerateInstance** method of an extension when the following conditions are met:</span></span>  
  
-   <span data-ttu-id="a4d45-104">La extensión está establecida como estándar mediante el uso de la **estándar** propiedad de la **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="a4d45-104">The extension is set as standard by using the **Standard** property of the **Schema** node.</span></span>  
  
-   <span data-ttu-id="a4d45-105">En el **páginas de propiedades** cuadro de diálogo asociado con el esquema, el **genere el tipo de salida de instancia** propiedad está establecida en **nativo.**</span><span class="sxs-lookup"><span data-stu-id="a4d45-105">On the **Property Pages** dialog box associated with the schema, the **Generate Instance Output Type** property is set to **Native.**</span></span>  
  
-   <span data-ttu-id="a4d45-106">En el **páginas de propiedades** asociado con el esquema, el cuadro de diálogo la **nombre de archivo de instancia de salida** propiedad se establece en el nombre del archivo que se guardará en la instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="a4d45-106">On the **Property Pages** dialog box associated with the schema, the **Output Instance Filename** property is set to the name of the file that the output instance will be saved to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4d45-107">Si el **nombre de archivo de instancia de salida** propiedad no está establecida, se utiliza un nombre de archivo predeterminado en una carpeta temporal para el mensaje de instancia generado y se proporciona un vínculo a él en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="a4d45-107">If the **Output Instance Filename** property is not set, a default file name in a temporary folder is used for the generated instance message, and a link to it is provided in the Output window.</span></span>  
  
 <span data-ttu-id="a4d45-108">Antes de la **IInstanceValidator.ValidateInstance** se llama al método, el Editor de BizTalk genera un mensaje de instancia XML de ejemplo y, a continuación, se pasa y el archivo especificado en el **nombre de archivo de instancia de salida** propiedad o un nombre de archivo predeterminado, a ese método.</span><span class="sxs-lookup"><span data-stu-id="a4d45-108">Before the **IInstanceValidator.ValidateInstance** method is called, BizTalk Editor generates a sample XML instance message, and then passes it and the file specified in the **Output Instance Filename** property, or a default file name, to that method.</span></span>  
  
 <span data-ttu-id="a4d45-109">Si se producen errores, mensajes de error se devuelven como una matriz de **IValidationInfo** objetos y se muestran en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="a4d45-109">If errors occur, error messages are returned as an array of **IValidationInfo** objects, and are displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Task List window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d45-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4d45-110">See Also</span></span>  
 [<span data-ttu-id="a4d45-111">Extender el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a4d45-111">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)