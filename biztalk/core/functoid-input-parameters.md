---
title: Parámetros de entrada de functoid | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cca24f93-74a8-460c-b9ab-9aa2c767fe2f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4a430b96f7a76ad6f99a7b3f9ee151f17c7b55a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968514"
---
# <a name="functoid-input-parameters"></a><span data-ttu-id="c6b25-102">Parámetros de entrada de functoid</span><span class="sxs-lookup"><span data-stu-id="c6b25-102">Functoid Input Parameters</span></span>
<span data-ttu-id="c6b25-103">Un aspecto crucial de la utilización de functoids en las asignaciones es la correcta configuración de los parámetros de entrada del functoid.</span><span class="sxs-lookup"><span data-stu-id="c6b25-103">A critical aspect of using functoids in your maps is properly configuring the input parameters to the functoid.</span></span> <span data-ttu-id="c6b25-104">Aunque el orden de los parámetros de entrada no es crítico para todos los functoids (como el **adición** functoid, que muestra el mismo propiedades de asociación que cabe esperar de la suma), muchos functoids deben tener sus parámetros de entrada especificado en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="c6b25-104">While the order of input parameters is not critical for all functoids (such as the **Addition** functoid, which displays the same associate properties that one expects from addition), many functoids must have their input parameters specified in the correct order.</span></span>  
  
## <a name="create-input-paramaters"></a><span data-ttu-id="c6b25-105">Crear parámetros de entrada</span><span class="sxs-lookup"><span data-stu-id="c6b25-105">Create input paramaters</span></span>
 <span data-ttu-id="c6b25-106">Los parámetros de entrada de functoid se pueden crear de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="c6b25-106">There are two ways that input parameters to a functoid can be created:</span></span>  
  
-   <span data-ttu-id="c6b25-107">Creando vínculos en la parte izquierda de un functoid en la página de cuadrícula que se muestra.</span><span class="sxs-lookup"><span data-stu-id="c6b25-107">By creating links into the left side of a functoid in the displayed grid page.</span></span> <span data-ttu-id="c6b25-108">El orden en que se crean los vínculos es el mismo en que los parámetros de entrada asociados se transmiten al functoid.</span><span class="sxs-lookup"><span data-stu-id="c6b25-108">The order in which you create the links is the order in which the associated input parameters are passed to the functoid.</span></span>  
  
-   <span data-ttu-id="c6b25-109">Abriendo el **configurar \<Functoid\> Functoid** cuadro de diálogo y agregando nuevos parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="c6b25-109">By opening the **Configure \<Functoid\> Functoid** dialog box and adding new input parameters.</span></span> <span data-ttu-id="c6b25-110">Este cuadro de diálogo también es importante porque permite reorganizar los parámetros de entrada a un functoid para que estén en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="c6b25-110">This dialog box is also important because it allows you to reorder the input parameters to a functoid so that they are in the correct order.</span></span> <span data-ttu-id="c6b25-111">Por ejemplo, si crea vínculos al functoid en el orden adecuado, puede ir a este cuadro de diálogo y realizar las correcciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="c6b25-111">For example, if you create links to the functoid in the incorrect order, you can go to this dialog box and make the necessary corrections.</span></span> <span data-ttu-id="c6b25-112">Para obtener instrucciones paso a paso acerca de cómo configurar los parámetros de entrada de un functoid, consulte [cómo configurar parámetros de entrada del Functoid](../core/how-to-configure-functoid-input-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c6b25-112">For step-by-step instructions on configuring the input parameters for a functoid, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
  
 <span data-ttu-id="c6b25-113">Debe utilizar el **configurar \<Functoid\> Functoid** cuadro de diálogo para crear parámetros de entrada que son constantes.</span><span class="sxs-lookup"><span data-stu-id="c6b25-113">You must use the **Configure \<Functoid\> Functoid** dialog box to create input parameters that are constants.</span></span>  
  
 <span data-ttu-id="c6b25-114">Cuando se proporciona una etiqueta para un vínculo o functoid utilizando la **etiqueta** propiedad en la ventana Propiedades cuando se selecciona el vínculo o functoid, esa etiqueta se mostrará en el **configurar \<Functoid\> Functoid** cuadro de diálogo en lugar de la expresión XPath correspondiente de un nodo de esquema o el nombre de un functoid que se va a usar como un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="c6b25-114">When you provide a label for a link or functoid using the **Label** property in the Properties window when the link or functoid is selected, that label will be shown in the **Configure \<Functoid\> Functoid** dialog box rather than the corresponding XPath of a schema node, or the name of a functoid being used as an input parameter.</span></span> <span data-ttu-id="c6b25-115">Con las etiquetas, será mucho más fácil distinguir los parámetros y ordenarlos correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6b25-115">With labels, it will be much easier to tell which parameter is which, and to get them into the correct order.</span></span>  
  
 <span data-ttu-id="c6b25-116">Para obtener una información sobre el orden correcto de parámetros de entrada de functoid, consulte el **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="c6b25-116">For definitive information about the correct order of functoid input parameters, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c6b25-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6b25-117">See Also</span></span>  
 <span data-ttu-id="c6b25-118">[Configurar los parámetros de entrada de Functoid](../core/how-to-configure-functoid-input-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="c6b25-118">[Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md) </span></span>  
 <span data-ttu-id="c6b25-119">[Configurar el Functoid de secuencias de comandos](../core/how-to-configure-the-scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="c6b25-119">[Configure the Scripting Functoid](../core/how-to-configure-the-scripting-functoid.md) </span></span>  
 [<span data-ttu-id="c6b25-120">Configurar los functoids de bucle de tabla y de extractor de tablas</span><span class="sxs-lookup"><span data-stu-id="c6b25-120">Configure the Table Looping and Table Extractor Functoids</span></span>](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)