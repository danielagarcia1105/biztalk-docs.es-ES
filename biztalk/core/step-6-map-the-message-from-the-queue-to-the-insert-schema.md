---
title: 'Paso 6 (local): Crear una transformación para asignar el mensaje de la cola en el esquema de inserción | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30a55f1e-32cc-409a-a814-084026f51b35
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae0bc6826bda147d4af6ccb47d81eb2513eea640
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981309"
---
# <a name="step-6-on-premises-create-a-transform-to-map-the-message-from-the-queue-to-the-insert-schema"></a>Paso 6 (local): Crear una transformación para asignar el mensaje de la cola en el esquema de inserción
El mensaje recibido por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde la cola de Service Bus será del **ECommerceSalesOrder.xsd** esquema. Sin embargo, para insertar un mensaje en el **SalesOrder** tabla, el mensaje debe ser de **insertar** esquema que ha generado en [(local) del paso 5: generar el esquema para insertar un mensaje en la Tabla SalesOrder](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md). Por lo tanto, en este tema, se creará una asignación para transformar el **ECommerceSalesOrder.xsd** esquema en el esquema de la operación de inserción.  

### <a name="to-create-a-map"></a>Para crear un mapa  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ya creado, haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. En el **nuevo elemento** cuadro de diálogo, seleccione **mapa**, escriba el nombre de asignación `SalesOrder_SQL.btm`y, a continuación, haga clic en **agregar**.  

2. En el mapa para el esquema de origen, seleccione **ECommerceSalesOrder.xsd**. El esquema de destino, seleccione **TableOperations.SalesOrder.xsd (Insert)** esquema.  

3. Asigne directamente los siguientes nodos en los esquemas de origen y de destino:  


   | Esquema de origen | Esquema de destino |
   |---------------|--------------------|
   |  CompanyCode  |    CompanyCode     |
   |    PartId     |      PartNum       |
   |   Cantidad    |        Qty         |
   |   AskPrice    |    UnitAskPrice    |
   |   Comentarios    |  CustomerComments  |


4. Use la **fecha y hora** functoid para asignar valores a la **DateRequested** y **ShipDate** elementos del esquema de destino. Estos nodos no se asignan a los nodos correspondientes en el esquema de origen. En su lugar, la fecha y hora actuales se pasa estos nodos mediante la **fecha y hora** functoid.  

   1.  Arrastre y coloque un **fecha y hora** functoid desde el cuadro de herramientas a la superficie del asignador.  

   2.  Conecte el functoid para el **DateRequested** elemento del esquema de destino.  

   3.  Arrastre y coloque otra **fecha y hora** functoid y conectarlo a la **ShipDate** elemento del esquema de destino.  

5. Asigne los siguientes nodos en los esquemas de origen y destino mediante un **concatenación de cadenas** functoid:  

   |Esquema de origen|Esquema de destino|  
   |-------------------|------------------------|  
   |Address\Line1|SellToAddress<br /><br /> BillToAddress|  
   |Address\Line2|SellToAddress<br /><br /> BillToAddress|  
   |Address\City|SellToAddress<br /><br /> BillToAddress|  
   |Address\State|SellToAddress<br /><br /> BillToAddress|  
   |Address\Country|SellToAddress<br /><br /> BillToAddress|  
   |Address\ZipCode|SellToAddress<br /><br /> BillToAddress|  
   |Contact\FirstName|PartnerContact|  
   |Contact\LastName||  

    Realice los siguientes pasos para cada uno de los conjuntos de asignación de concatenación de cadenas:  

   1.  Arrastre y coloque un **concatenación de cadenas** functoid desde el cuadro de herramientas a la superficie del asignador.  

   2.  Agregue cada elemento desde el árbol de origen como entrada para el **concatenación de cadenas** functoid.  

   3.  Arrastre y configurar la salida de la **concatenación de cadenas** functoid al elemento del esquema de destino.  

        El mapa completado queda de una forma similar a la siguiente:  

        ![Asignación para transformar los esquemas](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")  

## <a name="see-also"></a>Vea también  
 [Tutorial 4: Crear una aplicación híbrida con BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)