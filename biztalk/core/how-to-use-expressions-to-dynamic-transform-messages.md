---
title: "Cómo usar expresiones para transformar dinámica mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48387d97-9312-4df5-b614-727ea9035bf8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9d16c38fefb4e2732bd05f7c3489acaa8ca645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expressions-to-dynamic-transform-messages"></a><span data-ttu-id="d6931-102">Cómo usar expresiones para transformar mensajes de forma dinámica</span><span class="sxs-lookup"><span data-stu-id="d6931-102">How to Use Expressions to Dynamic Transform Messages</span></span>
<span data-ttu-id="d6931-103">En la orquestación, puede usar expresiones para transformar mensajes de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="d6931-103">You can use expressions to dynamic transform messages in your orchestration.</span></span> <span data-ttu-id="d6931-104">XLANG expone un método de transformación que se pueda llamar desde una **asignación de mensajes** forma dentro de un **construir mensaje** forma.</span><span class="sxs-lookup"><span data-stu-id="d6931-104">XLANG exposes a transform method that can be called from within a **Message Assignment** shape inside of a **Construct Message** shape.</span></span> <span data-ttu-id="d6931-105">Este es el mismo método que se llama cuando un **transformar** forma se utiliza, pero permite transformar mediante programación los mensajes mediante la asignación designada en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="d6931-105">This is the same method that is called when a **Transform** shape is used, but allows you to programmatically transform the messages using the map you designated within the orchestration.</span></span> <span data-ttu-id="d6931-106">Esto resulta útil en los procesamientos de mensajes de tipo independiente.</span><span class="sxs-lookup"><span data-stu-id="d6931-106">This is useful when you are doing type-agnostic message processing.</span></span> <span data-ttu-id="d6931-107">Por ejemplo, si tiene un proceso empresarial que necesita elegir entre una serie de asignaciones para transformar mensajes entrantes según los parámetros que los mensajes entrantes recibidos proporcionaron, puede conseguirlo mediante el uso del método de transformación en la forma Expresión mientras mantiene intacto su proceso empresarial general.</span><span class="sxs-lookup"><span data-stu-id="d6931-107">For example, if you have a business process that needs to choose from a series of maps to transform inbound messages based on the parameters provided by the received inbound messages, you can achieve this by using the transform method in the Expression shape while maintaining your overall business process intact.</span></span>  
  
## <a name="transforming-messages"></a><span data-ttu-id="d6931-108">Transformar mensajes</span><span class="sxs-lookup"><span data-stu-id="d6931-108">Transforming messages</span></span>  
 <span data-ttu-id="d6931-109">Puede usar el siguiente código de ejemplo para transformar mediante programación los mensajes en el **asignación de mensajes** forma:</span><span class="sxs-lookup"><span data-stu-id="d6931-109">You can use the following sample code to programmatically transform the messages in the **Message Assignment** shape:</span></span>  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg);  
```  
  
 <span data-ttu-id="d6931-110">En este ejemplo, MyMapType se declara como una variable de tipo **System.Type** en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="d6931-110">In this example, MyMapType is declared as a variable of type **System.Type** in the orchestration.</span></span> <span data-ttu-id="d6931-111">MyMapName es el nombre de una asignación ya creada en el proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d6931-111">MyMapName is the name of a map that was already created in your BizTalk project.</span></span> <span data-ttu-id="d6931-112">Si desea hacer referencia a una asignación que se encuentre en un ensamblado de BizTalk diferente, tendrá que hacer referencia a ese ensamblado en el proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d6931-112">If you would like to reference a map that is in a separate BizTalk assembly, you will need to reference that assembly in your BizTalk project.</span></span> <span data-ttu-id="d6931-113">MyInputMsg es el mensaje de origen y MyOutputMsg es el mensaje de destino.</span><span class="sxs-lookup"><span data-stu-id="d6931-113">MyInputMsg is the source message and MyOutputMsg is the destination message.</span></span> <span data-ttu-id="d6931-114">Si la asignación toma varios mensajes de origen, puede usar el siguiente código de ejemplo para transformar los mensajes:</span><span class="sxs-lookup"><span data-stu-id="d6931-114">If your map takes multiple source messages, then you can use the following sample code to transform the messages:</span></span>  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg1, MyInputMsg2);  
```  
  
> [!NOTE]
>  <span data-ttu-id="d6931-115">Si tiene varios mensajes de origen, deben estar colocados en orden en la expresión en relación al número de parte del mensaje de entrada que se indica en la asignación.</span><span class="sxs-lookup"><span data-stu-id="d6931-115">If you have multiple source messages, they must be placed in order in the expression with respect to the input message part number indicated in the map.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d6931-116">Cuando se transforman mensajes de forma dinámica en la forma Expresión, se recomienda escribir una caché en el código de usuario para almacenar las asignaciones compiladas y, después, usarla en la forma Expresión para recuperar las asignaciones antes de realizar la transformación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d6931-116">When dynamic transforming messages in the Expression shape, we recommend that you write a cache in user code for caching the compiled maps, and then use the cache in the Expression shape to retrieve the maps before performing the message transformation.</span></span> <span data-ttu-id="d6931-117">Si no almacena en caché las asignaciones, existe la posibilidad de que la memoria de Common Language Runtime (CLR) aumente de forma significativa.</span><span class="sxs-lookup"><span data-stu-id="d6931-117">If you are not caching the maps, it is possible to see Common Language Runtime (CLR) memory grow significantly.</span></span> <span data-ttu-id="d6931-118">La asignación dinámica requiere que el motor de tiempo de ejecución de .NET realice comprobaciones de acceso al código que de origen a un objeto de evidencia de .NET se coloque en el montón del objeto grande para cada transformación y a que este objeto no se elimine hasta que la orquestación finalice.</span><span class="sxs-lookup"><span data-stu-id="d6931-118">Dynamic mapping requires that the .NET Runtime perform code access check which results in a .NET Evidence object being placed in the Large Object Heap for each transformation and this object is not disposed of until the orchestration completes.</span></span> <span data-ttu-id="d6931-119">Por tanto, cuando se suceden muchos de estos tipos de transformaciones de forma simultánea, puede ver que el uso de memoria aumenta significativamente lo que puede provocar también una excepción de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="d6931-119">Therefore, when there are a lot of these types of transforms occurring simultaneously, you may see the memory usage increase substantially which can also lead to the out of memory exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6931-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6931-120">See Also</span></span>  
 <span data-ttu-id="d6931-121">[Formas de orquestación](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="d6931-121">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 [<span data-ttu-id="d6931-122">Crear asignaciones usando al asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d6931-122">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)