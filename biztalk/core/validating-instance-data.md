---
title: Validar datos de instancia | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19c3ca83-0abf-42ba-8e29-653ff12d5e20
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86cde9d6133959e34ec09880be8a6beca5c37191
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="validate-instance-data"></a><span data-ttu-id="88138-102">Validar datos de instancia</span><span class="sxs-lookup"><span data-stu-id="88138-102">Validate Instance Data</span></span>

## <a name="overview"></a><span data-ttu-id="88138-103">Información general</span><span class="sxs-lookup"><span data-stu-id="88138-103">Overview</span></span>
<span data-ttu-id="88138-104">Durante el proceso de prueba de una asignación, quizá desee validar los datos de instancia con respecto a los esquemas de origen y destino para comprobar que esos datos de instancia se ajustan a la estructura del esquema.</span><span class="sxs-lookup"><span data-stu-id="88138-104">During the process of testing a map, you may want to validate instance data against the source and destination schemas to verify that the instance data adheres to the schema structure.</span></span> <span data-ttu-id="88138-105">Para validar un mensaje de instancia con respecto al esquema de origen o destino, haga clic en el esquema en el Explorador de soluciones y, a continuación, haga clic en **Validar instancia**.</span><span class="sxs-lookup"><span data-stu-id="88138-105">To validate an instance message against the source or destination schema, right-click the schema in the Solution Explorer, and then click **Validate Instance**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="88138-106">Si en la salida utiliza constantes o datos personalizados, debe comprobar que los tipos de datos de los datos de prueba de origen y los valores constantes de destino sean válidos.</span><span class="sxs-lookup"><span data-stu-id="88138-106">If you use custom data or constants in your output, you must verify that the data types of your source test data and target constant values are valid.</span></span> <span data-ttu-id="88138-107">Cuando se valida una asignación, el asignador de BizTalk no comprueba si los datos de instancia infringen los tipos de datos definidos por los esquemas.</span><span class="sxs-lookup"><span data-stu-id="88138-107">When you validate a map, BizTalk Mapper does not check whether or not the instance data violates any data types defined by the schemas.</span></span> <span data-ttu-id="88138-108">Esto se hace al probar la asignación o validar los datos de instancia.</span><span class="sxs-lookup"><span data-stu-id="88138-108">This is done when you test the map or validate the instance data.</span></span>  
  
 <span data-ttu-id="88138-109">Para obtener más información acerca de cómo generar y validar datos de instancia mediante el Editor de BizTalk, consulte [validación y generación de mensaje de instancia](../core/instance-message-generation-and-validation.md) y [validación de instancia](../core/instance-validation.md).</span><span class="sxs-lookup"><span data-stu-id="88138-109">For more information about how to generate and validate instance data by using BizTalk Editor, see [Instance Message Generation and Validation](../core/instance-message-generation-and-validation.md) and [Instance Validation](../core/instance-validation.md).</span></span> <span data-ttu-id="88138-110">.</span><span class="sxs-lookup"><span data-stu-id="88138-110">.</span></span> <span data-ttu-id="88138-111">El **valor** propiedad del nodo de un esquema también afecta a cómo BizTalk genera datos de instancia.</span><span class="sxs-lookup"><span data-stu-id="88138-111">The **Value** property of the node of a schema also affects how BizTalk generates instance data.</span></span> <span data-ttu-id="88138-112">Para obtener más información, consulte el **propiedades del nodo esquema** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="88138-112">For more information, see the **Schema Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="88138-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="88138-113">See Also</span></span>  
-  [<span data-ttu-id="88138-114">Validación y generación de mensajes de instancia</span><span class="sxs-lookup"><span data-stu-id="88138-114">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)   
-  [<span data-ttu-id="88138-115">Cómo validar esquemas en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="88138-115">How to Validate Schemas in Visual Studio</span></span>](../core/how-to-validate-schemas-in-visual-studio.md)   
-  <span data-ttu-id="88138-116">**Referencia de propiedad se asignan**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="88138-116">**Map Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
-  [<span data-ttu-id="88138-117">Probar las asignaciones</span><span class="sxs-lookup"><span data-stu-id="88138-117">Testing Maps</span></span>](../core/testing-maps.md)