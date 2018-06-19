---
title: Cómo usar asignaciones en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfd628d8-c163-431d-8ad7-d7d77007c549
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e67249857ec00b2ca66648c1985f0c336d93b3b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255332"
---
# <a name="how-to-use-maps-in-orchestrations"></a><span data-ttu-id="b57de-102">Cómo usar asignaciones en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="b57de-102">How to Use Maps in Orchestrations</span></span>
<span data-ttu-id="b57de-103">El Asignador de BizTalk es una herramienta que se ejecuta en el entorno Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b57de-103">BizTalk Mapper is a tool that runs within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="b57de-104">El Asignador de BizTalk le permite crear y editar asignaciones en las que usará vínculos y functoids para definir la relación entre un esquema de origen y uno de destino mediante vínculos.</span><span class="sxs-lookup"><span data-stu-id="b57de-104">You use BizTalk Mapper to create and edit maps in which you use links and functoids to define the relationship between an input and an output schema.</span></span> <span data-ttu-id="b57de-105">Un vínculo define una copia de datos directa de un registro o campo.</span><span class="sxs-lookup"><span data-stu-id="b57de-105">A link defines a direct data copy of a record or field.</span></span> <span data-ttu-id="b57de-106">Los vínculos puede conectarse directamente con elementos del otro esquema, o pueden establecer conexiones con functoids.</span><span class="sxs-lookup"><span data-stu-id="b57de-106">Links may directly connect to items in the other schema, or they may form connections to functoids.</span></span> <span data-ttu-id="b57de-107">Los functoids llevan a cabo manipulaciones de datos más complejas.</span><span class="sxs-lookup"><span data-stu-id="b57de-107">Functoids perform more complex data manipulations.</span></span>  
  
## <a name="examples-of-using-maps"></a><span data-ttu-id="b57de-108">Ejemplos de uso de asignaciones</span><span class="sxs-lookup"><span data-stu-id="b57de-108">Examples of Using Maps</span></span>  
 <span data-ttu-id="b57de-109">Los siguientes ejemplos muestran varias formas de utilizar asignaciones:</span><span class="sxs-lookup"><span data-stu-id="b57de-109">The following samples show ways in which you can use maps:</span></span>  
  
-   [<span data-ttu-id="b57de-110">Herramientas XML (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b57de-110">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="b57de-111">PartyResolution (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b57de-111">PartyResolution (BizTalk Server Sample)</span></span>](../core/partyresolution-biztalk-server-sample.md)  
  
-   <span data-ttu-id="b57de-112">Descargue el ejemplo SDK "Usar el Functoid de copia masiva" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="b57de-112">Download the SDK sample "Using the Mass Copy Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="b57de-113">Descargue el ejemplo SDK "Usar el Functoid de bucle" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="b57de-113">Download the SDK sample "Using the Looping Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="b57de-114">Descargue el ejemplo SDK "Asignación de una repetición estructura" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="b57de-114">Download the SDK sample "Mapping to a Repeating Structure" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="b57de-115">Descargue el ejemplo SDK "Usar el Functoid de bucle de tabla" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="b57de-115">Download the SDK sample "Using the Table Looping Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="b57de-116">Descargue el ejemplo SDK "Mediante la asignación de valores y los Functoids de asignación (sin formato) de valor" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="b57de-116">Download the SDK sample "Using the Value Mapping and Value Mapping (Flattening) Functoids" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57de-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b57de-117">See Also</span></span>  
 <span data-ttu-id="b57de-118">[Crear asignaciones usando al asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="b57de-118">[Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md) </span></span>  
 <span data-ttu-id="b57de-119">[Construir mensajes](../core/constructing-messages.md) </span><span class="sxs-lookup"><span data-stu-id="b57de-119">[Constructing Messages](../core/constructing-messages.md) </span></span>  
 <span data-ttu-id="b57de-120">[Cómo configurar la forma transformación](../core/how-to-configure-the-transform-shape.md) </span><span class="sxs-lookup"><span data-stu-id="b57de-120">[How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md) </span></span>  
 [<span data-ttu-id="b57de-121">Cómo usar expresiones para transformar dinámica mensajes</span><span class="sxs-lookup"><span data-stu-id="b57de-121">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)