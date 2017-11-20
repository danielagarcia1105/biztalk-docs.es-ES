---
title: Tipos de correlaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- correlation sets, correlation types
- correlation types, correlation sets
- correlation types
- validating, correlation types
- correlation types, about correlation types
- correlation types, validating
ms.assetid: 1aa5ca5c-c37d-4091-9f5d-331a6b202d4e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3da5fad8cb4edc1d6a528f481616b4f10efb71d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="correlation-types"></a><span data-ttu-id="07444-102">Tipos de correlación</span><span class="sxs-lookup"><span data-stu-id="07444-102">Correlation Types</span></span>
<span data-ttu-id="07444-103">Cada conjunto de correlaciones se basa en un **tipo de correlación**, que es simplemente una lista de propiedades.</span><span class="sxs-lookup"><span data-stu-id="07444-103">Each correlation set is based on a **correlation type**, which is simply a list of properties.</span></span> <span data-ttu-id="07444-104">Éstas pueden ser propiedades de datos, que se encuentran en el propio mensaje, o propiedades de contexto, que describen detalles del sistema o de mensajes no relacionados con los datos transmitidos en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="07444-104">These properties might be data properties, which are found in the message itself, or context properties, which describe details of the system or messages that are unrelated to the data being conveyed in the message.</span></span>  
  
 <span data-ttu-id="07444-105">Puede usar un tipo de correlación en más de un conjunto de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="07444-105">You can use a correlation type in more than one correlation set.</span></span> <span data-ttu-id="07444-106">Si necesita establecer correlaciones entre distintos valores de las propiedades de un tipo de correlación, debe crear un nuevo conjunto de correlación, se puede inicializar una sola vez cada conjunto de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="07444-106">If you need to correlate on different values for the properties in a correlation type, you must create a new correlation set—each correlation set can be initialized only once.</span></span>  
  
 <span data-ttu-id="07444-107">Puede promocionar las propiedades de un esquema de propiedades para declarar que algunas de las propiedades de un mensaje están accesibles para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="07444-107">You can promote properties in a property schema to declare that certain properties in a message are accessible to your orchestration.</span></span> <span data-ttu-id="07444-108">Para obtener más información, consulte [promocionar propiedades](../core/promoting-properties.md).</span><span class="sxs-lookup"><span data-stu-id="07444-108">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="07444-109">No establezca la propiedad definida por el sistema **BTS. CorrelationToken** que está asociado a cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="07444-109">Do not set the system-defined property **BTS.CorrelationToken** that is associated with each message.</span></span> <span data-ttu-id="07444-110">El motor la usa en la correlación de mensajes y establecerla podría dar lugar a la pérdida de mensajes en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="07444-110">This is used by the engine in correlating messages, and setting it could result in your orchestration losing messages.</span></span>  
  
## <a name="validating-message-correlation-on-send-actions"></a><span data-ttu-id="07444-111">Validar la correlación de mensajes en las acciones de envío</span><span class="sxs-lookup"><span data-stu-id="07444-111">Validating Message Correlation on Send Actions</span></span>  
 <span data-ttu-id="07444-112">Puede validar las propiedades de un mensaje enviado desde la orquestación a fin de asegurarse de que refleje las propiedades de su conjunto de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="07444-112">You can validate the properties of a message that you send from your orchestration to ensure that it reflects the properties in its correlation set.</span></span> <span data-ttu-id="07444-113">De manera predeterminada, esta validación está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="07444-113">By default, this validation is disabled.</span></span> <span data-ttu-id="07444-114">Para obtener información sobre cómo habilitarlo, consulte [validación en tiempo de ejecución para el motor de orquestaciones](../core/runtime-validation-for-the-orchestration-engine.md).</span><span class="sxs-lookup"><span data-stu-id="07444-114">For information on how to enable it, see [Runtime Validation for the Orchestration Engine](../core/runtime-validation-for-the-orchestration-engine.md).</span></span>