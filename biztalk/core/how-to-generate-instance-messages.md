---
title: Cómo generar mensajes de instancia | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff74c67a-7e73-4153-9ec4-e6e50464ee92
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a911e4b0f1167e8ec200dad65b8dacb94bb08be3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254404"
---
# <a name="how-to-generate-instance-messages"></a><span data-ttu-id="31b8a-102">Cómo generar mensajes de instancia</span><span class="sxs-lookup"><span data-stu-id="31b8a-102">How to Generate Instance Messages</span></span>
<span data-ttu-id="31b8a-103">Una vez creado un esquema, una forma de comprobar el trabajo es generar un mensaje de instancia de ejemplo a partir del esquema.</span><span class="sxs-lookup"><span data-stu-id="31b8a-103">After you have constructed a schema, one way to check your work is to generate a sample instance message from the schema.</span></span> <span data-ttu-id="31b8a-104">Examinar un mensaje de instancia es mucho más sencillo en muchos sentidos que mirar el árbol de esquema o la representación del esquema en el lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="31b8a-104">In many ways, looking at an instance message is much more straightforward than looking at either the schema tree or the XML Schema definition (XSD) language representation of the schema.</span></span> <span data-ttu-id="31b8a-105">El motivo es que el esquema debe describir todas las variaciones posibles de los mensajes de instancia correspondientes y que un mensaje de instancia concreto solo debe expresar algunos datos mediante el formato especificado por el esquema.</span><span class="sxs-lookup"><span data-stu-id="31b8a-105">This is because the schema needs to describe all of the possible variations of the corresponding instance messages, and a specific instance message just needs to convey some data by using the format specified by the schema.</span></span> <span data-ttu-id="31b8a-106">El mensaje de instancia generado es una muestra y no puede mostrar todas las estructuras definidas por el esquema correspondiente.</span><span class="sxs-lookup"><span data-stu-id="31b8a-106">The generated instance message is a sample and may not show all of the structures defined by the corresponding schema.</span></span>  
  
### <a name="to-explicitly-specify-a-file-to-contain-the-generated-instance-message"></a><span data-ttu-id="31b8a-107">Para especificar de forma explícita que un archivo debe contener el mensaje de instancia generado</span><span class="sxs-lookup"><span data-stu-id="31b8a-107">To explicitly specify a file to contain the generated instance message</span></span>  
  
1.  <span data-ttu-id="31b8a-108">En el Explorador de soluciones, haga clic en el esquema para el que desea generar un mensaje de instancia y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="31b8a-108">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="31b8a-109">Si es necesario, en la ventana Propiedades, expanda el **General** sección de la **General** ficha haciendo clic en su signo más (+) icono.</span><span class="sxs-lookup"><span data-stu-id="31b8a-109">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="31b8a-110">En el **nombre de archivo de instancia de salida** campo de valor de propiedad, escriba el nombre de un archivo o utilice el botón de puntos suspensivos (**...** ) situado en el extremo derecho del campo de valor para buscar un archivo en el que se colocarán los mensajes de instancia generado y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="31b8a-110">In the **Output Instance Filename** property value field, either type the name of a file or use the ellipsis (**...**) button at the right end of the value field to browse for a file into which generated instance messages will be placed, and then click **Save**.</span></span>  
  
### <a name="to-specify-the-type-of-the-generated-instance-message"></a><span data-ttu-id="31b8a-111">Para especificar el tipo del mensaje de instancia generado</span><span class="sxs-lookup"><span data-stu-id="31b8a-111">To specify the type of the generated instance message</span></span>  
  
1.  <span data-ttu-id="31b8a-112">En el Explorador de soluciones, haga clic en el esquema para el que desea generar un mensaje de instancia y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="31b8a-112">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="31b8a-113">Si es necesario, en la ventana Propiedades, expanda el **General** sección de la **General** ficha haciendo clic en su signo más (+) icono.</span><span class="sxs-lookup"><span data-stu-id="31b8a-113">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="31b8a-114">En el **genere el tipo de salida de instancia** campo de valor de propiedad, use la lista desplegable lista para seleccionar **XML** o **nativo** como el tipo del que se genere el mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="31b8a-114">In the **Generate Instance Output Type** property value field, use the drop-down list to select either **XML** or **Native** as the type of the instance message to be generated.</span></span>  
  
     <span data-ttu-id="31b8a-115">**XML** es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="31b8a-115">**XML** is the default value.</span></span>  
  
### <a name="to-generate-a-sample-instance-message-for-a-schema"></a><span data-ttu-id="31b8a-116">Para generar un mensaje de instancia de ejemplo para un esquema</span><span class="sxs-lookup"><span data-stu-id="31b8a-116">To generate a sample instance message for a schema</span></span>  
  
1.  <span data-ttu-id="31b8a-117">En el Explorador de soluciones, haga clic en el esquema para el que desea generar un mensaje de instancia y, a continuación, haga clic en **generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="31b8a-117">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Generate Instance**.</span></span>  
  
2.  <span data-ttu-id="31b8a-118">En la ventana Resultados, vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="31b8a-118">In the Output window, view the results.</span></span> <span data-ttu-id="31b8a-119">En esta ventana se muestran mensajes para indicar si la operación ha sido correcta o no.</span><span class="sxs-lookup"><span data-stu-id="31b8a-119">Success and error messages are displayed in this window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31b8a-120">Si la ventana Resultados o la ventana Lista de tareas no se abre ni muestra información acerca de si la generación de la instancia se ha realizado correctamente o no, puede abrirla manualmente.</span><span class="sxs-lookup"><span data-stu-id="31b8a-120">If the Output window and/or the Task List window did not open and display information about whether the instance generation succeeded or failed, you can open them manually.</span></span> <span data-ttu-id="31b8a-121">Para obtener más información acerca de cómo administrar estas ventanas, vea [administrar otras ventanas de Visual Studio](../core/how-to-manage-other-visual-studio-windows.md).</span><span class="sxs-lookup"><span data-stu-id="31b8a-121">For more information about managing these windows, see [Managing Other Visual Studio Windows](../core/how-to-manage-other-visual-studio-windows.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31b8a-122">Si no especifica un valor para el **referencia raíz** propiedad, el Editor de BizTalk genera un mensaje de instancia de ejemplo para el primer nodo raíz del esquema.</span><span class="sxs-lookup"><span data-stu-id="31b8a-122">If you do not specify a value for the **Root Reference** property, BizTalk Editor generates a sample instance message for the first root node in the schema.</span></span> <span data-ttu-id="31b8a-123">Si especifica un valor para el **referencia raíz** propiedad, el Editor de BizTalk genera un mensaje de instancia de ejemplo para ese nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="31b8a-123">If you specify a value for the **Root Reference** property, BizTalk Editor generates a sample instance message for that root.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31b8a-124">En algunos casos, los mensajes de instancia generados desde un esquema concreto no pueden pasar la validación con ese mismo esquema.</span><span class="sxs-lookup"><span data-stu-id="31b8a-124">There are some cases instance messages generated from a particular schema may not pass validation with that same schema.</span></span> <span data-ttu-id="31b8a-125">Para obtener más información acerca de estos casos, consulte [problemas conocidos relacionados con la validación y generación de esquema](../core/known-issues-with-schema-generation-and-validation.md).</span><span class="sxs-lookup"><span data-stu-id="31b8a-125">For more information about such cases, see [Known Issues with Schema Generation and Validation](../core/known-issues-with-schema-generation-and-validation.md).</span></span> <span data-ttu-id="31b8a-126">En general, es conveniente editar un mensaje de instancia generado y cambiar los datos que contiene para que represente el escenario más realista.</span><span class="sxs-lookup"><span data-stu-id="31b8a-126">Generally, you want to edit a generated instance message and change the data it contains so that it more realistically represents your scenario.</span></span> <span data-ttu-id="31b8a-127">A continuación, use ese mensaje de instancia modificado para validar el esquema.</span><span class="sxs-lookup"><span data-stu-id="31b8a-127">Then use this modified instance message to validate your schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b8a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="31b8a-128">See Also</span></span>  
 <span data-ttu-id="31b8a-129">[Comprobación de esquemas](../core/testing-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="31b8a-129">[Testing Schemas](../core/testing-schemas.md) </span></span>  
 <span data-ttu-id="31b8a-130">[Validación de esquemas](../core/schema-validation1.md) </span><span class="sxs-lookup"><span data-stu-id="31b8a-130">[Schema Validation](../core/schema-validation1.md) </span></span>  
 [<span data-ttu-id="31b8a-131">Validación y generación de mensajes de instancia</span><span class="sxs-lookup"><span data-stu-id="31b8a-131">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)