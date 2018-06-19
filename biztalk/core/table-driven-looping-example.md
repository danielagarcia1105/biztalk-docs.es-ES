---
title: Ejemplo de bucle controlado por tablas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6989ac7e64cf28784d08f26aaf9e7af3a166a28
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25974538"
---
# <a name="table-driven-looping-example"></a>Ejemplo de bucle controlado por tablas
Esta sección describen brevemente una asignación que utiliza el **bucle de tabla** y **Extractor de tablas** functoids. Para obtener información detallada acerca de la selección, colocación, vinculación y configuración de los functoids, consulte [cómo agregar Functoids de bucle y tabla extractor de tablas a un mapa](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).  
  
 Suponga que tiene una lista de direcciones que necesita utilizar en un documento que requiera distintas direcciones de envío y de facturación. Las direcciones podrían ser similares al siguiente código.  
  
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
  
 Una manera de expresar el resultado sería el siguiente código, en el que las direcciones están duplicadas pero se han marcado con distintos atributos.  
  
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
  
 `The following figure shows a map using the`  **Tabla** **bucle**`functoid and`**tabla** **extractor de tablas**   `functoids to generate the desired output instance message.`  
  
 ![El functoid de bucle de tabla y Extractor de tablas se asignan](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")  
Functoids de bucle de tabla y de extractor de tablas  
  
 Tenga en cuenta que la **bucle de tabla** vínculos de functoid para el elemento de nivel de registro en los esquemas de entrada y salidos. El vínculo asegura la creación de la estructura envolvente y por lo tanto la creación de elementos dentro del registro. Observe también que hay un **Extractor de tablas** functoid para cada campo en el esquema de salida.  
  
 El vínculo con el registro en el esquema de entrada es el primer parámetro de la **configurar \<Functoid\> Functoid**cuadro de diálogo.  
  
 El segundo parámetro es el número de columnas en la tabla de la cuadrícula del functoid: una columna para el tipo de dirección, nombre, calle, ciudad, estado y código postal. Después del segundo parámetro, se encuentra una lista con todos los valores que pueden aparecer en la tabla de la cuadrícula. Entre los que se incluyen las constantes de las cadenas para el tipo de dirección ("ShipTo", "BillTo"), así como vínculos a los campos de la dirección. Observe que los vínculos de los campos de dirección tienen nombres. Al darles nombres a estos vínculos se simplifica la construcción de la tabla. En caso contrario, aparecen rutas completas en el **configurar Functoid de bucle de tabla** cuadro de diálogo.  
  
 Después de haber configurado el **bucle de tabla** functoid, puede construir la tabla mediante el **configurar Functoid de bucle de tabla** cuadro de diálogo. El cuadro de diálogo aparece al hacer clic en el botón de puntos suspensivos (**...** ) asociado a la **cuadrícula de bucle de tabla** propiedad en el **propiedades** ventana.  
  
 Observe que hay seis columnas como se especifica en el **configurar Functoid de bucle de tabla** cuadro de diálogo: una columna para cada campo en el esquema de salida. La lista desplegable muestra los posibles valores para un campo, también según lo especificado por el tercer parámetro y siguientes en la **configurar Functoid de bucle de tabla** cuadro de diálogo. La tabla tiene dos filas, una para cada tipo de registro del esquema de salida. Al haber dos filas, esta asignación crea dos registros por cada registro de entrada. Si hubiera cuatro filas, habría cuatro registros de salida por cada registro de entrada.  
  
 Como el **bucle de tabla** functoid toma cada registro, rellena la tabla con los valores del registro y, a continuación, envía una fila a la vez a la **Extractor de tablas** functoids. El **Extractor de tablas** functoids cada extraer un valor de la fila de la tabla y la pasa al campo vinculado en el mensaje de instancia de salida.  
  
## <a name="see-also"></a>Vea también  
 [Functoid de bucle de tabla](../core/table-looping-functoid.md)   
 [Functoid de Extractor de tablas](../core/table-extractor-functoid.md)   
 [Configuración de bucle controlado por tablas](../core/table-driven-looping-configuration.md)   
 [Cómo agregar el bucle de tabla y Functoids de Extractor de tabla a un mapa](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [Functoids avanzados](../core/advanced-functoids.md)   
 [Functoid de índice](../core/index-functoid.md)   
 [Functoid de iteración](../core/iteration-functoid.md)   
 [Functoid de bucle](../core/looping-functoid.md)   
 [Functoid de número de registros](../core/record-count-functoid.md)