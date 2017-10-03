---
title: Secuencias de comandos con ensamblados externos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scripting functoids, warnings
- Scripting functoids, external assemblies
ms.assetid: 0bdf6adc-91b9-462e-8fd0-9cb48bfa7817
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 475a3b9781eecb0ccc79165bbe54e6dfd542ecfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scripting-using-external-assemblies"></a><span data-ttu-id="19cb7-102">Secuencias de comandos que utilizan ensamblados externos</span><span class="sxs-lookup"><span data-stu-id="19cb7-102">Scripting Using External Assemblies</span></span>
<span data-ttu-id="19cb7-103">Las secuencias de comandos con ensamblados externos es la forma recomendada de usar las secuencias de comandos en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19cb7-103">Scripting with external assemblies is the preferred way to use scripting in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="19cb7-104">Los ensamblados externos proporcionan varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="19cb7-104">External assemblies provide several advantages:</span></span>  
  
-   <span data-ttu-id="19cb7-105">Facilidad para compartir código</span><span class="sxs-lookup"><span data-stu-id="19cb7-105">Easy code sharing</span></span>  
  
-   <span data-ttu-id="19cb7-106">Mantenimiento más sencillo</span><span class="sxs-lookup"><span data-stu-id="19cb7-106">Simpler maintenance</span></span>  
  
-   <span data-ttu-id="19cb7-107">Depuración más fácil</span><span class="sxs-lookup"><span data-stu-id="19cb7-107">Easier debugging</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19cb7-108">Comprobar asignación se produce un error si la **secuencias de comandos** functoid usa un ensamblado externo que no está registrado en la GAC.</span><span class="sxs-lookup"><span data-stu-id="19cb7-108">Test Map fails if the **Scripting** functoid uses an external assembly which is not registered in the GAC.</span></span> <span data-ttu-id="19cb7-109">Funciona si el ensamblado externo está en la misma carpeta bin que el ensamblado del proyecto actual (colocado después de la generación).</span><span class="sxs-lookup"><span data-stu-id="19cb7-109">It works if the external assembly is in the same bin folder as the current project's assembly (placed after build).</span></span>  
  
 <span data-ttu-id="19cb7-110">Volver a usar el script basta con configurar la **Script** propiedad de la **secuencias de comandos** functoid.</span><span class="sxs-lookup"><span data-stu-id="19cb7-110">Re-using the script only requires setting the **Script** property of the **Scripting** functoid.</span></span> <span data-ttu-id="19cb7-111">Puesto que el script está almacenado fuera de la asignación, es posible modificar el script sin modificar la asignación.</span><span class="sxs-lookup"><span data-stu-id="19cb7-111">Because the script is stored outside of the map, you can modify the script without changing the map.</span></span> <span data-ttu-id="19cb7-112">Y puede utilizar la totalidad de herramientas de depuración de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para asegurarse de que el script se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="19cb7-112">And you can use the full array of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debugging tools to ensure your script runs correctly.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="19cb7-113">El código del ensamblado externo debe ser seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="19cb7-113">The code in the external assembly must be thread-safe.</span></span> <span data-ttu-id="19cb7-114">En condiciones de sobrecarga, pueden ejecutarse simultáneamente varias instancias de una asignación.</span><span class="sxs-lookup"><span data-stu-id="19cb7-114">Under stress conditions, multiple instances of a map may be running concurrently.</span></span>  
  
 <span data-ttu-id="19cb7-115">Para una función de ejemplo que se aloja en un ensamblado externo, vea [herramientas de XML (carpeta de ejemplos de BizTalk Server)](../core/xml-tools-biztalk-server-samples-folder.md).</span><span class="sxs-lookup"><span data-stu-id="19cb7-115">For a sample function housed in an external assembly, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19cb7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="19cb7-116">See Also</span></span>  
 <span data-ttu-id="19cb7-117">[Secuencias de comandos de Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="19cb7-117">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="19cb7-118">[Secuencias de comandos mediante C# en línea, JScript .NET y Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span><span class="sxs-lookup"><span data-stu-id="19cb7-118">[Scripting Using Inline C#, JScript .NET, and Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span></span>  
 <span data-ttu-id="19cb7-119">[Secuencias de comandos utilizando XSLT en línea y plantillas de llamada XSLT](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="19cb7-119">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 <span data-ttu-id="19cb7-120">[Cómo agregar Functoids de Scripting a un mapa](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="19cb7-120">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="19cb7-121">Cómo configurar el Functoid de secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="19cb7-121">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)