---
title: No se pudo mensajes y objetos ErrorCollection | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- failed messages, ErrorCollection objects
- ErrorCollection objects
ms.assetid: 8a2ff3b5-d7a0-4595-8b74-3133e9e3a821
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4f9fd17807d9bc1b92b1eae1ac75662843c8e17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993165"
---
# <a name="failed-messages-and-errorcollection-objects"></a><span data-ttu-id="7b7b9-102">Mensajes de error y objetos ErrorCollection</span><span class="sxs-lookup"><span data-stu-id="7b7b9-102">Failed Messages and ErrorCollection Objects</span></span>
<span data-ttu-id="7b7b9-103">Además de decoración de un mensaje con errores con propiedades promocionadas, Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] publica el mensaje error en la base de datos de cuadro de mensajes con un mensaje adicional *parte*, llamado **ErrorSegment**.</span><span class="sxs-lookup"><span data-stu-id="7b7b9-103">In addition to decorating a failed message with promoted properties, Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] publishes the failed message to the MessageBox database with an additional message *part*, called **ErrorSegment**.</span></span> <span data-ttu-id="7b7b9-104">Esta parte de error contiene XML que representa un **ErrorCollection** objeto.</span><span class="sxs-lookup"><span data-stu-id="7b7b9-104">This error part contains XML representing an **ErrorCollection** object.</span></span> <span data-ttu-id="7b7b9-105">El Desensamblador de A4SWIFT rellena el **ErrorCollection** objeto durante cada fase de procesamiento (análisis, validación de XML y la validación de motor de reglas de negocios (BRE)) de mensajes.</span><span class="sxs-lookup"><span data-stu-id="7b7b9-105">The A4SWIFT disassembler populates the **ErrorCollection** object during each stage of message processing (parsing, XML validation, and Business Rule Engine (BRE) validation).</span></span>  
  
 <span data-ttu-id="7b7b9-106">El **ErrorCollection** objeto es una colección de *objetos error*, cada uno de los cuales representa un error concreto o un error durante el procesamiento del mensaje.</span><span class="sxs-lookup"><span data-stu-id="7b7b9-106">The **ErrorCollection** object is a collection of *error objects*, each of which represents a particular error or failure during message processing.</span></span> <span data-ttu-id="7b7b9-107">Los objetos individuales de error contienen detalles acerca de un único error (por ejemplo, la ubicación en el mensaje y una descripción del error).</span><span class="sxs-lookup"><span data-stu-id="7b7b9-107">The individual error objects contain details about a single failure (such as the location in the message and a description of the failure).</span></span>  
  
 <span data-ttu-id="7b7b9-108">Para obtener más información sobre la **ErrorCollection** programación de aplicaciones (API) de la interfaz y obtener detalles de uso, vea la clase ErrorCollection.</span><span class="sxs-lookup"><span data-stu-id="7b7b9-108">For more information about the **ErrorCollection** application programming interface (API) and usage details, see ErrorCollection Class.</span></span> <span data-ttu-id="7b7b9-109">Para obtener más información acerca de los objetos de errores individuales, consulte ErrorBase clase (la clase base para los objetos de error), clase BreValidationError, ParseError clase y clase XmlValidationError.</span><span class="sxs-lookup"><span data-stu-id="7b7b9-109">For more information about individual error objects, see ErrorBase Class (the base class for error objects), BreValidationError Class, ParseError Class, and XmlValidationError Class.</span></span>  
  
 <span data-ttu-id="7b7b9-110">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="7b7b9-110">This section contains:</span></span>  
  
-   [<span data-ttu-id="7b7b9-111">Ampliación de la solución para la captura y reparación de mensajes</span><span class="sxs-lookup"><span data-stu-id="7b7b9-111">Extending the Solution for Capture and Message Repair</span></span>](../../adapters-and-accelerators/accelerator-swift/extending-the-solution-for-capture-and-message-repair.md)