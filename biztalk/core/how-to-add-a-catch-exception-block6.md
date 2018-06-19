---
title: Cómo agregar un Block6 de excepción Catch | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exception handling, Catch Exception block
- Catch Exception blocks
- exceptions, Catch Exception block
ms.assetid: 404312dd-773b-44fe-8b65-7de3d0af2f79
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4be60ddbe45ef4b4f293d7959dc774254e7cd3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248724"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="67ee1-102">Cómo agregar un bloque Excepción de filtrado</span><span class="sxs-lookup"><span data-stu-id="67ee1-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="67ee1-103">El **excepción de filtrado** de bloqueo representa un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="67ee1-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="67ee1-104">**Detectar excepciones** bloques se adjuntan al final de un **ámbito** forma en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="67ee1-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="67ee1-105">En BizTalk Server, puede adjuntar tantos **excepción de filtrado** bloquea según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="67ee1-105">In BizTalk Server, you can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="67ee1-106">Puede configurar controladores de excepción para controlar los distintos tipos de excepciones.</span><span class="sxs-lookup"><span data-stu-id="67ee1-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="67ee1-107">En cada controlador de excepción, especifique un tipo de excepción, que puede ser un mensaje de error o un objeto derivado de la clase `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="67ee1-107">On each exception handler, you specify an exception type, which must be either a fault message or an object derived from the class `System.Exception`.</span></span> <span data-ttu-id="67ee1-108">Si no especifica ningún tipo de excepción, el bloque de excepción se tratará como un controlador de excepción general y podrá filtrar las excepciones que no procedan de `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="67ee1-108">If you do not specify an exception type, the exception block is treated as a general exception handler, and can catch exceptions that do not derive from `System.Exception`.</span></span>  
  
 <span data-ttu-id="67ee1-109">Si se origina una excepción que coincida con el tipo especificado en un controlador de excecpción, se llamará a este controlador.</span><span class="sxs-lookup"><span data-stu-id="67ee1-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler is called.</span></span> <span data-ttu-id="67ee1-110">Si se produce otra excepción, se controla por el controlador de excepción predeterminado.</span><span class="sxs-lookup"><span data-stu-id="67ee1-110">If some other exception is thrown, it is handled by the default exception handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67ee1-111">Para agregar una **excepción de filtrado** bloquear a un **ámbito** forma, el **tipo de transacción** propiedad de la **ámbito** forma debe establecerse en None o Long En ejecución.</span><span class="sxs-lookup"><span data-stu-id="67ee1-111">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to None or Long Running.</span></span>  
  
## <a name="adding-and-populating-a-catch-exception-block"></a><span data-ttu-id="67ee1-112">Agregar y rellenar un bloque Excepción de filtrado</span><span class="sxs-lookup"><span data-stu-id="67ee1-112">Adding and Populating a Catch Exception Block</span></span>  
  
#### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="67ee1-113">Para agregar y rellenar un bloque Excepción de filtrado</span><span class="sxs-lookup"><span data-stu-id="67ee1-113">To add and populate a catch exception block</span></span>  
  
1.  <span data-ttu-id="67ee1-114">Haga clic en el **ámbito** forma a la que desea agregar un **excepción de filtrado** bloquear a y, a continuación, haga clic en **nuevo controlador de excepción**.</span><span class="sxs-lookup"><span data-stu-id="67ee1-114">Right-click the **Scope** shape that you want to add a **Catch Exception** block to, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="67ee1-115">A **excepción de filtrado** bloque se agrega a la orquestación inmediatamente después asociado **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="67ee1-115">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="67ee1-116">En el **propiedades** ventana, especifique las propiedades.</span><span class="sxs-lookup"><span data-stu-id="67ee1-116">In the **Properties** window, specify the properties.</span></span> <span data-ttu-id="67ee1-117">La propiedad más importante es la **tipo de objeto de excepción** porque éste es el tipo de mensaje que filtrará.</span><span class="sxs-lookup"><span data-stu-id="67ee1-117">The most important property is the **Exception Object Type** because this is the type of message it will catch.</span></span>  
  
    |<span data-ttu-id="67ee1-118">Propiedad</span><span class="sxs-lookup"><span data-stu-id="67ee1-118">Property</span></span>|<span data-ttu-id="67ee1-119">Description</span><span class="sxs-lookup"><span data-stu-id="67ee1-119">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="67ee1-120">Nombre de objeto de excepción</span><span class="sxs-lookup"><span data-stu-id="67ee1-120">Exception Object Name</span></span>|<span data-ttu-id="67ee1-121">Asigna un nombre al objeto de excepción filtrado por el controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="67ee1-121">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="67ee1-122">Tipo de objeto de excepción</span><span class="sxs-lookup"><span data-stu-id="67ee1-122">Exception Object Type</span></span>|<span data-ttu-id="67ee1-123">Determina el tipo de objeto (procedente de System.Exception) que filtrará este controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="67ee1-123">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="67ee1-124">En el **propiedades** ventana, haga clic en el **tipo de objeto de excepción** lista.</span><span class="sxs-lookup"><span data-stu-id="67ee1-124">In the **Properties** window, click the **Exception Object Type** list.</span></span> <span data-ttu-id="67ee1-125">Esta lista contiene la excepción general que inicia el adaptador.</span><span class="sxs-lookup"><span data-stu-id="67ee1-125">This list contains the general exception that is thrown by the adapter.</span></span>  
  
     <span data-ttu-id="67ee1-126">El nombre aparecerá como el error establecido en el puerto al sistema de servidor, por ejemplo, PS.SQLExecute.Fault.</span><span class="sxs-lookup"><span data-stu-id="67ee1-126">The name appears as the fault you set in the port to the back-end system, for example, PS.SQLExecute.Fault.</span></span>  
  
4.  <span data-ttu-id="67ee1-127">Agregar un nombre para el **nombre de objeto de excepción**, por ejemplo, una prueba.</span><span class="sxs-lookup"><span data-stu-id="67ee1-127">Add a name for the **Exception Object Name**, for example, Test.</span></span>  
  
     <span data-ttu-id="67ee1-128">Dentro de la **excepción de filtrado** bloquear, agregue formas a fin de crear el proceso para controlar la excepción.</span><span class="sxs-lookup"><span data-stu-id="67ee1-128">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="67ee1-129">Menú contextual que aparece a continuación el **excepción de filtrado**, seleccione **Insertar forma**y seleccione **construir mensaje**.</span><span class="sxs-lookup"><span data-stu-id="67ee1-129">Right-click below the **Catch Exception**, point to **Insert Shape**, and select **Construct Message**.</span></span>  
  
         ![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")  
  
    2.  <span data-ttu-id="67ee1-130">Haga doble clic en **MessageAssignment** para abrir el Editor de texto y escriba la asignación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="67ee1-130">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="67ee1-131">Escriba el nombre que se establece en los **nombre de objeto de excepción** desde el **excepción de filtrado**y el nuevo mensaje creado para el error.</span><span class="sxs-lookup"><span data-stu-id="67ee1-131">Enter the name that you set in the **Exception Object Name** from the **Catch Exception**, and the new message you created for the fault.</span></span>  
  
         <span data-ttu-id="67ee1-132">Por ejemplo, escriba `Message_3 = Test`.</span><span class="sxs-lookup"><span data-stu-id="67ee1-132">For example, type `Message_3 = Test`.</span></span>  
  
         ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")  
  
## <a name="see-also"></a><span data-ttu-id="67ee1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="67ee1-133">See Also</span></span>  
 <span data-ttu-id="67ee1-134">[Cómo agregar una forma ámbito](../core/how-to-add-a-scope-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="67ee1-134">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape1.md) </span></span>  
 <span data-ttu-id="67ee1-135">[Completar el mensaje de excepción](../core/completing-the-exception-message3.md) </span><span class="sxs-lookup"><span data-stu-id="67ee1-135">[Completing the Exception Message](../core/completing-the-exception-message3.md) </span></span>  
 [<span data-ttu-id="67ee1-136">Uso de control de excepciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="67ee1-136">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)