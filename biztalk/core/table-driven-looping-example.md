---
title: Ejemplo de bucle controlado por tablas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Table Extractor functoids, code sample
- Table Looping functoids
- Table Extractor functoids
- Table Looping functoids, about Table Looping functoids
- Table Extractor functoids, about Table Extractor functoids
- code samples, Table Looping functoids
- Table Looping functoids, code sample
- code samples, Table Extractor functoids
ms.assetid: d890bdb1-12a6-4001-9748-737b1f2bab79
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6989ac7e64cf28784d08f26aaf9e7af3a166a28
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="table-driven-looping-example"></a><span data-ttu-id="2cfc4-102">Ejemplo de bucle controlado por tablas</span><span class="sxs-lookup"><span data-stu-id="2cfc4-102">Table-Driven Looping Example</span></span>
<span data-ttu-id="2cfc4-103">Esta sección describen brevemente una asignación que utiliza el **bucle de tabla** y **Extractor de tablas** functoids.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-103">This section briefly describes a map using the **Table Looping** and **Table Extractor** functoids.</span></span> <span data-ttu-id="2cfc4-104">Para obtener información detallada acerca de la selección, colocación, vinculación y configuración de los functoids, consulte [cómo agregar Functoids de bucle y tabla extractor de tablas a un mapa](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span><span class="sxs-lookup"><span data-stu-id="2cfc4-104">For detailed information about selecting, placing, linking, and configuring the functoids, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span>  
  
 <span data-ttu-id="2cfc4-105">Suponga que tiene una lista de direcciones que necesita utilizar en un documento que requiera distintas direcciones de envío y de facturación.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-105">Suppose you have a list of addresses that you need to use in a document requiring separate ship-to and bill-to addresses.</span></span> <span data-ttu-id="2cfc4-106">Las direcciones podrían ser similares al siguiente código.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-106">The addresses might appear like the following code.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://TableLoopingSample.Addresses">  
    <Address>  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City>  
        <State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address>  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
</ns0:Root>  
```  
  
 <span data-ttu-id="2cfc4-107">Una manera de expresar el resultado sería el siguiente código, en el que las direcciones están duplicadas pero se han marcado con distintos atributos.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-107">One form the output could take would be the following code, duplicating the addresses but marking them with attributes.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://TableLoopingSample.POAddresses">  
    <Address Type="ShipTo">  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City>  
        <State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address Type="BillTo">  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City><State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address Type="ShipTo">  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
    <Address Type="BillTo">  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
</ns0:Root>  
```  
  
 <span data-ttu-id="2cfc4-108">`The following figure shows a map using the`  **Tabla** **bucle**`functoid and`**tabla** **extractor de tablas**   `functoids to generate the desired output instance message.`</span><span class="sxs-lookup"><span data-stu-id="2cfc4-108">`The following figure shows a map using the`  **Table** **Looping**  `functoid and`  **Table** **Extractor**  `functoids to generate the desired output instance message.`</span></span>  
  
 <span data-ttu-id="2cfc4-109">![El functoid de bucle de tabla y Extractor de tablas se asignan](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")</span><span class="sxs-lookup"><span data-stu-id="2cfc4-109">![Map the Table Looping and Table Extractor functoid](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")</span></span>  
<span data-ttu-id="2cfc4-110">Functoids de bucle de tabla y de extractor de tablas</span><span class="sxs-lookup"><span data-stu-id="2cfc4-110">TableLooping and Extractor Functoids</span></span>  
  
 <span data-ttu-id="2cfc4-111">Tenga en cuenta que la **bucle de tabla** vínculos de functoid para el elemento de nivel de registro en los esquemas de entrada y salidos.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-111">Notice that the **Table Looping** functoid links to the record-level element in both the input and output schemas.</span></span> <span data-ttu-id="2cfc4-112">El vínculo asegura la creación de la estructura envolvente y por lo tanto la creación de elementos dentro del registro.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-112">The link ensures the creation of the enclosing structure and, thus, the creation of the elements within the record.</span></span> <span data-ttu-id="2cfc4-113">Observe también que hay un **Extractor de tablas** functoid para cada campo en el esquema de salida.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-113">Also notice that there is one **Table Extractor** functoid for each field in the output schema.</span></span>  
  
 <span data-ttu-id="2cfc4-114">El vínculo con el registro en el esquema de entrada es el primer parámetro de la **configurar \<Functoid\> Functoid**cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-114">The link to the record in the input schema is the first parameter in the **Configure \<Functoid\> Functoid**dialog box.</span></span>  
  
 <span data-ttu-id="2cfc4-115">El segundo parámetro es el número de columnas en la tabla de la cuadrícula del functoid: una columna para el tipo de dirección, nombre, calle, ciudad, estado y código postal.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-115">The second parameter is the number of columns in the grid table of the functoid: one column each for the address type, name, street, city, state, and postal code.</span></span> <span data-ttu-id="2cfc4-116">Después del segundo parámetro, se encuentra una lista con todos los valores que pueden aparecer en la tabla de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-116">Following the second parameter is a list of all of the values that may appear in the grid table.</span></span> <span data-ttu-id="2cfc4-117">Entre los que se incluyen las constantes de las cadenas para el tipo de dirección ("ShipTo", "BillTo"), así como vínculos a los campos de la dirección.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-117">These include string constants for the address type ("ShipTo", "BillTo"), as well as links to the fields of the address.</span></span> <span data-ttu-id="2cfc4-118">Observe que los vínculos de los campos de dirección tienen nombres.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-118">Notice that the links to the address fields have names.</span></span> <span data-ttu-id="2cfc4-119">Al darles nombres a estos vínculos se simplifica la construcción de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-119">Naming the links in the map simplifies constructing the table.</span></span> <span data-ttu-id="2cfc4-120">En caso contrario, aparecen rutas completas en el **configurar Functoid de bucle de tabla** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-120">Otherwise, full paths appear in the **Configure Table Looping Functoid** dialog box.</span></span>  
  
 <span data-ttu-id="2cfc4-121">Después de haber configurado el **bucle de tabla** functoid, puede construir la tabla mediante el **configurar Functoid de bucle de tabla** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-121">After you have configured the **Table Looping** functoid, you can construct the table using the **Configure Table Looping Functoid** dialog box.</span></span> <span data-ttu-id="2cfc4-122">El cuadro de diálogo aparece al hacer clic en el botón de puntos suspensivos (**...** ) asociado a la **cuadrícula de bucle de tabla** propiedad en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-122">The dialog appears when you click the ellipsis (**…**) button associated with the **Table Looping Grid** property in the **Properties** window.</span></span>  
  
 <span data-ttu-id="2cfc4-123">Observe que hay seis columnas como se especifica en el **configurar Functoid de bucle de tabla** cuadro de diálogo: una columna para cada campo en el esquema de salida.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-123">Notice that there are six columns as specified in the **Configure Table Looping Functoid** dialog: one column for each field in the output schema.</span></span> <span data-ttu-id="2cfc4-124">La lista desplegable muestra los posibles valores para un campo, también según lo especificado por el tercer parámetro y siguientes en la **configurar Functoid de bucle de tabla** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-124">The dropdown shows the possible values for a field, also as specified by the third and following parameters in the **Configure Table Looping Functoid** dialog.</span></span> <span data-ttu-id="2cfc4-125">La tabla tiene dos filas, una para cada tipo de registro del esquema de salida.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-125">The table has two rows, one for each type of record in the output schema.</span></span> <span data-ttu-id="2cfc4-126">Al haber dos filas, esta asignación crea dos registros por cada registro de entrada.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-126">Because there are two rows, this map produces two records for every input record.</span></span> <span data-ttu-id="2cfc4-127">Si hubiera cuatro filas, habría cuatro registros de salida por cada registro de entrada.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-127">If there were four rows, there would be four output records for each input record.</span></span>  
  
 <span data-ttu-id="2cfc4-128">Como el **bucle de tabla** functoid toma cada registro, rellena la tabla con los valores del registro y, a continuación, envía una fila a la vez a la **Extractor de tablas** functoids.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-128">As the **Table Looping** functoid takes each record, it fills in the table with the values from the record, and then sends one row at a time to the **Table Extractor** functoids.</span></span> <span data-ttu-id="2cfc4-129">El **Extractor de tablas** functoids cada extraer un valor de la fila de la tabla y la pasa al campo vinculado en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-129">The **Table Extractor** functoids each extract one value from the table row and pass it on to the linked field in the output instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cfc4-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cfc4-130">See Also</span></span>  
 <span data-ttu-id="2cfc4-131">[Functoid de bucle de tabla](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc4-131">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="2cfc4-132">[Functoid de Extractor de tablas](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc4-132">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="2cfc4-133">[Configuración de bucle controlado por tablas](../core/table-driven-looping-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc4-133">[Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md) </span></span>  
 <span data-ttu-id="2cfc4-134">[Cómo agregar el bucle de tabla y Functoids de Extractor de tabla a un mapa](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc4-134">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="2cfc4-135">[Functoids avanzados](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc4-135">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="2cfc4-136">[Functoid de índice](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc4-136">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="2cfc4-137">[Functoid de iteración](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc4-137">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="2cfc4-138">[Functoid de bucle](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc4-138">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="2cfc4-139">Functoid de número de registros</span><span class="sxs-lookup"><span data-stu-id="2cfc4-139">Record Count Functoid</span></span>](../core/record-count-functoid.md)