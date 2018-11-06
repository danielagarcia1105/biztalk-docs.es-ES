---
title: Usar campos distintivos y campos de propiedades | Microsoft Docs
description: Obtenga información acerca de las diferencias entre los conjuntos de propiedades, campos distintivos y campos de propiedades. Los campos distintivos utilizan la ruta de acceso en el campo de mensaje, los campos de propiedades que se usa el nombre del mensaje y el espacio de nombres de esquema y conjuntos de propiedades asignación las propiedades de contexto de un mensaje (un conjunto de propiedades) a las propiedades de contexto de otro mensaje de BizTalk Server
ms.custom: ''
ms.date: 05/02/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 264ee15e-be9a-4ba2-9c61-a1570b20378e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd58f8b9e72f955bc02c5b7116469390468937d9
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752307"
---
# <a name="using-distinguished-fields-and-property-fields"></a>Usar campos distintivos y campos de propiedades
los campos distintivos son datos de mensaje de especial interés que se usan principalmente para tomar decisiones o manipular datos de la orquestación.  
  
 Propiedades de mensaje son datos: contenido del propio mensaje, o "metadata", información de contexto sobre el mensaje como marcas de tiempo o información de enrutamiento. Puede usar propiedades de contexto de transporte o mensaje definidas por el sistema o bien puede definir sus propias propiedades mediante la referencia a campos de esquema desde un esquema de propiedades. Las propiedades se usan en suscripciones y correlaciones.  
  
-   Puede designar un campo en un esquema como campo distintivo o campo de propiedad mediante la **promocionar propiedades** cuadro de diálogo en el Editor. Para obtener más información, consulte [promocionar propiedades](../core/promoting-properties.md)  
  
-   Puede designar un campo en un tipo .NET como campo distintivo al decorarlo con el atributo DistinguishedField o como propiedad con el atributo Property.  
  
## <a name="using-distinguished-fields"></a>Usar campos distintivos  
 Los campos distintivos se denominan mediante la ruta al campo en el mensaje, con puntos para separar el nombre del mensaje, los nombres de los registros que cierran el campo y el propio nombre del campo:  
  
```  
MyMessage.MyRecord.MySubrecord.MyDistinguishedField  
```  
  
## <a name="using-property-fields"></a>Usar campos de propiedades  
 Una vez que ha agregado un campo a un esquema de propiedades, se puede tener acceso a su valor en la orquestación con código y en expresiones de filtro. Para obtener más información acerca de los esquemas de propiedad, vea [esquemas de propiedad](../core/property-schemas.md).  
  
> [!NOTE]
>  Propiedades de contenido o los datos de mensajes son esencialmente accesos directos a los datos subyacentes: si modifica la propiedad, se modificarán los datos y viceversa.  
  
 Las propiedades de los mensajes se denominan mediante el nombre del mensaje seguido del espacio de nombres (el esquema) y el nombre de la propiedad entre paréntesis:  
  
```  
MyMessage(Invoice.PropertySchema.InvoiceID)  
```  
  
> [!NOTE]
>  Cuando utiliza una palabra clave reservada como el nombre de un campo en un esquema y promocionar el campo seleccionando promoción rápida, el nombre del campo de propiedad se cambia a __\<palabra clave reservada\>. (El subrayado doble se agrega delante del nombre de la propiedad.) Sin embargo, si usa este nombre de propiedad en una expresión de orquestación, recibirá un error del compilador al crear la orquestación.  Para solucionar este error, deberá agregar manualmente \@ delante del subrayado doble. Por ejemplo,  
>   
>  `MyMessage(Invoice.PropertySchema.@__Name) = "Product Name";`  
  
## <a name="property-sets"></a>Conjuntos de propiedades  
 También puede asignar todas las propiedades de contexto de un mensaje (un conjunto de propiedades) a las propiedades de contexto de otro mensaje. Para asignar un conjunto de propiedades, basta con colocar un asterisco entre paréntesis después de los dos nombres de mensaje, igual que si colocara una propiedad entre paréntesis:  
  
```  
MyMessage2(*)=MyMessage1(*);  
```  
  
 Después de que el conjunto de propiedades se ha asignado a MyMessage2 en el ejemplo, todas las propiedades en MyMessage2 contienen los mismos valores que las propiedades en MyMessage1.  
  
## <a name="see-also"></a>Vea también  
 [Promoción de propiedades](../core/promoting-properties.md)   
 [Uso de filtros con la forma recibir mensaje](../core/using-filters-with-the-receive-message-shape.md)   
 [Uso de los mensajes en orquestaciones](../core/using-messages-in-orchestrations.md)   
 [Propiedades de contexto de mensaje de BizTalk](../core/about-biztalk-message-context-properties.md)
