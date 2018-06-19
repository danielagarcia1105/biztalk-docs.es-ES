---
title: Seguimiento de eventos empresariales sincrónico | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 302c7918-bc62-46f1-a949-fbf94a7073e3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84223714e2e04cec6c079862693a09786cb19a7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277940"
---
# <a name="synchronous-business-event-tracking"></a><span data-ttu-id="c1cd9-102">Seguimiento sincrónico de eventos empresariales</span><span class="sxs-lookup"><span data-stu-id="c1cd9-102">Synchronous Business Event Tracking</span></span>
<span data-ttu-id="c1cd9-103">La manera más fácil de enviar datos de evento a BAM consiste en usar una instancia de la clase DirectEventStream.</span><span class="sxs-lookup"><span data-stu-id="c1cd9-103">The simplest way to send event data to BAM is to use an instance of the class DirectEventStream.</span></span> <span data-ttu-id="c1cd9-104">Esta clase guarda los datos de evento directamente en la base de datos de importación principal de BAM en el contexto de la transacción actual de la aplicación (si existe).</span><span class="sxs-lookup"><span data-stu-id="c1cd9-104">This class saves the event data directly into the BAM Primary Import Database in the context of the current transaction of the application (if present).</span></span>  
  
 <span data-ttu-id="c1cd9-105">Si se produce cualquier error durante esta operación, la llamada a método iniciará una excepción de nuevo en la aplicación que hace la llamada.</span><span class="sxs-lookup"><span data-stu-id="c1cd9-105">If any error happens during this operation, the method call will throw an exception back in the calling application.</span></span> <span data-ttu-id="c1cd9-106">Por ejemplo, esto sucederá si el nombre de un elemento que se pasa en UpdateActivity no coincide con la definición de actividad de BAM, o si aún no implementó la definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="c1cd9-106">This will happen for example if the name of an item passed in UpdateActivity mismatches the BAM Activity Definition, or you did not deploy the BAM Definition yet.</span></span> <span data-ttu-id="c1cd9-107">Esto permite que la aplicación que hace la llamada pueda filtrar y corregir cualquier error al guardar los datos de BAM, lo que da lugar a una administración más sencilla.</span><span class="sxs-lookup"><span data-stu-id="c1cd9-107">This allows the calling application to catch and recover from any errors when saving the BAM data, which results in much easier management later.</span></span>  
  
 <span data-ttu-id="c1cd9-108">Guardar los datos sincrónicamente podría tener un impacto en el rendimiento, ya que la aplicación que hace la llamada tiene que esperar hasta que BAM ejecute todos los desencadenadores y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="c1cd9-108">Saving the data synchronously might have a performance impact, because the calling application has to wait until BAM executes all stored procedures and triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1cd9-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1cd9-109">See Also</span></span>  
 [<span data-ttu-id="c1cd9-110">Seguimiento de eventos empresariales asíncronos</span><span class="sxs-lookup"><span data-stu-id="c1cd9-110">Asynchronous Business Event Tracking</span></span>](../core/asynchronous-business-event-tracking.md)