---
title: Referencia | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b916c55a-c84c-4008-8927-f8e584c36fe9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3e32145e2340a4d86a6893db3e9209b79c2b5e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="reference"></a><span data-ttu-id="ad6a0-102">Referencia</span><span class="sxs-lookup"><span data-stu-id="ad6a0-102">Reference</span></span>
<span data-ttu-id="ad6a0-103">El **referencia** elemento se puede usar para agregar una o varias relaciones a una actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-103">The **Reference** element can be used to add one or more relationships to a BAM activity.</span></span> <span data-ttu-id="ad6a0-104">Resulta útil cuando se desea adjuntar un puntero como una clave principal, un Id. o una URL a un mensaje relacionado.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-104">This is useful when you want to attach a pointer like a primary key, ID, or URL to a related message.</span></span> <span data-ttu-id="ad6a0-105">Por ejemplo, podría almacenar una referencia a un lote de envío en una actividad de pedido.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-105">For example, you might store a reference to a Shipment Batch in a Purchase Order activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="ad6a0-106">Formato</span><span class="sxs-lookup"><span data-stu-id="ad6a0-106">Format</span></span>  
 <span data-ttu-id="ad6a0-107">El `Reference` elemento admite tanto la **datos** y **LongData** los elementos secundarios que contienen una expresión que especifica los datos que se va a asociar a la actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-107">The `Reference` element supports both the **Data** and **LongData** child elements that contain an expression specifying the data to attach to the BAM activity.</span></span> <span data-ttu-id="ad6a0-108">Puede usar cualquier combinación de **datos** y **LongData** para satisfacer los requisitos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-108">You can use any combination of **Data** and **LongData** to meet your tracking requirements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad6a0-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ad6a0-109">Attributes</span></span>  
  
|<span data-ttu-id="ad6a0-110">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="ad6a0-110">Attribute name</span></span>|<span data-ttu-id="ad6a0-111">Description</span><span class="sxs-lookup"><span data-stu-id="ad6a0-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="ad6a0-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="ad6a0-112">Name</span></span>|<span data-ttu-id="ad6a0-113">Nombre de la relación que se adjuntará a la actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-113">Name of the relationship that will be attached to the BAM activity.</span></span>|  
|<span data-ttu-id="ad6a0-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="ad6a0-114">Type</span></span>|<span data-ttu-id="ad6a0-115">Cadena arbitraria que especifica el tipo de relación que se adjuntará a la actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-115">Arbitrary string specifying the type of relationship that will be attached to the BAM activity.</span></span> <span data-ttu-id="ad6a0-116">Se admiten las cadenas arbitrarias y los siguientes tipos de BAM predefinidos:</span><span class="sxs-lookup"><span data-stu-id="ad6a0-116">Both arbitrary strings and the following predefined BAM types are supported:</span></span><br /><br /> <span data-ttu-id="ad6a0-117">-BizTalkService</span><span class="sxs-lookup"><span data-stu-id="ad6a0-117">-   BizTalkService</span></span><br /><span data-ttu-id="ad6a0-118">-MessageID</span><span class="sxs-lookup"><span data-stu-id="ad6a0-118">-   MessageID</span></span><br /><span data-ttu-id="ad6a0-119">-Activity</span><span class="sxs-lookup"><span data-stu-id="ad6a0-119">-   Activity</span></span><br /><span data-ttu-id="ad6a0-120">-DocumentUrl</span><span class="sxs-lookup"><span data-stu-id="ad6a0-120">-   DocumentUrl</span></span><br /><span data-ttu-id="ad6a0-121">-InstanceID</span><span class="sxs-lookup"><span data-stu-id="ad6a0-121">-   InstanceID</span></span><br /><br /> <span data-ttu-id="ad6a0-122">Para obtener más información sobre tipos de referencia BAM predefinidos, vea [propiedades de la referencia](http://go.microsoft.com/fwlink/?LinkId=119601).</span><span class="sxs-lookup"><span data-stu-id="ad6a0-122">For more information on predefined BAM reference types, see [Reference Properties](http://go.microsoft.com/fwlink/?LinkId=119601).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad6a0-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ad6a0-123">Child Elements</span></span>  
  
|<span data-ttu-id="ad6a0-124">Estado de ejecución</span><span class="sxs-lookup"><span data-stu-id="ad6a0-124">Execution status</span></span>|<span data-ttu-id="ad6a0-125">Description</span><span class="sxs-lookup"><span data-stu-id="ad6a0-125">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="ad6a0-126">data</span><span class="sxs-lookup"><span data-stu-id="ad6a0-126">Data</span></span>|<span data-ttu-id="ad6a0-127">Especifica cómo extraer los datos de la cadena hasta 128 caracteres que se adjuntará a la actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-127">Specifies how to extract string data up to 128 characters that will be attached to the BAM activity.</span></span>|  
|<span data-ttu-id="ad6a0-128">LongData</span><span class="sxs-lookup"><span data-stu-id="ad6a0-128">LongData</span></span>|<span data-ttu-id="ad6a0-129">Especifica cómo extraer los datos de cadenas largas arbitrariamente que se adjuntarán a la actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-129">Specifies how to extract arbitrarily long string data that will be attached to the BAM activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ad6a0-130">A `Reference` elemento puede combinar uno o varios **datos** y **LongData** los elementos secundarios según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-130">A `Reference` element can combine one or more **Data** and **LongData** child elements as needed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad6a0-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad6a0-131">Remarks</span></span>  
 <span data-ttu-id="ad6a0-132">En expresiones de Reference, no se permiten las operaciones comunes siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad6a0-132">The following common operations are not allowed in Reference expressions:</span></span>  
  
-   <span data-ttu-id="ad6a0-133">And</span><span class="sxs-lookup"><span data-stu-id="ad6a0-133">And</span></span>  
  
-   <span data-ttu-id="ad6a0-134">Es igual a</span><span class="sxs-lookup"><span data-stu-id="ad6a0-134">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad6a0-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad6a0-135">Example</span></span>  
 <span data-ttu-id="ad6a0-136">En el ejemplo siguiente, se crea una referencia con el nombre "Related Document" de tipo "DocumentUrl" por medio de `GetUserData` para un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-136">In the following sample, a reference named "Related Document" of type "DocumentUrl" is created using `GetUserData` for a workflow.</span></span> <span data-ttu-id="ad6a0-137">Puesto que se espera que los datos del usuario sean inferiores a 1024 caracteres de longitud, el elemento `Data` se usa para contener el elemento `Expression`.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-137">Because the user data is expected to be fewer than 1024 characters in length, the `Data` element is used to contain the `Expression` element.</span></span>  
  
```  
<ic:Reference Name="Related Document" Type="DocumentUrl">  
  <ic:Data>  
    <ic:Expression>  
      <wf:Operation Name="GetUserData" />  
    </ic:Expression>  
  </ic:Data>  
</ic:Reference>  
```  
  
 <span data-ttu-id="ad6a0-138">El **referencia** elemento admite una combinación de `Data` y `LongData` elementos.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-138">The **Reference** element supports a mix of `Data` and `LongData` elements.</span></span> <span data-ttu-id="ad6a0-139">En el ejemplo siguiente, los campos del nombre del país y de notas de un pedido se recuperan de un Servicio WCF y se escriben en la relación "Long and Short Data" como tipo "MyType".</span><span class="sxs-lookup"><span data-stu-id="ad6a0-139">In the following sample, the country name and note fields from a purchase order are retrieved from a WCF service and written to the relationship "Long and Short Data" as type "MyType".</span></span> <span data-ttu-id="ad6a0-140">Puesto que el campo de nota admite más de 1024 caracteres, la expresión aparece en un elemento `LongData`.</span><span class="sxs-lookup"><span data-stu-id="ad6a0-140">Because the note field supports more than 1024 characters, the expression is enclosed in a `LongData` element.</span></span>  
  
```  
<ic:Reference Name="Long and Short Data" Type="MyType">  
  <ic:Data>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Country: </ic:Argument>  
      </ic:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body//po:Country</wcf:Argument>  
      </wcf:Operation>  
       <ic:Operation Name="Concatenate" />  
    </ic:Expression>  
  </ic:Data>  
  <ic:LongData>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Note: </ic:Argument>  
      </ic:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body//po:Note</wcf:Argument>  
      </wcf:Operation>  
      <ic:Operation Name="Concatenate" />  
    </ic:Expression>  
  </ic:LongData>  
</ic:Reference>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad6a0-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad6a0-141">See Also</span></span>  
 <span data-ttu-id="ad6a0-142">[Elemento OnEvent del interceptor](../core/interceptor-onevent-element.md) </span><span class="sxs-lookup"><span data-stu-id="ad6a0-142">[Interceptor OnEvent Element](../core/interceptor-onevent-element.md) </span></span>  
 [<span data-ttu-id="ad6a0-143">Método EventStream.AddRelatedActivity</span><span class="sxs-lookup"><span data-stu-id="ad6a0-143">EventStream.AddRelatedActivity Method</span></span>](http://go.microsoft.com/fwlink/?LinkId=119602)