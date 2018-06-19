---
title: Acerca de las asignaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper
- maps, file type
- maps, about maps
- BizTalk Mapper, about BizTalk Mapper
- maps
ms.assetid: 512ef2b7-3d01-4fcf-bb38-de68ec608b07
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d15f37dc0ff0112906a449e1b1d84704b21727
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225564"
---
# <a name="about-maps"></a><span data-ttu-id="167d1-102">Acerca de las asignaciones</span><span class="sxs-lookup"><span data-stu-id="167d1-102">About Maps</span></span>
<span data-ttu-id="167d1-103">Con el Asignador de BizTalk, se define la relación entre un esquema de origen y uno de destino mediante vínculos y functoids.</span><span class="sxs-lookup"><span data-stu-id="167d1-103">Using BizTalk Mapper, you define the relationship between an input and an output schema by using links and functoids.</span></span> <span data-ttu-id="167d1-104">Un vínculo define una copia de datos directa de un registro o campo.</span><span class="sxs-lookup"><span data-stu-id="167d1-104">A link defines a direct data copy of a record or field.</span></span> <span data-ttu-id="167d1-105">Los vínculos puede conectarse directamente con elementos del otro esquema, o pueden establecer conexiones con functoids.</span><span class="sxs-lookup"><span data-stu-id="167d1-105">Links may directly connect to items in the other schema, or they may form connections to functoids.</span></span> <span data-ttu-id="167d1-106">Los functoids llevan a cabo manipulaciones de datos más complejas, como:</span><span class="sxs-lookup"><span data-stu-id="167d1-106">Functoids perform more complex data manipulations, such as:</span></span>  
  
-   <span data-ttu-id="167d1-107">Sumar el valor de dos campos del esquema de origen y copiar el resultado en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="167d1-107">Adding the value of two fields in the source schema and copying the result to the destination schema.</span></span>  
  
-   <span data-ttu-id="167d1-108">Convertir un carácter en su formato equivalente ASCII.</span><span class="sxs-lookup"><span data-stu-id="167d1-108">Converting a character to its ASCII format.</span></span>  
  
-   <span data-ttu-id="167d1-109">Devolver el promedio de un campo de un registro de repetición y copiar el resultado en un campo del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="167d1-109">Returning the average of a field in a repeating record and copying the result to a field in the destination schema.</span></span>  
  
 <span data-ttu-id="167d1-110">El Asignador de BizTalk almacena las asignaciones en un archivo con la extensión .btm.</span><span class="sxs-lookup"><span data-stu-id="167d1-110">BizTalk Mapper stores maps in a file with a .btm extension.</span></span> <span data-ttu-id="167d1-111">El archivo guarda información de diseño acerca de la asignación, las ubicaciones de los iconos que representan functoids, los vínculos entre elementos de esquema y functoids y otra información acerca de la asignación.</span><span class="sxs-lookup"><span data-stu-id="167d1-111">The file saves design information about the map—the locations of icons representing functoids, the links between schema items and functoids, and other information about the map.</span></span> <span data-ttu-id="167d1-112">Cuando genera o compila la asignación, el Asignador de BizTalk convierte la información sobre la asignación en la hoja de estilo de Transformación de lenguaje de hojas de estilo extensible (XSLT).</span><span class="sxs-lookup"><span data-stu-id="167d1-112">When you build or compile the map, BizTalk Mapper converts the information about the map into the corresponding Extensible Language Stylesheet Transformations (XSLT) stylesheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="167d1-113">El compilador de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] tiene un límite de 16 megabytes en el tamaño total de todas las cadenas en un único proyecto.</span><span class="sxs-lookup"><span data-stu-id="167d1-113">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler has a 16-megabyte limitation on the total size of all strings in a single project.</span></span> <span data-ttu-id="167d1-114">Al compilar proyectos de BizTalk, el compilador serializa esquemas, asignaciones y orquestaciones para crear los ensamblados y, por ello, el tamaño total de todas las cadenas aumenta y puede superar el límite.</span><span class="sxs-lookup"><span data-stu-id="167d1-114">While compiling BizTalk projects, the compiler serializes schemas, maps, and orchestrations for creating the assemblies, and this increases the total size of all strings, which may exceed the limitation.</span></span> <span data-ttu-id="167d1-115">Para resolver este problema, puede reorganizar el proyecto colocando esquemas y/o asignaciones en otros proyectos de Biztalk (normalmente, bajo la misma solución), de modo que el tamaño total de todas las cadenas de cada proyecto no supere los 16 MB.</span><span class="sxs-lookup"><span data-stu-id="167d1-115">To resolve this issue, you can reorganize your project by putting schemas and/or maps into different Biztalk projects (Typically, under the same solution), such that  the total size of all strings in each project is less than 16 MB.</span></span>  
  
 <span data-ttu-id="167d1-116">Las asignaciones que cree pueden transformar o traducir datos y pueden ser específicas para un único socio comercial o utilizarse con muchos socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="167d1-116">The maps that you create can transform or translate data, and they can be specific to a single trading partner or be used with many trading partners.</span></span> <span data-ttu-id="167d1-117">En los temas de esta sección se proporciona una introducción a los conceptos relacionados con los esquemas de asignación.</span><span class="sxs-lookup"><span data-stu-id="167d1-117">The topics in this section provide an introduction to the concepts involved in mapping schemas.</span></span> <span data-ttu-id="167d1-118">Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).</span><span class="sxs-lookup"><span data-stu-id="167d1-118">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="167d1-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="167d1-119">In This Section</span></span>  
  
-   [<span data-ttu-id="167d1-120">Vínculos en asignaciones</span><span class="sxs-lookup"><span data-stu-id="167d1-120">Links in Maps</span></span>](../core/links-in-maps.md)  
  
-   [<span data-ttu-id="167d1-121">Functoids en asignaciones</span><span class="sxs-lookup"><span data-stu-id="167d1-121">Functoids in Maps</span></span>](../core/functoids-in-maps.md)  
  
-   [<span data-ttu-id="167d1-122">Compilación de la asignación y las pruebas</span><span class="sxs-lookup"><span data-stu-id="167d1-122">Map Compilation and Testing</span></span>](../core/map-compilation-and-testing.md)