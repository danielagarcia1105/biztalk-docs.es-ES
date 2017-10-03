---
title: Functoids en asignaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- functoids
- functoids, about functoids
- functoid types, Record Count
- functoid types, Looping
- Looping functoids
- functoids, categories
- functoid types, Addition
- Record Count functoids
ms.assetid: 10ee8b62-cb20-4d26-9d86-b6564f30c297
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 976af2faed27e6cae8a57d9c7c83308d0519d81d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="functoids-in-maps"></a><span data-ttu-id="095fc-102">Functoids en asignaciones</span><span class="sxs-lookup"><span data-stu-id="095fc-102">Functoids in Maps</span></span>
<span data-ttu-id="095fc-103">El Asignador de BizTalk admite transformaciones estructurales complejas de registros y campos del esquema de origen a registros y campos del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="095fc-103">BizTalk Mapper supports complex structural transformations from records and fields in the source schema to records and fields in the destination schema.</span></span> <span data-ttu-id="095fc-104">Los functoids realizan cálculos utilizando fórmulas predefinidas y valores específicos, denominados argumentos.</span><span class="sxs-lookup"><span data-stu-id="095fc-104">Functoids perform calculations by using predefined formulas and specific values, called arguments.</span></span> <span data-ttu-id="095fc-105">Estos cálculos se llevan a cabo según el orden establecido de registros y campos.</span><span class="sxs-lookup"><span data-stu-id="095fc-105">These calculations are executed based on the designated order of the records and fields.</span></span>  
  
 <span data-ttu-id="095fc-106">Al seleccionar un functoid en el cuadro de herramientas, arrastrarlo a la página de cuadrícula y vincularlo con nodos de los esquemas de origen y de destino, los datos se pueden agregar juntos, la información de fecha u hora se puede modificar, los datos se pueden concatenar o pueden llevarse a cabo otras operaciones.</span><span class="sxs-lookup"><span data-stu-id="095fc-106">By selecting a functoid from the Toolbox, dragging it to the grid page, and linking it to nodes in the source schema and destination schema, data can be added together, date or time information can be modified, data can be concatenated, or other operations can be performed.</span></span> <span data-ttu-id="095fc-107">Por ejemplo, el **suma** functoid agrega valores y la **número de registros** functoid devuelve el número total de un registro de bucle en un mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="095fc-107">For example, the **Addition** functoid adds values and the **Record Count** functoid returns the total count of a looping record in an instance message.</span></span> <span data-ttu-id="095fc-108">Las categorías de functoids que puede encontrar en el cuadro de herramientas son: avanzadas, conversión, acumulativos, base de datos, fecha / hora, lógicos, matemáticos, científica y cadena.</span><span class="sxs-lookup"><span data-stu-id="095fc-108">Categories of functoids that you can find in the Toolbox include: Advanced, Conversion, Cumulative, Database, Date/ Time, Logical, Mathematical, Scientific, and String.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="095fc-109">Todos los functoids son C# en línea, excepto los de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="095fc-109">All functoids are inline C# except for the Database functoids.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="095fc-110">Nodos de esquema de destino solo aceptan una entrada de un functoid con excepción de la **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="095fc-110">Destination schema nodes accept only one input from a functoid with the exception of the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="095fc-111">En los temas de esta sección se describe cómo migrar functoids de versiones anteriores de BizTalk Server, qué functoids hay, qué hacen y cómo utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="095fc-111">The topics in this section describe how to migrate functoids from previous versions of BizTalk Server, what functoids are, what they do, and how to use them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="095fc-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="095fc-112">In This Section</span></span>  
  
-   [<span data-ttu-id="095fc-113">Categorías de functoids</span><span class="sxs-lookup"><span data-stu-id="095fc-113">Functoid Categories</span></span>](../core/functoid-categories.md)  
  
-   [<span data-ttu-id="095fc-114">Parámetros de entrada de functoid</span><span class="sxs-lookup"><span data-stu-id="095fc-114">Functoid Input Parameters</span></span>](../core/functoid-input-parameters.md)  
  
-   [<span data-ttu-id="095fc-115">Functoids básicos</span><span class="sxs-lookup"><span data-stu-id="095fc-115">Basic Functoids</span></span>](../core/basic-functoids.md)  
  
-   [<span data-ttu-id="095fc-116">Functoids avanzados</span><span class="sxs-lookup"><span data-stu-id="095fc-116">Advanced Functoids</span></span>](../core/advanced-functoids.md)  
  
-   [<span data-ttu-id="095fc-117">Functoids en cascada</span><span class="sxs-lookup"><span data-stu-id="095fc-117">Cascading Functoids</span></span>](../core/cascading-functoids.md)  
  
-   [<span data-ttu-id="095fc-118">Propiedades de functoid</span><span class="sxs-lookup"><span data-stu-id="095fc-118">Functoid Properties</span></span>](../core/functoid-properties.md)  
  
-   [<span data-ttu-id="095fc-119">Migrar Functoids</span><span class="sxs-lookup"><span data-stu-id="095fc-119">Migrating Functoids</span></span>](../core/migrating-functoids.md)