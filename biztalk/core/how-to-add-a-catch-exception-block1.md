---
title: "Cómo agregar un 1 de excepción Catch | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, adding Catch Exception block
- Catch Exception blocks, adding
- exception handling, Catch Exception blocks
ms.assetid: 8e4b264b-b3b0-4d83-81df-a14dc2ddeea2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7922a1527e0f6359427be992c4cc9963f8c7d93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="3d747-102">Cómo agregar un bloque Excepción de filtrado</span><span class="sxs-lookup"><span data-stu-id="3d747-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="3d747-103">El **excepción de filtrado** de bloqueo representa un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="3d747-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="3d747-104">**Detectar excepciones** bloques se adjuntan al final de un **ámbito** forma en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="3d747-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="3d747-105">Puede adjuntar tantos **excepción de filtrado** bloquea según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3d747-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="3d747-106">Puede configurar controladores de excepción para controlar los distintos tipos de excepciones.</span><span class="sxs-lookup"><span data-stu-id="3d747-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="3d747-107">En cada controlador de excepción, especifique un tipo de excepción, que puede ser una excepción o un objeto derivado de la clase `System`.</span><span class="sxs-lookup"><span data-stu-id="3d747-107">On each exception handler, you specify an exception type, which must be either an exception or an object derived from the class `System`.</span></span> <span data-ttu-id="3d747-108">Si se origina una excepción que coincida con el tipo especificado en un controlador de excepción, se llamará a dicho controlador.</span><span class="sxs-lookup"><span data-stu-id="3d747-108">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d747-109">Para agregar una **excepción de filtrado** bloquear a un **ámbito** forma, la propiedad de tipo de transacción de la **ámbito** forma debe establecerse en **ninguno** o  **Larga ejecución**.</span><span class="sxs-lookup"><span data-stu-id="3d747-109">To add a **Catch Exception** block to a **Scope** shape, the Transaction Type property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="3d747-110">Para agregar y rellenar un bloque de excepción de filtrado</span><span class="sxs-lookup"><span data-stu-id="3d747-110">To add and populate a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="3d747-111">Haga clic en el **ámbito** forma a la que desea agregar un **excepción de filtrado** bloquear y, a continuación, haga clic en **nuevo controlador de excepción**.</span><span class="sxs-lookup"><span data-stu-id="3d747-111">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="3d747-112">A **excepción de filtrado** bloque se agrega a la orquestación inmediatamente después asociado **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="3d747-112">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="3d747-113">En el **propiedades** ventana, especifique las propiedades.</span><span class="sxs-lookup"><span data-stu-id="3d747-113">In the **Properties** window, specify the properties.</span></span>  
  
     <span data-ttu-id="3d747-114">La propiedad más importante es el Tipo de objeto de excepción, ya que es el tipo de mensaje que detectará.</span><span class="sxs-lookup"><span data-stu-id="3d747-114">The most important property is the Exception Object Type; this is the type of message it will catch.</span></span>  
  
    |<span data-ttu-id="3d747-115">Propiedad</span><span class="sxs-lookup"><span data-stu-id="3d747-115">Property</span></span>|<span data-ttu-id="3d747-116">Description</span><span class="sxs-lookup"><span data-stu-id="3d747-116">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="3d747-117">Nombre de objeto de excepción</span><span class="sxs-lookup"><span data-stu-id="3d747-117">Exception Object Name</span></span>|<span data-ttu-id="3d747-118">Asigna un nombre al objeto de excepción filtrado por el controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="3d747-118">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="3d747-119">Tipo de objeto de excepción</span><span class="sxs-lookup"><span data-stu-id="3d747-119">Exception Object Type</span></span>|<span data-ttu-id="3d747-120">Determina el tipo de objeto (procedente de System.Exception) que filtrará este controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="3d747-120">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="3d747-121">En el **propiedades** ventana, en la **tipo de objeto de excepción** lista, seleccione la **excepción General**.</span><span class="sxs-lookup"><span data-stu-id="3d747-121">In the **Properties** window, in the **Exception Object Type** list, select the **General Exception**.</span></span>  
  
4.  <span data-ttu-id="3d747-122">Dentro de la **excepción de filtrado** bloquear, agregue formas a fin de crear el proceso para controlar la excepción.</span><span class="sxs-lookup"><span data-stu-id="3d747-122">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
5.  <span data-ttu-id="3d747-123">Menú contextual que aparece a continuación el **excepción de filtrado** bloquear, seleccione **Insertar forma**y, a continuación, seleccione **construir mensaje**.</span><span class="sxs-lookup"><span data-stu-id="3d747-123">Right-click below the **Catch Exception** block, point to **Insert Shape**, and then select **Construct Message**.</span></span>  
  
6.  <span data-ttu-id="3d747-124">Haga doble clic en **MessageAssignment** para activar el Editor de texto y escriba la asignación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3d747-124">Double-click inside **MessageAssignment** to activate the Text Editor and enter the Message assignment.</span></span>  
  
     <span data-ttu-id="3d747-125">Por ejemplo, escriba `Message_3 = Test`.</span><span class="sxs-lookup"><span data-stu-id="3d747-125">For example, type `Message_3 = Test`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d747-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d747-126">See Also</span></span>  
 <span data-ttu-id="3d747-127">[Completar el mensaje de excepción](../core/completing-the-exception-message5.md) </span><span class="sxs-lookup"><span data-stu-id="3d747-127">[Completing the Exception Message](../core/completing-the-exception-message5.md) </span></span>  
 <span data-ttu-id="3d747-128">[Cómo agregar una forma ámbito](../core/how-to-add-a-scope-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="3d747-128">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape2.md) </span></span>  
 [<span data-ttu-id="3d747-129">Uso de control de excepciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3d747-129">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)