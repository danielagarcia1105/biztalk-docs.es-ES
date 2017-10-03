---
title: "Generación de esquema en el adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, generating
- writing, schemas
ms.assetid: 43b69383-bae0-401b-9620-d4302db799b2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d10d927e4ede59e716b3f9838c96bac8cd144a81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schema-generation-in-the-adapter"></a><span data-ttu-id="845f4-102">Generación de esquemas del adaptador</span><span class="sxs-lookup"><span data-stu-id="845f4-102">Schema Generation in the Adapter</span></span>
<span data-ttu-id="845f4-103">Un sistema TIBCO Rendezvous no incluye un repositorio de tipos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="845f4-103">A TIBCO Rendezvous system does not include a message types repository.</span></span> <span data-ttu-id="845f4-104">Todos los análisis y construcciones de mensajes se incluyen en el tipo de aplicación Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="845f4-104">All the message construction and parsing is buried at the Rendezvous application level.</span></span> <span data-ttu-id="845f4-105">Debido a esta limitación, el adaptador de Microsoft BizTalk para TIBCO Rendezvous no puede proporcionar capacidades de generación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="845f4-105">Because of this limitation, Microsoft BizTalk Adapter for TIBCO Rendezvous cannot provide schema-generation capabilities.</span></span>  
  
## <a name="writing-schemas"></a><span data-ttu-id="845f4-106">Esquemas de escritura</span><span class="sxs-lookup"><span data-stu-id="845f4-106">Writing Schemas</span></span>  
 <span data-ttu-id="845f4-107">Debe escribir un esquema y usar **Agregar elemento existente** en Visual Studio para importarlo para su uso en orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="845f4-107">You must write a schema and use **Add Existing Item** in Visual Studio to import it for use in orchestrations.</span></span> <span data-ttu-id="845f4-108">Los esquemas son muy importantes para las herramientas de desarrollo de BizTalk Server y para la integración en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="845f4-108">Schemas are very important for BizTalk Server development tools and for integration in Visual Studio.</span></span> <span data-ttu-id="845f4-109">Los programadores de BizTalk Server tienen la opción de proporcionar un esquema completo, minimalista o una versión intermedia.</span><span class="sxs-lookup"><span data-stu-id="845f4-109">BizTalk Server developers can choose to provide a complete schema, a minimalist schema, or a version somewhere in between.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="845f4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="845f4-110">See Also</span></span>  
 [<span data-ttu-id="845f4-111">Introducción</span><span class="sxs-lookup"><span data-stu-id="845f4-111">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)