---
title: El controlador de errores de las operaciones de ejemplo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Ops adapters, error handler
- process management solution tutorial, Ops adapters
ms.assetid: e6c55f01-c004-4340-beaa-d77764ae34c1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93536733c884b4d5db57ba18619ebabdead17561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-sample-operations-error-handler"></a><span data-ttu-id="b6d45-102">El controlador de errores de operaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6d45-102">The Sample Operations Error Handler</span></span>
<span data-ttu-id="b6d45-103">El controlador de errores de las operaciones de ejemplo tiene tres ensamblados principales: **OperationsClient**, **OperationsHandler**, y **OperationsServer**.</span><span class="sxs-lookup"><span data-stu-id="b6d45-103">The sample operations error handler has three major assemblies: **OperationsClient**, **OperationsHandler**, and **OperationsServer**.</span></span>  
  
 <span data-ttu-id="b6d45-104">La solución configura el adaptador para usar el **OpsClient** objeto en el **OperationsClient** ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b6d45-104">The solution configures the adapter to use the **OpsClient** object in the **OperationsClient** assembly.</span></span> <span data-ttu-id="b6d45-105">Como cabría esperar, el **OpsClient** objeto implementa la **IOpsAIC** interfaz.</span><span class="sxs-lookup"><span data-stu-id="b6d45-105">As you'd expect, the **OpsClient** object implements the **IOpsAIC** interface.</span></span>  
  
 <span data-ttu-id="b6d45-106">El **OpsClient** de objeto usa la **IOperationsSystem** interfaz para llamar a la **OpsHandler** objeto a través de la [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] característica de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="b6d45-106">The **OpsClient** object uses the **IOperationsSystem** interface to call the **OpsHandler** object through the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] remoting feature.</span></span> <span data-ttu-id="b6d45-107">El **IOperationsSystem** interfaz aparece como sigue:</span><span class="sxs-lookup"><span data-stu-id="b6d45-107">The **IOperationsSystem** interface appears as follows:</span></span>  
  
```  
public interface IOperationsSystem  
{  
    void Initialize(string initData);  
    void Post(string originMachine, byte[] message);  
}  
  
```  
  
 <span data-ttu-id="b6d45-108">El **OperationsServer**, una aplicación de consola, escucha las solicitudes de la **OpsHandler** de objeto y actúa como el servidor para el [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] característica de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="b6d45-108">The **OperationsServer**, a console application, listens for requests for the **OpsHandler** object and acts as the server for the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] remoting feature.</span></span> <span data-ttu-id="b6d45-109">Llamando a la **Execute** método de la **OpsClient** objeto a su vez, se invoca el **Post** método de la **OpsHandler** objeto.</span><span class="sxs-lookup"><span data-stu-id="b6d45-109">Calling the **Execute** method of the **OpsClient** object in turn invokes the **Post** method of the **OpsHandler** object.</span></span>  
  
 <span data-ttu-id="b6d45-110">El **OpsHandler** métodos responden escribiendo las cadenas de argumento utilizando el **seguimiento** objeto.</span><span class="sxs-lookup"><span data-stu-id="b6d45-110">The **OpsHandler** methods respond by writing out their argument strings using the **Trace** object.</span></span> <span data-ttu-id="b6d45-111">Esto envía los errores a la consola.</span><span class="sxs-lookup"><span data-stu-id="b6d45-111">This posts the errors to the console.</span></span> <span data-ttu-id="b6d45-112">Para obtener más información sobre la **seguimiento** de objetos, vea "Clase Trace" en la [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="b6d45-112">For more information about the **Trace** object, see "Trace Class" in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Class Library.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6d45-113">El patrón aquí es el mismo que en el **OrderHandler** en el que una interfaz especifica las llamadas al método entre un cliente y un objeto remoto.</span><span class="sxs-lookup"><span data-stu-id="b6d45-113">The pattern here is the same as that in the **OrderHandler** in which an interface specifies the method calls between a client and a remoted object.</span></span> <span data-ttu-id="b6d45-114">Sin embargo, hay un nivel adicional de direccionamiento indirecto entre el **OpsClient** y **OpsHandler**.</span><span class="sxs-lookup"><span data-stu-id="b6d45-114">There is, however, an additional layer of indirection here between the **OpsClient** and the **OpsHandler**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d45-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6d45-115">See Also</span></span>  
 [<span data-ttu-id="b6d45-116">El adaptador Ops</span><span class="sxs-lookup"><span data-stu-id="b6d45-116">The Ops Adapter</span></span>](../core/the-ops-adapter.md)