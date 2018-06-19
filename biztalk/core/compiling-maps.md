---
title: Compilar asignaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, compiling
- XSLT, generating
- maps, validating
- BizTalk Mapper, compiling
- BizTalk Mapper, validating
ms.assetid: 967181d6-22a9-4a76-ae45-3317c0c6321b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346769519343afe9456a7b1e7cf9a3bd5bb159ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231868"
---
# <a name="compiling-maps"></a><span data-ttu-id="5d8cb-102">Compilar asignaciones</span><span class="sxs-lookup"><span data-stu-id="5d8cb-102">Compiling Maps</span></span>
<span data-ttu-id="5d8cb-103">Cuando se validan asignaciones, el componente de compilador de Asignador de BizTalk genera una hoja de estilo de Transformación de lenguaje de hojas de estilo extensible (XSLT).</span><span class="sxs-lookup"><span data-stu-id="5d8cb-103">When you validate maps, the BizTalk Mapper compiler component generates an Extensible Stylesheet Language Transformations (XSLT) style sheet.</span></span> <span data-ttu-id="5d8cb-104">Esto crea una asignación compilada que transforma un mensaje de instancia definido por el esquema de origen en un mensaje de instancia definido por el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="5d8cb-104">This creates a compiled map that transforms an instance message defined by the source schema to an instance message defined by the destination schema.</span></span> <span data-ttu-id="5d8cb-105">Compilar una asignación reclama las transformaciones y reglas estructurales especificadas en las páginas de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="5d8cb-105">Compiling a map enforces the structural rules and transformations specified in the grid pages.</span></span>  
  
 <span data-ttu-id="5d8cb-106">Las transformaciones, como los vínculos, se procesan en el mismo orden en que los registros y campos aparecen en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="5d8cb-106">Transformations, such as links, are processed in the same order that records and fields appear in the destination schema.</span></span> <span data-ttu-id="5d8cb-107">Por ejemplo, cuando el asignador de BizTalk alcanza un destino **registro** o **campo** nodo con un vínculo, el asignador de BizTalk compila las propiedades del vínculo.</span><span class="sxs-lookup"><span data-stu-id="5d8cb-107">For example, when BizTalk Mapper reaches a destination **Record** or **Field** node with a link, BizTalk Mapper compiles the properties of the link.</span></span> <span data-ttu-id="5d8cb-108">La acción puede ser un sencillo valor copiado desde un registro o campo del esquema de origen, o puede implicar varios cálculos mediante functoids y múltiples registros y campos.</span><span class="sxs-lookup"><span data-stu-id="5d8cb-108">The action might be a simple copy value from a record or field in the source schema, or the action might involve multiple calculations using functoids and multiple records and fields.</span></span>  
  
 <span data-ttu-id="5d8cb-109">El asignador de BizTalk genera advertencias en el **salida** ventana y **lista de tareas** ventana cuando el compilador encuentra una situación que podría producir un resultado incorrecto.</span><span class="sxs-lookup"><span data-stu-id="5d8cb-109">BizTalk Mapper generates warnings in the **Output** window and **Task List** window when the compiler encounters a situation that might yield incorrect output.</span></span> <span data-ttu-id="5d8cb-110">Por ejemplo, si un functoid requiere un parámetro de entrada y no tiene ningún parámetro de entrada, el asignador de BizTalk genera una advertencia en el **salida** ventana.</span><span class="sxs-lookup"><span data-stu-id="5d8cb-110">For example, if a functoid requires one input parameter and has no input parameters, BizTalk Mapper generates a warning in the **Output** window.</span></span> <span data-ttu-id="5d8cb-111">Generalmente, no debe utilizar una asignación en un entorno de producción si está generando advertencias.</span><span class="sxs-lookup"><span data-stu-id="5d8cb-111">In general, you should not use a map in a production environment if it is generating warnings.</span></span>  
  
 <span data-ttu-id="5d8cb-112">También aparece un vínculo a la hoja de estilos XSLT generado en el **salida** ventana cuando la asignación se compila correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d8cb-112">A link to the generated XSLT style sheet also appears in the **Output** window when the map compiles correctly.</span></span>  
  
 <span data-ttu-id="5d8cb-113">El servidor BizTalk Server utiliza la asignación compilada para llevar a cabo la traducción de un mensaje de instancia de entrada a un mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="5d8cb-113">BizTalk Server uses the compiled map to perform the translation of an input instance message to an output instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d8cb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d8cb-114">See Also</span></span>  
 <span data-ttu-id="5d8cb-115">[Probar las asignaciones](../core/testing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="5d8cb-115">[Testing Maps](../core/testing-maps.md) </span></span>  
 <span data-ttu-id="5d8cb-116">[Configuración de transformación de datos](../core/data-transformation-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="5d8cb-116">[Data Transformation Configuration](../core/data-transformation-configuration.md) </span></span>  
 [<span data-ttu-id="5d8cb-117">Coincidencia del nivel jerárquico de nodos</span><span class="sxs-lookup"><span data-stu-id="5d8cb-117">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)