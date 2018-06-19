---
title: Functoid de bucle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19886ccb-4642-48a4-b93e-563640ea828b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ce2b66fd796708a0e8b24ee05e3a0b043af6808
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22262844"
---
# <a name="looping-functoid"></a><span data-ttu-id="30ab6-102">Bucle (functoid)</span><span class="sxs-lookup"><span data-stu-id="30ab6-102">Looping Functoid</span></span>

## <a name="overview--example"></a><span data-ttu-id="30ab6-103">Información general sobre & ejemplo</span><span class="sxs-lookup"><span data-stu-id="30ab6-103">Overview & example</span></span>
<span data-ttu-id="30ab6-104">El **bucle** functoid combina múltiples registros o campos del esquema de origen en un único registro del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="30ab6-104">The **Looping** functoid combines multiple records or fields in the source schema into a single record in the destination schema.</span></span>  
  
 <span data-ttu-id="30ab6-105">La siguiente ilustración muestra un **bucle**functoid usado en una asignación para combinar direcciones recopiladas de dos encuestas diferentes en una lista de direcciones maestra única.</span><span class="sxs-lookup"><span data-stu-id="30ab6-105">The following figure shows a **Looping**functoid used in a map to combine addresses collected from two different surveys into a single master address list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30ab6-106">El **bucle** y **asignación de valores (sin formato)** functoids no deben usarse juntos.</span><span class="sxs-lookup"><span data-stu-id="30ab6-106">The **Looping** and **Value Mapping (Flattening)** functoids should not be used together.</span></span> <span data-ttu-id="30ab6-107">Si ambos se usan conjuntamente, se produce una asignación compilada que supone que no hay dependencia de los nodos de destino que están por debajo de bucle de origen el **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="30ab6-107">If both are used together, it results in a compiled map that assumed there is no source looping dependency for the target nodes that are below the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="30ab6-108">![Mapa que ilustra el uso del functoid de bucle. ] (../core/media/loopingfunctoid.gif "loopingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="30ab6-108">![Map illustrating the use of the looping functoid.](../core/media/loopingfunctoid.gif "loopingfunctoid")</span></span>  
  
 <span data-ttu-id="30ab6-109">El **FoodSurvey** y **FlowerSurvey** registros de bucle del esquema de origen se asignan a los bucles **dirección** registro del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="30ab6-109">The **FoodSurvey** and **FlowerSurvey** looping records of the source schema are mapped to the looping **Address** record of the destination schema.</span></span> <span data-ttu-id="30ab6-110">Si un mensaje de instancia de entrada tiene tres **FoodSurvey** y dos registros **FlowerSurvey** registros, la **bucle**functoid combina estos elementos para crear cinco  **Dirección** registros en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="30ab6-110">If an input instance message has three **FoodSurvey** records and two **FlowerSurvey** records, the **Looping**functoid combines these to create five **Address** records in the output instance message.</span></span>  
  
 <span data-ttu-id="30ab6-111">El siguiente código es un mensaje de instancia de entrada de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="30ab6-111">The following code is a sample input instance message.</span></span>  
  
```  
<ns0:Surveys xmlns:ns0="http://LoopingFunctoid.Surveys">  
    <FoodSurvey Name="Karin Zimprich" Address="345 N 63rd St" City="Boston" State="MA" PostalCode="07485" />  
    <FoodSurvey Name="Wendy Wheeler" Address="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" />  
    <FoodSurvey Name="Florian Voss" Address="1234 Main St" City="Denver" State="CO" PostalCode="97402" />  
    <FlowerSurvey Name="Kelly Focht" Address="456 1st Ave" City="Miami" State="FL" PostalCode="81406" />  
    <FlowerSurvey Name="Jim Kim" Address="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" />  
</ns0:Surveys>  
```  
  
 <span data-ttu-id="30ab6-112">Este mensaje de instancia de entrada produce el siguiente mensaje de instancia de salida cuando lo procesa una asignación en la ilustración anterior.</span><span class="sxs-lookup"><span data-stu-id="30ab6-112">This input instance message produces the following output instance message when processed by the map in the preceding figure.</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 <span data-ttu-id="30ab6-113">El **FoodSurvey** y **FlowerSurvey** han combinado las direcciones de mensaje.</span><span class="sxs-lookup"><span data-stu-id="30ab6-113">The **FoodSurvey** and **FlowerSurvey** message addresses have been combined.</span></span> <span data-ttu-id="30ab6-114">El mensaje combinado no indica el origen de cada dirección.</span><span class="sxs-lookup"><span data-stu-id="30ab6-114">The combined message does not indicate the source of each address.</span></span> <span data-ttu-id="30ab6-115">Si desea realizar un seguimiento del origen, agregue un **origen** atribuir a la **dirección** registros de la **MasterAddress** esquema y asignar un valor constante.</span><span class="sxs-lookup"><span data-stu-id="30ab6-115">If you want to track the source, add a **Source** attribute to the **Address** record of the **MasterAddress** schema and map a constant value.</span></span> <span data-ttu-id="30ab6-116">Para establecer este valor, conecte el **FoodSurvey** campo a la nueva **origen** campo.</span><span class="sxs-lookup"><span data-stu-id="30ab6-116">To set this value, connect the **FoodSurvey** field to the new **Source** field.</span></span> <span data-ttu-id="30ab6-117">En la línea de conexión, modifique la **propiedades de vínculo de** &#124; **compilador** &#124; **vínculos de origen** propiedad a "Copiar nombre".</span><span class="sxs-lookup"><span data-stu-id="30ab6-117">On the connector line, modify the **Link Properties** &#124; **Compiler** &#124; **Source Links** property to "Copy name".</span></span> <span data-ttu-id="30ab6-118">Repita este proceso para el **FlowerSurvey** campo.</span><span class="sxs-lookup"><span data-stu-id="30ab6-118">Repeat this process for the **FlowerSurvey** field.</span></span> <span data-ttu-id="30ab6-119">Volver a procesar el mensaje de entrada anterior produce el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="30ab6-119">Reprocessing the input message from above yields the following output:</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458" Source="FoodSurvey"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" Source="FoodSurvey"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402" Source="FoodSurvey"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406" Source="FlowerSurvey"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" Source="FlowerSurvey"/>  
</ns0:MasterAddresses>  
```  

## <a name="relationships-with-nodes"></a><span data-ttu-id="30ab6-120">Relaciones con nodos</span><span class="sxs-lookup"><span data-stu-id="30ab6-120">Relationships with nodes</span></span>

 <span data-ttu-id="30ab6-121">Las relaciones entre nodos afectan al comportamiento de la **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="30ab6-121">Relationships among nodes affect the behavior of the **Looping** functoid.</span></span> <span data-ttu-id="30ab6-122">Por ejemplo, vincular un nodo secundario y su entidad primaria en el esquema de origen el **bucle** functoid impide que el nodo de destino que se está creando.</span><span class="sxs-lookup"><span data-stu-id="30ab6-122">For example, linking both a child node and its parent in the source schema to the **Looping** functoid prevents the destination node from being created.</span></span>  
  
 <span data-ttu-id="30ab6-123">También se ven afectados los functoids por las relaciones entre los nodos de origen.</span><span class="sxs-lookup"><span data-stu-id="30ab6-123">Functoids are also affected by the relationships among source nodes.</span></span> <span data-ttu-id="30ab6-124">Conectar un functoid a campos secundarios de diferente nivel de nodos de origen de la **bucle** functoid puede producir resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="30ab6-124">Connecting a functoid to non-sibling child fields of source nodes of the **Looping** functoid may produce unexpected results.</span></span> <span data-ttu-id="30ab6-125">Por ejemplo, si se usa el **concatenación de cadenas** functoid para combinar el **FoodSurvey** campo de nombre y **FlowerSurvey** campo de dirección en el campo de nombre de dirección en **MasterAddress** generaría el siguiente mensaje de instancia de salida:</span><span class="sxs-lookup"><span data-stu-id="30ab6-125">For example, using the **String Concatenate** functoid to combine the **FoodSurvey** Name field and **FlowerSurvey** Address field into the Address Name field in **MasterAddress** would produce the following output instance message:</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 <span data-ttu-id="30ab6-126">Observe cómo la **nombre** campo no está presente para **FoodSurvey** origen mensajes pero está presente para **FlowerSurvey** mensajes de origen.</span><span class="sxs-lookup"><span data-stu-id="30ab6-126">Notice how the **Name** field is missing for **FoodSurvey** source messages but is present for **FlowerSurvey** source messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="30ab6-127">Conectar un functoid a campos secundarios de nodos de origen de la **bucle** functoid puede producir resultados inesperados si los nodos de origen no son del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="30ab6-127">Connecting a functoid to child fields of source nodes of the **Looping** functoid may produce unexpected results if the source nodes are not siblings.</span></span>  
  
 <span data-ttu-id="30ab6-128">El **bucle** functoid es una eficaz construcción que puede usar para crear bucles condicionales y asignar esquemas a catálogos.</span><span class="sxs-lookup"><span data-stu-id="30ab6-128">The **Looping** functoid is a powerful construct that you can use to create conditional loops and to map schemas to catalogs.</span></span> <span data-ttu-id="30ab6-129">También hay algunos efectos de superpuestas **bucle** rutas de functoid debe tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="30ab6-129">There are also some effects of overlapping **Looping** functoid paths you need to take into account.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="30ab6-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="30ab6-130">Next steps</span></span>
  
-   [<span data-ttu-id="30ab6-131">Bucles condicionales</span><span class="sxs-lookup"><span data-stu-id="30ab6-131">Conditional Looping</span></span>](../core/conditional-looping.md)  
  
-   [<span data-ttu-id="30ab6-132">De esquema sin formato a catálogo</span><span class="sxs-lookup"><span data-stu-id="30ab6-132">Flat Schema to Catalog</span></span>](../core/flat-schema-to-catalog.md)  
  
-   [<span data-ttu-id="30ab6-133">Rutas de acceso de bucles</span><span class="sxs-lookup"><span data-stu-id="30ab6-133">Loop Paths</span></span>](../core/loop-paths.md)  
  
## <a name="see-also"></a><span data-ttu-id="30ab6-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="30ab6-134">See Also</span></span>  
 <span data-ttu-id="30ab6-135">**Referencia de Functoid de bucle de tabla** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="30ab6-135">**Table Looping Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>