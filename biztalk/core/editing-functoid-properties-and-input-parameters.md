---
title: "Editar propiedades de Functoid y parámetros de entrada | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 257f92d7-8196-4c7c-98de-819996270e43
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f7839807244ecebadeb93640703886c12ce646a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="editing-functoid-properties-and-input-parameters"></a><span data-ttu-id="db322-102">Editar propiedades de functoid y parámetros de entrada</span><span class="sxs-lookup"><span data-stu-id="db322-102">Editing Functoid Properties and Input Parameters</span></span>
<span data-ttu-id="db322-103">Las propiedades de functoid pueden clasificarse de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="db322-103">Functoid properties can be categorized as follows:</span></span>  
  
-   <span data-ttu-id="db322-104">**Etiqueta** y **parámetros de entrada**.</span><span class="sxs-lookup"><span data-stu-id="db322-104">**Label** and **Input parameters**.</span></span> <span data-ttu-id="db322-105">Estas dos propiedades son de lectura y escritura y están disponibles para todos los functoids.</span><span class="sxs-lookup"><span data-stu-id="db322-105">These two properties are read/write and are available for all functoids.</span></span> <span data-ttu-id="db322-106">El **etiqueta** propiedad proporciona un mecanismo para proporcionar un nombre descriptivo para una instancia determinada de un functoid, que puede ayudar a mantener las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="db322-106">The **Label** property provides a mechanism for providing a descriptive name for a particular instance of a functoid, which may help in maintaining maps.</span></span> <span data-ttu-id="db322-107">El **parámetros de entrada** propiedad proporciona acceso a la **configurar \<Functoid > Functoid** cuadro de diálogo que desempeña un papel fundamental en la configuración de functoid.</span><span class="sxs-lookup"><span data-stu-id="db322-107">The **Input parameters** property provides access to the **Configure \<Functoid> Functoid** dialog box, which plays a central role in functoid configuration.</span></span>  
  
-   <span data-ttu-id="db322-108">**Secuencia de comandos** y **cuadrícula de bucle de tabla**.</span><span class="sxs-lookup"><span data-stu-id="db322-108">**Script** and **Table Looping Grid**.</span></span> <span data-ttu-id="db322-109">Estas dos propiedades proporcionan acceso a los cuadros de diálogo que solo son aplicables a la **secuencias de comandos** y **bucle de tabla** functoids, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="db322-109">These two properties provide access to dialog boxes that are only applicable to the **Scripting** and **Table Looping** functoids, respectively.</span></span> <span data-ttu-id="db322-110">Estos cuadros de diálogo son el **configurar Functoid de secuencias de comandos** cuadro de diálogo y el **configurar Functoid de bucle de tabla** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="db322-110">These dialog boxes are the **Configure Scripting Functoid** dialog box and the **Configure Table Looping Functoid** dialog box.</span></span>  
  
-   <span data-ttu-id="db322-111">**Nombre**, **ayuda**, **parámetros de entrada máximo**, y **mínimo de parámetros de entrada**.</span><span class="sxs-lookup"><span data-stu-id="db322-111">**Name**, **Help**, **Maximum Input Parameters**, and **Minimum Input Parameters**.</span></span> <span data-ttu-id="db322-112">Estas cuatro propiedades son informativas y exclusivamente de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="db322-112">These four are informational and always read-only.</span></span>  
  
 <span data-ttu-id="db322-113">Para obtener información conceptual acerca de estas propiedades de functoid, consulte [propiedades de Functoid](../core/functoid-properties.md).</span><span class="sxs-lookup"><span data-stu-id="db322-113">For conceptual information about these functoid properties, see [Functoid Properties](../core/functoid-properties.md).</span></span>  
  
 <span data-ttu-id="db322-114">Esta sección proporciona instrucciones paso a paso para trabajar con y modificar específicamente, las propiedades de functoids, se incluyen instrucciones generales para configurar parámetros de entrada para functoids, Configurar secuencia de comandos para la **secuencias de comandos**  functoid y configurar cuadrícula de tabla para la **bucle de tabla** functoid.</span><span class="sxs-lookup"><span data-stu-id="db322-114">This section provides step-by-step instructions for working with, and specifically modifying, the properties of functoids, including general instructions for configuring input parameters for functoids, configuring script for the **Scripting** functoid, and configuring table grid for the **Table Looping** functoid.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db322-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="db322-115">In This Section</span></span>  
  
-   [<span data-ttu-id="db322-116">Cómo configurar los parámetros de entrada de Functoid</span><span class="sxs-lookup"><span data-stu-id="db322-116">How to Configure Functoid Input Parameters</span></span>](../core/how-to-configure-functoid-input-parameters.md)  
  
-   [<span data-ttu-id="db322-117">Cómo configurar el Functoid de secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="db322-117">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)  
  
-   [<span data-ttu-id="db322-118">Cómo configurar el bucle de tabla y Functoids de Extractor de tabla</span><span class="sxs-lookup"><span data-stu-id="db322-118">How to Configure the Table Looping and Table Extractor Functoids</span></span>](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)  
  
-   [<span data-ttu-id="db322-119">Cómo etiquetar y comentar un Functoid</span><span class="sxs-lookup"><span data-stu-id="db322-119">How to Label and Comment a Functoid</span></span>](../core/how-to-label-and-comment-a-functoid.md)