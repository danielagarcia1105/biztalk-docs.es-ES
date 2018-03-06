---
title: "Asignaciones básicas y complejas operaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da864b48-6255-4847-9a6f-13e489e8658d
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82876310cfa497f8002e7df680281122e90884af
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="basic-and-complex-mapping-operations"></a><span data-ttu-id="522f4-102">Operaciones de asignaciones básicas y complejas</span><span class="sxs-lookup"><span data-stu-id="522f4-102">Basic and Complex Mapping Operations</span></span>
<span data-ttu-id="522f4-103">El Asignador de BizTalk proporciona soluciones para una serie de escenarios de asignaciones que van desde simples operaciones de tipo árbol primario-secundario hasta operaciones complejas y detalladas en las que hay registros de bucles y jerarquías.</span><span class="sxs-lookup"><span data-stu-id="522f4-103">BizTalk Mapper provides solutions for a variety of mapping scenarios ranging from simple parent-child tree-type operations to detailed, complex operations involving looping records and hierarchies.</span></span> <span data-ttu-id="522f4-104">La complejidad de un escenario de asignación depende de sus preferencias y necesidades empresariales: lenguaje de definición (XSD) de esquemas XML proporciona gran flexibilidad para definir formatos estructurados.</span><span class="sxs-lookup"><span data-stu-id="522f4-104">The complexity of a mapping scenario depends on your preferences and business needs—XML Schema definition (XSD) language gives you considerable flexibility in defining structured formats.</span></span> <span data-ttu-id="522f4-105">Casi todos los escenarios de asignación se dividen en dos categorías: asignación básica y asignación compleja.</span><span class="sxs-lookup"><span data-stu-id="522f4-105">Almost all mapping scenarios fall into one of two categories: basic mapping and complex mapping.</span></span>  
  
## <a name="basic-mapping"></a><span data-ttu-id="522f4-106">Asignación básica</span><span class="sxs-lookup"><span data-stu-id="522f4-106">Basic Mapping</span></span>  
 <span data-ttu-id="522f4-107">La asignación básica es el tipo más común de asignación que se puede crear.</span><span class="sxs-lookup"><span data-stu-id="522f4-107">Basic mapping is the most common type of mapping you can create.</span></span> <span data-ttu-id="522f4-108">En una asignación básica, los elementos de entrada y salida tienen una relación de uno a uno.</span><span class="sxs-lookup"><span data-stu-id="522f4-108">In a basic map, input and output items have a one-to-one relationship.</span></span> <span data-ttu-id="522f4-109">Un elemento de entrada se asigna a un único elemento de salida.</span><span class="sxs-lookup"><span data-stu-id="522f4-109">An input item maps to one and only one output item.</span></span> <span data-ttu-id="522f4-110">Aunque muchos tipos de transformaciones y traducciones son posibles con la asignación básica, como el uso de varios *functoids* y functoids en cascada para manipular el valor que se está copiando, el escenario subyacente resulta relativamente simple.</span><span class="sxs-lookup"><span data-stu-id="522f4-110">Although many types of transformations and translations are possible with basic mapping, such as using multiple *functoids* and cascading functoids to manipulate the value being copied, the underlying scenario remains relatively simple.</span></span> <span data-ttu-id="522f4-111">Las operaciones de asignación básica también incluyen la asignación de campos de dos registros primarios diferentes (que solo ocurren una vez) a campos bajo un solo registro primario en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="522f4-111">Basic mapping operations also include mapping fields from two different parent records (occurring only once) to fields under a single parent record in the destination schema.</span></span>  
  
## <a name="complex-mapping"></a><span data-ttu-id="522f4-112">Asignación compleja</span><span class="sxs-lookup"><span data-stu-id="522f4-112">Complex Mapping</span></span>  
 <span data-ttu-id="522f4-113">Asignación compleja implica registros o campos que aparecen varias veces para una única instancia de la **registro** o **elemento de campo** nodo en el árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="522f4-113">Complex mapping involves records or fields that occur multiple times for a single instance of the **Record** or **Field Element** node in the schema tree.</span></span> <span data-ttu-id="522f4-114">Tales nodos tienen sus **Max Occurs** propiedad establecida en un valor mayor que uno (1), que indica la puede haber más de un elemento correspondiente en un mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="522f4-114">Such nodes have their **Max Occurs** property set to a value greater than one (1), indicating there may be more than one corresponding element in an instance message.</span></span> <span data-ttu-id="522f4-115">Cuando una asignación de BizTalk utiliza este tipo de asignación de variable de número (también conocido como *bucle*), el compilador de hoja de estilos Extensible Stylesheet Language (XSL) debe ser capaz de determinar la ruta de acceso adecuada del bucle que se recorre para generar la salida requerida.</span><span class="sxs-lookup"><span data-stu-id="522f4-115">When a BizTalk map uses this type of variable count mapping (also known as *looping*), the Extensible Stylesheet Language (XSL) style sheet compiler must be able to determine the proper loop path over which to iterate to produce the required output.</span></span>  
  
 <span data-ttu-id="522f4-116">En general, puede vincular un campo de un registro de bucle del esquema de origen con un campo de un registro de bucle del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="522f4-116">In general, you can link a field in a looping record in the source schema to a field in a looping record in the destination schema.</span></span> <span data-ttu-id="522f4-117">El número de elementos correspondientes en un mensaje de instancia de entrada determina el número de elementos que se han creado en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="522f4-117">The number of corresponding elements in an input instance message determines the number of elements created in the output instance message.</span></span> <span data-ttu-id="522f4-118">Fíjese en los siguientes fragmentos XSD de esquemas de ejemplo de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="522f4-118">Consider the following XSD fragments from example source and destination schemas.</span></span>  
  
### <a name="source-schema-fragment"></a><span data-ttu-id="522f4-119">Fragmento de esquema de origen</span><span class="sxs-lookup"><span data-stu-id="522f4-119">Source Schema Fragment</span></span>  
  
```  
<xs:element minOccurs="1" maxOccurs="5"  
            name="SrcLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
  
```  
  
### <a name="destination-schema-fragment"></a><span data-ttu-id="522f4-120">Fragmento de esquema de destino</span><span class="sxs-lookup"><span data-stu-id="522f4-120">Destination Schema Fragment</span></span>  
  
```  
<xs:element minOccurs="0" maxOccurs="unbounded"  
            name="DstLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  
```  
  
 <span data-ttu-id="522f4-121">En estos fragmentos:</span><span class="sxs-lookup"><span data-stu-id="522f4-121">In these fragments:</span></span>  
  
-   <span data-ttu-id="522f4-122">**SrcLoopingRecord**, **registro** nodo en los mensajes de instancia de entrada, puede aparecer entre uno y cinco veces.</span><span class="sxs-lookup"><span data-stu-id="522f4-122">**SrcLoopingRecord**, a **Record** node in input instance messages, can occur from one to five times.</span></span> <span data-ttu-id="522f4-123">También contiene el elemento secundario **elemento de campo** nodos **Field1** (una cadena) y **Field2** (un entero) que ocurren una vez para cada instancia de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="522f4-123">It also contains the child **Field Element** nodes **Field1** (a string) and **Field2** (an integer) that occur once for each instance of their parent.</span></span>  
  
-   <span data-ttu-id="522f4-124">**DstLoopingRecord**, **registro** nodo en los mensajes de instancia de salida, puede aparecer cero (0) o más veces, sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="522f4-124">**DstLoopingRecord**, a **Record** node in output instance messages, can occur zero (0) or more times, unbounded.</span></span> <span data-ttu-id="522f4-125">También contiene el elemento secundario **elemento de campo** nodos **FieldA** (una cadena) y **FieldB** (un entero) que ocurren una vez para cada instancia de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="522f4-125">It also contains the child **Field Element** nodes **FieldA** (a string) and **FieldB** (an integer) that occur once for each instance of their parent.</span></span>  
  
 <span data-ttu-id="522f4-126">Suponiendo que Field1 está enlazado con FieldA y Field2 está enlazado con FieldB, y que el siguiente fragmento de un mensaje de instancia de entrada ha procesado esas asignaciones, se creará el siguiente fragmento de un mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="522f4-126">Assuming that Field1 is mapped to FieldA and Field2 is mapped to FieldB, and that the following fragment from an input instance message has processed those mappings, the following fragment from an output instance message would be produced.</span></span>  
  
### <a name="input-instance-message-fragment"></a><span data-ttu-id="522f4-127">Fragmento de mensaje de instancia de entrada</span><span class="sxs-lookup"><span data-stu-id="522f4-127">Input Instance Message Fragment</span></span>  
  
```  
<SrcLoopingRecord>  
    <Field1>A string</Field1>  
    <Field2>10</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>Another string</Field1>  
    <Field2>11</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>A ball of string</Field1>  
    <Field2>12</Field2>  
</SrcLoopingRecord>  
```  
  
### <a name="output-instance-message-fragment"></a><span data-ttu-id="522f4-128">Fragmento de mensaje de instancia de salida</span><span class="sxs-lookup"><span data-stu-id="522f4-128">Output Instance Message Fragment</span></span>  
  
```  
<DstLoopingRecord>  
    <FieldA>A string</FieldA>  
    <FieldB>10</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
  <FieldA>Another string</FieldA>  
  <FieldB>11</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
    <FieldA>A ball of string</FieldA>  
    <FieldB>12</FieldB>  
</DstLoopingRecord>  
```  
  
 <span data-ttu-id="522f4-129">El número de repeticiones de la **SrcLoopingRecord** elemento en el mensaje de instancia de entrada (3) determina el número de repeticiones de la **DstLoopingRecord** elemento en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="522f4-129">The number of occurrences of the **SrcLoopingRecord** element in the input instance message (3) determines the number of occurrences of the **DstLoopingRecord** element in the output instance message.</span></span>  
  
 <span data-ttu-id="522f4-130">Disponer de varias rutas de bucle es un tipo de asignación que no admite el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="522f4-130">A type of mapping not supported by BizTalk Mapper is the use of multiple loop paths.</span></span> <span data-ttu-id="522f4-131">Este tipo de asignación trabaja con campos de dos o más registros de bucle en el esquema de origen que está asignando a los campos dentro de un registro de bucle simple en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="522f4-131">This type of mapping involves fields from two or more looping records in the source schema being mapped to fields within a single looping record in the destination schema.</span></span> <span data-ttu-id="522f4-132">Esto presenta un problema, no hay ninguna manera eficaz de determinar el número de elementos que se va a producir en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="522f4-132">This presents a problem—there is no effective way to determine the number of elements to produce in the output instance message.</span></span> <span data-ttu-id="522f4-133">Varias rutas de bucle dan como resultado una advertencia de compilación de asignación que indica que el nodo de destino tiene varias rutas de bucle de origen.</span><span class="sxs-lookup"><span data-stu-id="522f4-133">Multiple loop paths result in a map compilation warning indicating that the destination node has multiple source loop paths.</span></span> <span data-ttu-id="522f4-134">Sin embargo, esto no es más que una advertencia, y el número de iteraciones en la primera ruta del bucle de origen se utiliza para determinar el número de elementos que se producen en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="522f4-134">However, this is only a warning, and the number of iterations in the first source loop path is used to determine the number of elements produced in the output instance message.</span></span> <span data-ttu-id="522f4-135">Puede tomar el control explícito de bucle comportamiento mediante el uso de la **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="522f4-135">You can take explicit control of looping behavior by using the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="522f4-136">Microsoft BizTalk Server integra a un nuevo tipo de bucle denominado bucle controlado por la tabla.</span><span class="sxs-lookup"><span data-stu-id="522f4-136">Microsoft BizTalk Server introduced a new kind of looping called table-driven looping.</span></span> <span data-ttu-id="522f4-137">El bucle controlado por tablas es útil cuando el mensaje de instancia de salida necesita basarse en datos del mensaje de instancia de entrada en combinación con una o más constantes, vínculos del esquema de origen o functoids.</span><span class="sxs-lookup"><span data-stu-id="522f4-137">Table-driven looping is useful when your output instance message needs to be based on data from the input instance message, combined with one or more constants, links from the source schema, or functoids.</span></span> <span data-ttu-id="522f4-138">En tales casos, el mensaje de instancia de salida puede tener varios registros basándose en los datos de un registro simple en el mensaje de instancia de entrada que se combina con distintas constantes o basándose en datos procedentes de varios registros en el mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="522f4-138">In such cases, the output instance message can have multiple records based on data from a single record in the input instance message that is combined with different constants, or based on data coming from multiple records in the input instance message.</span></span> <span data-ttu-id="522f4-139">Para obtener más información acerca de controlado por tablas bucle con el **bucle de tabla** y **Extractor de tablas** functoids, consulte [bucle de tabla y Functoids de Extractor de tabla](../core/table-looping-and-table-extractor-functoids.md).</span><span class="sxs-lookup"><span data-stu-id="522f4-139">For more information about table-driven looping using the **Table Looping** and **Table Extractor** functoids, see [Table Looping and Table Extractor Functoids](../core/table-looping-and-table-extractor-functoids.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="522f4-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="522f4-140">See Also</span></span>  
 <span data-ttu-id="522f4-141">[Mapas](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="522f4-141">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="522f4-142">Crear asignaciones usando al asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="522f4-142">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)