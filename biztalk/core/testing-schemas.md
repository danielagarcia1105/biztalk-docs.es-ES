---
title: Comprobación de esquemas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2e28b7c-9d0c-4336-8bee-4599d41a57f4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20879925ff98d5c5d6ca7d0c9ebcf11853239bba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279588"
---
# <a name="testing-schemas"></a><span data-ttu-id="2d07a-102">Comprobación de esquemas</span><span class="sxs-lookup"><span data-stu-id="2d07a-102">Testing Schemas</span></span>
<span data-ttu-id="2d07a-103">Una vez creado un esquema, es probable que desee validar que éste describe la estructura XML que pretende describir.</span><span class="sxs-lookup"><span data-stu-id="2d07a-103">After you have created your schema, you may want to validate that it describes the XML structure you intend it to describe.</span></span> <span data-ttu-id="2d07a-104">Puede realizar las tres operaciones siguientes en el esquema para validarlo:</span><span class="sxs-lookup"><span data-stu-id="2d07a-104">You can perform the following three operations on your schema to validate it:</span></span>  
  
-   <span data-ttu-id="2d07a-105">**Generación de instancia**.</span><span class="sxs-lookup"><span data-stu-id="2d07a-105">**Instance generation**.</span></span> <span data-ttu-id="2d07a-106">esta operación genera un mensaje de instancia a partir de un esquema y crea los datos de prueba que se acompañan a los elementos y atributos XML especificados por el esquema.</span><span class="sxs-lookup"><span data-stu-id="2d07a-106">This operation generates an instance message from a schema, creating test data to accompany the XML elements and attributes specified by the schema.</span></span>  
  
-   <span data-ttu-id="2d07a-107">**La validación del esquema**.</span><span class="sxs-lookup"><span data-stu-id="2d07a-107">**Schema validation**.</span></span> <span data-ttu-id="2d07a-108">esta operación valida la coherencia interna de un esquema y garantiza que se ajusta al estándar de esquema del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="2d07a-108">This operation validates the internal consistency of a schema, assuring that it conforms to the XML Schema definition (XSD) language schema standard.</span></span>  
  
-   <span data-ttu-id="2d07a-109">**Validación de instancia**.</span><span class="sxs-lookup"><span data-stu-id="2d07a-109">**Instance validation**.</span></span> <span data-ttu-id="2d07a-110">esta operación valida un determinado mensaje de instancia con respecto a un esquema.</span><span class="sxs-lookup"><span data-stu-id="2d07a-110">This operation validates a given instance message against a schema.</span></span>  
  
 <span data-ttu-id="2d07a-111">Las tres operaciones son útiles para probar los esquemas antes de colocarlos en un entorno de producción para su uso.</span><span class="sxs-lookup"><span data-stu-id="2d07a-111">All three of these operations are useful for testing your schemas before putting them into use in a production environment.</span></span>  
  
 <span data-ttu-id="2d07a-112">Esta sección describe estas operaciones con mayor detalle.</span><span class="sxs-lookup"><span data-stu-id="2d07a-112">This section describes these operations in greater detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d07a-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2d07a-113">In This Section</span></span>  
  
-   [<span data-ttu-id="2d07a-114">Cómo validar esquemas en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2d07a-114">How to Validate Schemas in Visual Studio</span></span>](../core/how-to-validate-schemas-in-visual-studio.md)  
  
-   [<span data-ttu-id="2d07a-115">Cómo validar los mensajes de instancia</span><span class="sxs-lookup"><span data-stu-id="2d07a-115">How to Validate Instance Messages</span></span>](../core/how-to-validate-instance-messages.md)  
  
-   [<span data-ttu-id="2d07a-116">Cómo generar mensajes de instancia</span><span class="sxs-lookup"><span data-stu-id="2d07a-116">How to Generate Instance Messages</span></span>](../core/how-to-generate-instance-messages.md)