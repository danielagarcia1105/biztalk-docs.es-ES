---
title: Implementación de las pruebas automatizadas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4ba540e-789d-49bf-af4b-87e6f37ab96f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aee97d5c44ebd32ca5b325af386fb1a8754f5b20
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298052"
---
# <a name="implementing-automated-testing"></a><span data-ttu-id="de8ae-102">Implementación de las pruebas automatizadas</span><span class="sxs-lookup"><span data-stu-id="de8ae-102">Implementing Automated Testing</span></span>
<span data-ttu-id="de8ae-103">Soluciones de BizTalk Server se implementan a menudo en escenarios "de misión crítica", por la que la solución de BizTalk es un componente esencial de la empresa.</span><span class="sxs-lookup"><span data-stu-id="de8ae-103">BizTalk Server solutions are often deployed in “mission-critical” scenarios, whereby the BizTalk solution is a core component of the business.</span></span> <span data-ttu-id="de8ae-104">En estos escenarios, el rendimiento continuo y la estabilidad de BizTalk solución es un requisito clave para el negocio; Si se produce un error en la solución de BizTalk, los costos de tiempo de inactividad asociado son significativos.</span><span class="sxs-lookup"><span data-stu-id="de8ae-104">In these scenarios, the continual performance and stability of the BizTalk solution is a key business requirement; if the BizTalk solution fails, the associated downtime costs are significant.</span></span> <span data-ttu-id="de8ae-105">En estos escenarios, resulta de gran importancia que la solución de BizTalk se ha probado exhaustivamente antes de que la solución se coloca en producción.</span><span class="sxs-lookup"><span data-stu-id="de8ae-105">In such scenarios, it is of paramount importance that the BizTalk solution be thoroughly tested before the solution is placed into production.</span></span> <span data-ttu-id="de8ae-106">Los costos asociados con pruebas correctamente la solución son pequeños en comparación con los costos de tiempo de inactividad resultantes no estén probando o no son lo suficientemente probar la solución.</span><span class="sxs-lookup"><span data-stu-id="de8ae-106">The costs associated with properly testing the solution are small compared to the downtime costs resulting from not testing or insufficiently testing the solution.</span></span> <span data-ttu-id="de8ae-107">Por lo tanto, las pruebas de una solución de BizTalk Server sin duda es la fase más importante de cualquier implementación de la solución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="de8ae-107">Therefore, the testing of a BizTalk Server solution is arguably the most important phase of any BizTalk Server solution deployment.</span></span>  
  
 <span data-ttu-id="de8ae-108">Esta sección describe la metodología para probar una solución de BizTalk antes de ejecutar la solución en un entorno de producción adecuada.</span><span class="sxs-lookup"><span data-stu-id="de8ae-108">This section describes the proper methodology for testing a BizTalk solution before running the solution in a production environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de8ae-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="de8ae-109">In This Section</span></span>  
  
-   [<span data-ttu-id="de8ae-110">¿Por qué es importante para pruebas</span><span class="sxs-lookup"><span data-stu-id="de8ae-110">Why It Is Important to Test</span></span>](../technical-guides/why-it-is-important-to-test.md)  
  
-   [<span data-ttu-id="de8ae-111">Automatizar el proceso de compilación</span><span class="sxs-lookup"><span data-stu-id="de8ae-111">Automating the Build Process</span></span>](../technical-guides/automating-the-build-process.md)  
  
-   [<span data-ttu-id="de8ae-112">Usando BizUnit para facilitar la prueba automatizada</span><span class="sxs-lookup"><span data-stu-id="de8ae-112">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)  
  
-   [<span data-ttu-id="de8ae-113">Con Visual Studio para facilitar la prueba automatizada</span><span class="sxs-lookup"><span data-stu-id="de8ae-113">Using Visual Studio to Facilitate Automated Testing</span></span>](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)