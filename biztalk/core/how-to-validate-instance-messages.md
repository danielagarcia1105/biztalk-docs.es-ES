---
title: Cómo validar los mensajes de instancia | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f6302c6-b56b-4572-aa76-0f4c4599672a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd0baa898f801c924cffc5a446aa1a22d063a8fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256796"
---
# <a name="how-to-validate-instance-messages"></a><span data-ttu-id="a0454-102">Cómo validar los mensajes de instancia</span><span class="sxs-lookup"><span data-stu-id="a0454-102">How to Validate Instance Messages</span></span>
<span data-ttu-id="a0454-103">Una vez construido un esquema, puede comprobarlo si valida un mensaje de instancia existente que sepa que representa correctamente a esos mensajes de instancia con respecto al esquema.</span><span class="sxs-lookup"><span data-stu-id="a0454-103">After you have constructed a schema, you can check your work by validating a pre-existing instance message that you know is a good representation of such instance messages against the schema.</span></span>  
  
 <span data-ttu-id="a0454-104">Este tema proporciona instrucciones paso a paso para esta tarea de validación.</span><span class="sxs-lookup"><span data-stu-id="a0454-104">This topic provides step-by-step instructions for this validation task.</span></span>  
  
### <a name="to-validate-an-instance-message-against-a-schema"></a><span data-ttu-id="a0454-105">Para validar un mensaje de instancia con respecto a un esquema</span><span class="sxs-lookup"><span data-stu-id="a0454-105">To validate an instance message against a schema</span></span>  
  
1.  <span data-ttu-id="a0454-106">En el Explorador de soluciones, haga clic en el esquema y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a0454-106">In Solution Explorer, right-click the schema, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a0454-107">Si es necesario, en la ventana Propiedades, expanda el **General** sección de la **General** ficha haciendo clic en su signo más (+) icono.</span><span class="sxs-lookup"><span data-stu-id="a0454-107">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="a0454-108">En el **nombre de archivo de instancia de entrada** campo de valor de propiedad, escriba el nombre de un archivo o utilice el botón de puntos suspensivos (**...** ) situado en el extremo derecho del campo de valor para buscar un archivo que contiene el mensaje de instancia que se valida con el esquema y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="a0454-108">In the **Input Instance Filename** property value field, either type the name of a file or use the ellipsis (**...**) button at the right end of the value field to browse for a file that contains the instance message to be validated against the schema, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="a0454-109">En **el Explorador de soluciones**, haga clic en el nombre de esquema y, a continuación, haga clic en **Validar instancia**.</span><span class="sxs-lookup"><span data-stu-id="a0454-109">In **Solution Explorer**, right-click the schema name, and then click **Validate Instance**.</span></span>  
  
5.  <span data-ttu-id="a0454-110">En la ventana Resultados, vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="a0454-110">In the Output window, view the results.</span></span> <span data-ttu-id="a0454-111">En esta ventana se muestran mensajes para indicar si la operación ha sido correcta o no.</span><span class="sxs-lookup"><span data-stu-id="a0454-111">Success and error messages are displayed in this window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0454-112">En algunos casos, los mensajes de instancia generados desde un esquema concreto no pueden pasar la validación con ese mismo esquema.</span><span class="sxs-lookup"><span data-stu-id="a0454-112">There are some cases instance messages generated from a particular schema may not pass validation with that same schema.</span></span> <span data-ttu-id="a0454-113">Para obtener más información acerca de estos casos, consulte [problemas conocidos relacionados con la validación y generación de esquema](../core/known-issues-with-schema-generation-and-validation.md).</span><span class="sxs-lookup"><span data-stu-id="a0454-113">For more information about such cases, see [Known Issues with Schema Generation and Validation](../core/known-issues-with-schema-generation-and-validation.md).</span></span> <span data-ttu-id="a0454-114">Normalmente, deseará editar un mensaje de instancia generado y cambiar los datos que contiene para que represente de una forma más real su situación.</span><span class="sxs-lookup"><span data-stu-id="a0454-114">Generally, you will want to edit a generated instance message and change the data it contains so that it more realistically represents your scenario.</span></span> <span data-ttu-id="a0454-115">A continuación, use ese mensaje de instancia modificado para validar el esquema.</span><span class="sxs-lookup"><span data-stu-id="a0454-115">Then use this modified instance message to validate your schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0454-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0454-116">See Also</span></span>  
 <span data-ttu-id="a0454-117">[Comprobación de esquemas](../core/testing-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="a0454-117">[Testing Schemas](../core/testing-schemas.md) </span></span>  
 <span data-ttu-id="a0454-118">[Validación de esquemas](../core/schema-validation1.md) </span><span class="sxs-lookup"><span data-stu-id="a0454-118">[Schema Validation](../core/schema-validation1.md) </span></span>  
 [<span data-ttu-id="a0454-119">Validación y generación de mensajes de instancia</span><span class="sxs-lookup"><span data-stu-id="a0454-119">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)