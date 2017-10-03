---
title: 'Tutorial: Usar el adaptador de BizTalk para JD Edwards OneWorld | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e13a648-7eaf-40c4-a71b-b66999087a69
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab54a0fe0f4a036e0045938951cf44337087853b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="c0da1-102">Tutorial: Usar el adaptador de BizTalk para JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="c0da1-102">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>
<span data-ttu-id="c0da1-103">A continuación se muestra el uso de propiedades de contexto de BizTalk para controlar la J.D.</span><span class="sxs-lookup"><span data-stu-id="c0da1-103">The following demonstrates using BizTalk Context Properties to control the J.D.</span></span> <span data-ttu-id="c0da1-104">Sesión de Edwards OneWorld en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="c0da1-104">Edwards OneWorld session in your orchestration.</span></span> <span data-ttu-id="c0da1-105">El tutorial se supone que dispone de una orquestación que envía llamadas BeginDoc, EditLine y EndDoc a un puerto de envío enlazado con el adaptador de Microsoft BizTalk para J.D.</span><span class="sxs-lookup"><span data-stu-id="c0da1-105">The tutorial assumes you have an orchestration that sends BeginDoc, EditLine and EndDoc calls to a send port bound to the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="c0da1-106">Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="c0da1-106">Edwards OneWorld.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0da1-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c0da1-107">In This Section</span></span>  
  
-   [<span data-ttu-id="c0da1-108">Paso 1: Hacer referencia al esquema DLL</span><span class="sxs-lookup"><span data-stu-id="c0da1-108">Step 1: Reference the Schema DLL</span></span>](../core/step-1-reference-the-schema-dll2.md)  
  
-   [<span data-ttu-id="c0da1-109">Paso 2: Crear la orquestación</span><span class="sxs-lookup"><span data-stu-id="c0da1-109">Step 2: Create the Orchestration</span></span>](../core/step-2-create-the-orchestration1.md)  
  
-   [<span data-ttu-id="c0da1-110">Paso 3: Completar y ejecutar el proyecto</span><span class="sxs-lookup"><span data-stu-id="c0da1-110">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project2.md)  
  
-   [<span data-ttu-id="c0da1-111">Paso 4: Crear un XML de ejemplo de BeginDoc</span><span class="sxs-lookup"><span data-stu-id="c0da1-111">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc1.md)