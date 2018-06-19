---
title: Cómo agregar un Block2 de excepción Catch | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks
- exceptions, Catch Exception blocks
ms.assetid: 7c8b6024-e8dc-4417-83f9-bf4032644b91
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e48ce1e6f0646acdf63ed33582f382f1baed797
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246844"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="d905f-102">Cómo agregar un bloque Excepción de filtrado</span><span class="sxs-lookup"><span data-stu-id="d905f-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="d905f-103">El **excepción de filtrado** de bloqueo representa un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="d905f-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="d905f-104">**Detectar excepciones** bloques se adjuntan al final de un **ámbito** forma en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="d905f-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="d905f-105">Puede adjuntar tantos **excepción de filtrado** bloquea según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d905f-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="d905f-106">Puede configurar controladores de excepción para controlar los distintos tipos de excepciones.</span><span class="sxs-lookup"><span data-stu-id="d905f-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="d905f-107">En cada controlador de excepciones, debe especificar un tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="d905f-107">On each exception handler, you specify an exception type.</span></span> <span data-ttu-id="d905f-108">Debe ser una excepción o un objeto derivado de la clase `System`.</span><span class="sxs-lookup"><span data-stu-id="d905f-108">This must be either an exception or an object derived from the class `System`.</span></span> <span data-ttu-id="d905f-109">Si se origina una excepción que coincida con el tipo especificado en un controlador de excepción, se llamará a dicho controlador.</span><span class="sxs-lookup"><span data-stu-id="d905f-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d905f-110">Para agregar un bloque de excepción de filtrado a una forma ámbito, la propiedad de tipo de transacción de la forma ámbito debe establecerse en **ninguno** o **larga ejecución**.</span><span class="sxs-lookup"><span data-stu-id="d905f-110">To add a Catch Exception block to a Scope shape, the Transaction Type property of the Scope shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="d905f-111">Para agregar y rellenar un bloque de excepción de filtrado</span><span class="sxs-lookup"><span data-stu-id="d905f-111">To add and populate a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="d905f-112">Haga clic en el **ámbito** forma a la que desea agregar un **excepción de filtrado** bloquear y, a continuación, haga clic en **nuevo controlador de excepción**.</span><span class="sxs-lookup"><span data-stu-id="d905f-112">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="d905f-113">A **excepción de filtrado** bloque se agrega a la orquestación inmediatamente después asociado **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="d905f-113">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="d905f-114">En el **propiedades** ventana, especifique las propiedades.</span><span class="sxs-lookup"><span data-stu-id="d905f-114">In the **Properties** window, specify the properties.</span></span>  
  
     <span data-ttu-id="d905f-115">La propiedad más importante es la **tipo de objeto de excepción**; éste es el tipo de mensaje que filtrará.</span><span class="sxs-lookup"><span data-stu-id="d905f-115">The most important property is the **Exception Object Type**; this is the type of message it will catch.</span></span>  
  
3.  <span data-ttu-id="d905f-116">En el **propiedades** windows, en la **tipo de objeto de excepción** lista, seleccione **excepción General**.</span><span class="sxs-lookup"><span data-stu-id="d905f-116">In the **Properties** windows, in the **Exception Object Type** list, select  **General Exception**.</span></span>  
  
    |<span data-ttu-id="d905f-117">Propiedad</span><span class="sxs-lookup"><span data-stu-id="d905f-117">Property</span></span>|<span data-ttu-id="d905f-118">Description</span><span class="sxs-lookup"><span data-stu-id="d905f-118">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="d905f-119">**Nombre del objeto de excepción**</span><span class="sxs-lookup"><span data-stu-id="d905f-119">**Exception Object Name**</span></span>|<span data-ttu-id="d905f-120">Asigna un nombre al objeto de excepción filtrado por el controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="d905f-120">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="d905f-121">**Tipo de objeto de excepción**</span><span class="sxs-lookup"><span data-stu-id="d905f-121">**Exception Object Type**</span></span>|<span data-ttu-id="d905f-122">Determina el tipo de objeto (procedente de System.Exception) que filtrará este controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="d905f-122">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
4.  <span data-ttu-id="d905f-123">Dentro del bloque Excepción de filtrado, agregue formas a fin de crear el proceso para controlar la excepción.</span><span class="sxs-lookup"><span data-stu-id="d905f-123">Inside the Catch Exception block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="d905f-124">Menú contextual que aparece a continuación el **CatchException** y seleccione **Insertar forma**y, a continuación, seleccione **construir mensaje**.</span><span class="sxs-lookup"><span data-stu-id="d905f-124">Right-click below the **CatchException** and point to **Insert Shape**, and then select **Construct Message**.</span></span>  
  
    2.  <span data-ttu-id="d905f-125">Haga doble clic en **MessageAssignment** para abrir el Editor de texto y escriba la asignación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d905f-125">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="d905f-126">Por ejemplo, escriba `Message_3 = Test`.</span><span class="sxs-lookup"><span data-stu-id="d905f-126">For example, type `Message_3 = Test`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d905f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d905f-127">See Also</span></span>  
 <span data-ttu-id="d905f-128">[Completar el mensaje de excepción](../core/completing-the-exception-message4.md) </span><span class="sxs-lookup"><span data-stu-id="d905f-128">[Completing the Exception Message](../core/completing-the-exception-message4.md) </span></span>  
 <span data-ttu-id="d905f-129">[Cómo agregar una forma ámbito](../core/how-to-add-a-scope-shape4.md) </span><span class="sxs-lookup"><span data-stu-id="d905f-129">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape4.md) </span></span>  
 [<span data-ttu-id="d905f-130">Uso de control de excepciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d905f-130">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling4.md)