---
title: Configuración de bucle controlado por tablas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Extractor functoids, configuring
- Table Extractor functoids
- Table Extractor functoids, adding to grid
- Table Looping functoids, about Table Looping functoids
- Table Looping functoids, configuring
- Table Extractor functoids, about Table Extractor functoids
- Table Looping functoids, adding to map
ms.assetid: ecc24d9b-ebc0-4559-9746-58e3b00c02ab
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46e8368dd57b32eab98c1a1dc3432e5be2012363
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973013"
---
# <a name="table-driven-looping-configuration"></a>Configuración de bucle controlado por tablas
Siga estos pasos para configurar el bucle controlado por tablas en su asignación.  
  
- **Agregar un functoid de bucle de tabla a la asignación.** Solo necesita un **bucle de tabla** functoid por instancia de bucle controlado por tablas. Por ejemplo, si utiliza un bucle controlado por tablas para derivar la información de BillTo y ShipTo, solo necesita un **bucle de tabla** functoid en el mapa. Sin embargo, si utiliza un bucle controlado por tablas para derivar la información de BillTo y ShipTo e información StoreName y StoreAddress, puede que tenga dos **bucle de tabla** functoids en el mapa.  
  
- **Agregar un functoid de Extractor de tablas más a la página de cuadrícula mostrada.** Agregue tantas **Extractor de tablas** functoids que usted necesita para cada **bucle de tabla** functoid. El número de **Extractor de tablas** functoids depende del número de campos del esquema de destino. Por ejemplo, si solo tiene un **AddressCode** en el esquema de origen y CompanyName, dirección, ciudad, estado, PostalCode y AttentionName en el esquema de destino, deberá agregar seis **Extractor de tablas** functoids a la página de cuadrícula mostrada.  
  
- **Configure el functoid de bucle de tabla con las entradas apropiadas.** En primer lugar, vincule el **bucle de tabla** functoid a la instancia de entrada de registro o elemento. Vincúlelo además con la estructura del mensaje de instancia de salida. A continuación, configure las entradas mediante el uso de la **configurar \<Functoid\> Functoid** cuadro de diálogo. Para obtener más información sobre cómo configurar esta propiedad, vea [editar propiedades de Functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md) . La lista de entradas que escriba debe ser completa porque se trata de los datos que se utilizará para configurar el **cuadrícula del Functoid de tabla** propiedad. Las entradas deben definirse de la siguiente manera:  
  
  -   **Primera entrada.** El parámetro de primera entrada es el vínculo con el campo o registro de mensaje de instancia de entrada. El **bucle de tabla** functoid se repite una vez por cada instancia del registro o campo.  
  
      > [!NOTE]
      >  Esta es una entrada obligatoria.  
  
  -   **Segunda entrada.** El segundo parámetro de entrada define el número de columnas que hay en la cuadrícula del bucle. La cuadrícula puede tener un máximo de 228 columnas.  
  
      > [!NOTE]
      >  Esta es una entrada obligatoria.  
  
  -   **Entradas restantes.** Las restantes entradas para el **bucle de tabla** functoid constan de una lista de todos los valores posibles que pueden aparecer en el **cuadrícula del Functoid de tabla**.  
  
      > [!NOTE]
      >  Nombrar los vínculos puede ser de gran utilidad. Sin etiquetas, los vínculos aparecen en la **cuadrícula del Functoid de tabla** como rutas totalmente especificadas.  
  
       Para obtener instrucciones paso a paso sobre cómo configurar las entradas para el **bucle de tabla** functoid, consulte [cómo agregar el bucle de tabla y los Functoids de Extractor de tabla a un mapa](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md). En concreto, vea los pasos del 3 al 8.  
  
- **Configurar la propiedad de cuadrícula del Functoid de tabla del functoid de bucle de tabla.** Use la **cuadrícula del Functoid de tabla** propiedad para abrir el **configurar Functoid de bucle de tabla** cuadro de diálogo en el que se configuran las celdas en la cuadrícula de bucle.  
  
   Para obtener instrucciones paso a paso sobre cómo configurar la cuadrícula de bucle, consulte [cómo agregar el bucle de tabla y los Functoids de Extractor de tabla a un mapa](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md). En concreto, vea los pasos del 9 al 10.  
  
- **Configure los functoids de Extractor de tablas.** Use la **parámetros de entrada** propiedad para configurar el **Extractor de tablas** entradas de functoid como sigue:  
  
  - **Primera entrada.** El primer parámetro de entrada a un **Extractor de tablas** functoid es el **bucle de tabla** functoid.  
  
  - **Segunda entrada.** El segundo parámetro de entrada especifica la columna de la fila de la que se van a extraer datos.  
  
    Para obtener instrucciones paso a paso sobre cómo configurar el **Extractor de tablas** functoids asociados con un **bucle de tabla** functoid, vea [cómo agregar el bucle de tabla y Extractor de tablas Functoids a una asignación](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md). En concreto, vea los pasos 11 a 16.  
  
## <a name="see-also"></a>Vea también  
 [Functoid de bucle de tabla](../core/table-looping-functoid.md)   
 [Functoid Extractor de tablas](../core/table-extractor-functoid.md)   
 [Ejemplo de bucle controlado por tablas](../core/table-driven-looping-example.md)   
 [Adición de bucle de tabla y los Functoids de Extractor de tabla a un mapa](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [Functoids avanzados](../core/advanced-functoids.md)   
 [Functoid de índice](../core/index-functoid.md)   
 [Functoid de iteración](../core/iteration-functoid.md)   
 [Functoid de bucle](../core/looping-functoid.md)   
 [Functoid de número de registros](../core/record-count-functoid.md)