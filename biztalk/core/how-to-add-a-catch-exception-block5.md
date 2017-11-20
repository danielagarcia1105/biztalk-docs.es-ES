---
title: "Cómo agregar un Block5 de excepción Catch | Documentos de Microsoft"
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
ms.assetid: 4875060c-976c-40e7-830a-ffd1a47ba68a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c045677fb2d177377725a3f11e81a5c5c70f9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="12d80-102">Cómo agregar un bloque Excepción de filtrado</span><span class="sxs-lookup"><span data-stu-id="12d80-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="12d80-103">Para agregar una **excepción de filtrado** bloquear a un **ámbito** forma, el **tipo de transacción** propiedad de la **ámbito** forma debe establecerse en **Ninguno** o **de larga ejecución**.</span><span class="sxs-lookup"><span data-stu-id="12d80-103">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-a-catch-exception-block"></a><span data-ttu-id="12d80-104">Procedimiento para agregar un bloque Excepción de filtrado</span><span class="sxs-lookup"><span data-stu-id="12d80-104">To add a catch exception block</span></span>  
  
1.  <span data-ttu-id="12d80-105">Haga clic en el **ámbito** forma y, a continuación, haga clic en **nuevo controlador de excepción**.</span><span class="sxs-lookup"><span data-stu-id="12d80-105">Right-click the **Scope** shape, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="12d80-106">A **excepción de filtrado** bloque se agrega a la orquestación inmediatamente después asociado **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="12d80-106">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="12d80-107">En el **propiedades** ventana, especifique las propiedades.</span><span class="sxs-lookup"><span data-stu-id="12d80-107">In the **Properties** window, specify the properties.</span></span>  
  
     <span data-ttu-id="12d80-108">La propiedad más importante es la **tipo de objeto de excepción**; éste es el tipo de mensaje que filtrará.</span><span class="sxs-lookup"><span data-stu-id="12d80-108">The most important property is the **Exception Object Type**; this is the type of message it will catch.</span></span>  
  
    |<span data-ttu-id="12d80-109">Propiedad</span><span class="sxs-lookup"><span data-stu-id="12d80-109">Property</span></span>|<span data-ttu-id="12d80-110">Description</span><span class="sxs-lookup"><span data-stu-id="12d80-110">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="12d80-111">**Nombre del objeto de excepción**</span><span class="sxs-lookup"><span data-stu-id="12d80-111">**Exception Object Name**</span></span>|<span data-ttu-id="12d80-112">Asigna un nombre al objeto de excepción filtrado por el controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="12d80-112">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="12d80-113">**Tipo de objeto de excepción**</span><span class="sxs-lookup"><span data-stu-id="12d80-113">**Exception Object Type**</span></span>|<span data-ttu-id="12d80-114">Determina el tipo de objeto (procedente de System.Exception) que filtrará este controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="12d80-114">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="12d80-115">En el **propiedades** ventana, en la **tipo de objeto de excepción** lista, seleccione **excepción General**.</span><span class="sxs-lookup"><span data-stu-id="12d80-115">In the **Properties** window, in the **Exception Object Type** list, select **General Exception**.</span></span>  
  
4.  <span data-ttu-id="12d80-116">Dentro de la **excepción de filtrado** bloquear, agregue formas a fin de crear el proceso para controlar la excepción.</span><span class="sxs-lookup"><span data-stu-id="12d80-116">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="12d80-117">Menú contextual que aparece a continuación el **CatchException** y seleccione **Insertar forma**y, a continuación, seleccione **construir mensaje**.</span><span class="sxs-lookup"><span data-stu-id="12d80-117">Right-click below the **CatchException** and point to **Insert Shape**, and then select **Construct Message**.</span></span>  
  
    2.  <span data-ttu-id="12d80-118">Haga doble clic en **MessageAssignment** para abrir el Editor de texto y escriba la asignación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="12d80-118">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="12d80-119">Por ejemplo, escriba `Message_3 = Test`.</span><span class="sxs-lookup"><span data-stu-id="12d80-119">For example, type `Message_3 = Test`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d80-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="12d80-120">See Also</span></span>  
 <span data-ttu-id="12d80-121">[Completar el mensaje de excepción](../core/completing-the-exception-message1.md) </span><span class="sxs-lookup"><span data-stu-id="12d80-121">[Completing the Exception Message](../core/completing-the-exception-message1.md) </span></span>  
 <span data-ttu-id="12d80-122">[Cómo agregar una forma ámbito](../core/how-to-add-a-scope-shape5.md) </span><span class="sxs-lookup"><span data-stu-id="12d80-122">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape5.md) </span></span>  
 [<span data-ttu-id="12d80-123">Uso de control de excepciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="12d80-123">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling5.md)