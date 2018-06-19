---
title: Functoids acumulativos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0549867-e0e4-4cdb-aae0-cadc99088e03
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6ed3d5037d64cf21e1ee2676a5739f13e18da3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240068"
---
# <a name="cumulative-functoids"></a><span data-ttu-id="ab195-102">Functoids acumulados</span><span class="sxs-lookup"><span data-stu-id="ab195-102">Cumulative Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="ab195-103">Información general</span><span class="sxs-lookup"><span data-stu-id="ab195-103">Overview</span></span>
<span data-ttu-id="ab195-104">**Acumulado** functoids reducen una serie de valores en un valor único como una suma, una cadena concatenada o un promedio.</span><span class="sxs-lookup"><span data-stu-id="ab195-104">**Cumulative** functoids reduce a series of values to a single value such as a sum, a concatenated string, or an average.</span></span>  
  
 <span data-ttu-id="ab195-105">Todos los **acumulativa** functoids aceptan dos parámetros de entrada:</span><span class="sxs-lookup"><span data-stu-id="ab195-105">All **Cumulative** functoids accept two input parameters:</span></span>  
  
1.  <span data-ttu-id="ab195-106">El valor que se va a acumular.</span><span class="sxs-lookup"><span data-stu-id="ab195-106">The value to accumulate.</span></span> <span data-ttu-id="ab195-107">Este valor es numérico para todos los **acumulativa** functoids excepto la **concatenación acumulativa** functoid que espera un valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="ab195-107">This value is numeric for all **Cumulative** functoids except the **Cumulative Concatenate** functoid which expects a string value.</span></span> <span data-ttu-id="ab195-108">El valor suele ser un vínculo desde un **atributo de campo**, **elemento de campo**, o **registro** nodo (con sus **Mixed** propiedad establecida en **True**).</span><span class="sxs-lookup"><span data-stu-id="ab195-108">The value is a link, often from a **Field Attribute**, **Field Element**, or **Record** node (with its **Mixed** property set to **True**).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab195-109">Si ninguno de los antecesores **registro** bucle nodos en el árbol de esquema, con un **acumulativa** functoid no es necesario.</span><span class="sxs-lookup"><span data-stu-id="ab195-109">If none of the ancestor **Record** nodes in the schema tree are looping, using a **Cumulative** functoid is unnecessary.</span></span>  
  
2.  <span data-ttu-id="ab195-110">El ámbito en el que se acumula este valor.</span><span class="sxs-lookup"><span data-stu-id="ab195-110">The scope within which the value is accumulated.</span></span> <span data-ttu-id="ab195-111">Este argumento es opcional.</span><span class="sxs-lookup"><span data-stu-id="ab195-111">This argument is optional.</span></span> <span data-ttu-id="ab195-112">El argumento indica el grado de relación que deben tener los valores para que se puedan acumular.</span><span class="sxs-lookup"><span data-stu-id="ab195-112">The argument indicates how closely related the specified values must be to be accumulated.</span></span>  
  
 <span data-ttu-id="ab195-113">En la siguiente tabla se muestran los valores del parámetro de ámbito y su efecto.</span><span class="sxs-lookup"><span data-stu-id="ab195-113">The following table shows the values for the scoping parameter and its effect:</span></span>  
  
|<span data-ttu-id="ab195-114">Valor del parámetro de ámbito</span><span class="sxs-lookup"><span data-stu-id="ab195-114">Scoping Parameter Value</span></span>|<span data-ttu-id="ab195-115">Efecto</span><span class="sxs-lookup"><span data-stu-id="ab195-115">Effect</span></span>|  
|-----------------------------|------------|  
|<span data-ttu-id="ab195-116">0 (cero)</span><span class="sxs-lookup"><span data-stu-id="ab195-116">0 (zero)</span></span>|<span data-ttu-id="ab195-117">Acumula los valores de todo el mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="ab195-117">Accumulate the value over the entire instance message.</span></span> <span data-ttu-id="ab195-118">El valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ab195-118">The default.</span></span>|  
|<span data-ttu-id="ab195-119">1 (uno)</span><span class="sxs-lookup"><span data-stu-id="ab195-119">1 (one)</span></span>|<span data-ttu-id="ab195-120">Acumula los valores de los elemento o atributos con el mismo elemento primario.</span><span class="sxs-lookup"><span data-stu-id="ab195-120">Accumulate the value of element or attribute values with the same parent element.</span></span>|  
|<span data-ttu-id="ab195-121">2</span><span class="sxs-lookup"><span data-stu-id="ab195-121">2</span></span>|<span data-ttu-id="ab195-122">Acumula los valores de los elemento o atributos con el mismo elemento primario de segundo nivel.</span><span class="sxs-lookup"><span data-stu-id="ab195-122">Accumulate the value of element or attribute values with the same grandparent element.</span></span>|  
|<span data-ttu-id="ab195-123">3 o superior</span><span class="sxs-lookup"><span data-stu-id="ab195-123">3 or greater</span></span>|<span data-ttu-id="ab195-124">Acumula los valores de los elementos o atributos, de ámbito progresivamente más amplio, que siguen el patrón anterior (elemento primario de segundo nivel, tercero, cuarto, etc.).</span><span class="sxs-lookup"><span data-stu-id="ab195-124">Accumulate the value of element or attribute values of progressively wider scope following the preceding pattern (great-grandparent, great-great-grandparent, etc.).</span></span>|  

## <a name="example"></a><span data-ttu-id="ab195-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ab195-125">Example</span></span>  
 <span data-ttu-id="ab195-126">Un ejemplo del uso de un **acumulativa** functoid sería la suma de los costos a través de un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="ab195-126">An example of using a **Cumulative** functoid might be summing costs across a purchase order.</span></span> <span data-ttu-id="ab195-127">El código que se muestra a continuación es un ejemplo de un pedido.</span><span class="sxs-lookup"><span data-stu-id="ab195-127">The following code is an example of a purchase order.</span></span>  
  
```  
<ns0:PurchaseOrder xmlns:ns0="http://CumulativeFunctoid.PurchaseOrder">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <LineItems>  
        <Item>  
            <Product>Laptop Computer</Product>  
            <Description>Thin profile laptop</Description>  
            <Price>1999.95</Price>  
            <Quantity>1</Quantity>  
        </Item>  
        <Item>  
            <Product>Monitor Swipes</Product>  
            <Description>Disposable monitor swipes</Description>  
            <Price>3.95</Price>  
            <Quantity>10</Quantity>  
        </Item>  
    </LineItems>  
</ns0:PurchaseOrder>  
```  
  
 <span data-ttu-id="ab195-128">El **Max Occurs** propiedad para la **elemento** registro, por supuesto, sería **unbounded**.</span><span class="sxs-lookup"><span data-stu-id="ab195-128">The **Max Occurs** property for the **Item** record would, of course, be **unbounded**.</span></span> <span data-ttu-id="ab195-129">Esto indica que el registro de elemento se repite y el Asignador de BizTalk compila este registro como un bucle.</span><span class="sxs-lookup"><span data-stu-id="ab195-129">This indicates that the item record loops, and BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="ab195-130">La siguiente ilustración muestra una asignación que utiliza un **multiplicación** functoid y un **suma acumulativa** functoid para agregar registros de elementos de una entrada de pedido de compra y mostrar los resultados en la  **POTotal** campo:</span><span class="sxs-lookup"><span data-stu-id="ab195-130">The following figure shows a map using a **Multiplication** functoid and a **Cumulative Sum** functoid to aggregate item records from an incoming purchase order and output the results in the **POTotal** field:</span></span>  
  
 <span data-ttu-id="ab195-131">![Mapa que muestra el uso del functoid de suma acumulativa. ] (../core/media/cumulativefunctoids.gif "cumulativefunctoids")</span><span class="sxs-lookup"><span data-stu-id="ab195-131">![Map showing usage of the cumulative sum functoid.](../core/media/cumulativefunctoids.gif "cumulativefunctoids")</span></span>  

  
 <span data-ttu-id="ab195-132">La asignación produce la siguiente salida con los datos anteriores y con el valor predeterminado del parámetro de ámbito, 0 (cero):</span><span class="sxs-lookup"><span data-stu-id="ab195-132">The map produces the following output with the preceding data and with the default scoping parameter value, 0 (zero):</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
 <span data-ttu-id="ab195-133">En este ejemplo, todos los **elemento** registra en el **LineItems** registro participar en la acumulación: el valor predeterminado para el parámetro de ámbito indica la suma de los valores en todo el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ab195-133">In this example, all the **Item** records under the **LineItems** record participate in the accumulation—the default for the scoping parameter indicates accumulating the values across the entire message.</span></span> <span data-ttu-id="ab195-134">El **precio** y **cantidad** campos se envían a un **multiplicación** functoid.</span><span class="sxs-lookup"><span data-stu-id="ab195-134">The **Price** and **Quantity** fields are sent to a **Multiplication** functoid.</span></span> <span data-ttu-id="ab195-135">El resultado de la **multiplicación** functoid se convierte en la entrada a la **suma acumulativa** functoid.</span><span class="sxs-lookup"><span data-stu-id="ab195-135">The output of the **Multiplication** functoid becomes the input to the **Cumulative Sum** functoid.</span></span> <span data-ttu-id="ab195-136">El resultado de la **suma acumulativa** functoid es el valor acumulado como el **elemento** se recorren los registros del pedido de compra de entrada.</span><span class="sxs-lookup"><span data-stu-id="ab195-136">The output of the **Cumulative Sum** functoid is the accumulated value as the **Item** records are traversed in the input purchase order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab195-137">La suma acumulativa de entradas tiene lugar en el registro primario en el que se origina el vínculo de entrada.</span><span class="sxs-lookup"><span data-stu-id="ab195-137">The cumulative aggregation of input takes place over the parent record from which the input link originates.</span></span> <span data-ttu-id="ab195-138">Incluso cuando la **acumulativa** functoid obtiene su entrada de otro functoid, la suma acumulativa tiene lugar en el registro primario de los vínculos de entrada para el functoid que actúa como entrada para el **acumulativa**functoid.</span><span class="sxs-lookup"><span data-stu-id="ab195-138">Even when the **Cumulative** functoid gets its input from another functoid, the cumulative aggregation takes place over the parent record of the input links to the functoid that serves as input to the **Cumulative** functoid.</span></span>  
  
 <span data-ttu-id="ab195-139">Si cambia el parámetro de ámbito a 1 (uno) y modifica ligeramente el esquema de salida, se produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ab195-139">Changing the scoping parameter to 1 (one) and modifying the output schema slightly, yields output like the following:</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <ItemTotal>1999.95</ItemTotal>  
    <ItemTotal>39.5</ItemTotal>  
</ns0:SummedPO>  
```  
  
 <span data-ttu-id="ab195-140">Si establece el parámetro de ámbito a 1 (uno) se acumulan los valores de elementos o atributos con el mismo elemento primario.</span><span class="sxs-lookup"><span data-stu-id="ab195-140">Setting the scoping parameter to 1 (one) indicates accumulating values for elements or attributes with the same parent.</span></span> <span data-ttu-id="ab195-141">Aquí el **precio** y **cantidad** campos tienen **elemento** como elemento primario para que el functoid suma los valores de cada cliente individual **elemento**.</span><span class="sxs-lookup"><span data-stu-id="ab195-141">Here the **Price** and **Quantity** fields have **Item** as a parent so that the functoid sums values for each individual **Item**.</span></span>  
  
 <span data-ttu-id="ab195-142">Si establece el parámetro de ámbito a 2 (dos) el functoid acumula los valores de elementos o atributos con el mismo elemento primario de segundo nivel.</span><span class="sxs-lookup"><span data-stu-id="ab195-142">If the scoping parameter is 2, the functoid accumulates values for elements or attributes with the same grandparent.</span></span> <span data-ttu-id="ab195-143">El primario de segundo nivel de la **precio** y **cantidad** campos es la **LineItems** registro.</span><span class="sxs-lookup"><span data-stu-id="ab195-143">The grandparent of the **Price** and **Quantity** fields is the **LineItems** record.</span></span> <span data-ttu-id="ab195-144">Dado que solo hay un **LineItems** registros en el mensaje de instancia, el resultado es el mismo que usar el valor predeterminado:</span><span class="sxs-lookup"><span data-stu-id="ab195-144">Because there is only one **LineItems** record in the instance message, the result is the same as using the default value:</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  <span data-ttu-id="ab195-145">Functoids acumulativos (salvo el **cadena acumulativa** functoid) ignorar la entrada no numéricos.</span><span class="sxs-lookup"><span data-stu-id="ab195-145">Cumulative functoids (except for the **Cumulative String** functoid) ignore non-numeric input.</span></span> <span data-ttu-id="ab195-146">Por ejemplo, se omite un valor de entrada de "tres”.</span><span class="sxs-lookup"><span data-stu-id="ab195-146">For example, an input value of "three" is ignored.</span></span>  
  
 <span data-ttu-id="ab195-147">El **promedio acumulativo**, **mínimo acumulativo**, y **máximo acumulativo** functoids se comportan de forma similar a la **suma acumulativa** functoid.</span><span class="sxs-lookup"><span data-stu-id="ab195-147">The **Cumulative Average**, **Cumulative Minimum**, and **Cumulative Maximum** functoids behave similarly to the **Cumulative Sum** functoid.</span></span> <span data-ttu-id="ab195-148">El **cadena acumulativa** concatena cadenas en lugar de agregar valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="ab195-148">The **Cumulative String** concatenates strings rather than aggregating numeric values.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="ab195-149">Functoids disponibles</span><span class="sxs-lookup"><span data-stu-id="ab195-149">Available functoids</span></span>
  
 <span data-ttu-id="ab195-150">El **acumulativa** functoids son:</span><span class="sxs-lookup"><span data-stu-id="ab195-150">The **Cumulative** functoids are:</span></span> 

* <span data-ttu-id="ab195-151">Promedio acumulativo</span><span class="sxs-lookup"><span data-stu-id="ab195-151">Cumulative Average</span></span>
* <span data-ttu-id="ab195-152">Concatenación acumulativa</span><span class="sxs-lookup"><span data-stu-id="ab195-152">Cumulative Concatenate</span></span>
* <span data-ttu-id="ab195-153">Máximo acumulativo</span><span class="sxs-lookup"><span data-stu-id="ab195-153">Cumulative Maximum</span></span>
* <span data-ttu-id="ab195-154">Mínimo acumulativo</span><span class="sxs-lookup"><span data-stu-id="ab195-154">Cumulative Minimum</span></span>
* <span data-ttu-id="ab195-155">Suma acumulativa</span><span class="sxs-lookup"><span data-stu-id="ab195-155">Cumulative Sum</span></span>

<span data-ttu-id="ab195-156">Más detalles sobre estos functoids [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="ab195-156">More details on these functoids are [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ab195-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab195-157">See Also</span></span>  
-  [<span data-ttu-id="ab195-158">Cómo agregar Functoids básicos a un mapa</span><span class="sxs-lookup"><span data-stu-id="ab195-158">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
-  <span data-ttu-id="ab195-159">**Referencia a Functoids acumulativos**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="ab195-159">**Cumulative Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>