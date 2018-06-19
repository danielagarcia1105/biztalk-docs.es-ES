---
title: Promoción de propiedades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- properties, promoting
- promoting properties
- promoting properties, about promoting properties
ms.assetid: e1825028-7dd9-4eae-a383-4db12a83a402
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1c5ac3e6e9aeadccc4eaefcb1457821ef36a93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266428"
---
# <a name="promoting-properties"></a>Promoción de propiedades
Promoción de propiedades implica cualquier promoción **elemento de campo** o **atributo de campo** nodos en un esquema para que sea **campos distintivos** o **propiedad Campos**. También puede promocionar **registro** nodos como **campos de propiedades** si tienen contenido simple (**Content Type** propiedad de la **registro** nodo establecido en **SimpleContent**). Esta sección proporciona instrucciones paso a paso para promocionar nodos como **campos distintivos** o como **campos de propiedades**.  
  
 Para promover un **registro** (con contenido simple), **elemento de campo**, o **atributo de campo** nodo como un **campo de propiedad**, primero debe definir un tipo especial de esquema denominado esquema de propiedades. Esquemas de propiedad definen un conjunto no estructurado de **elemento de campo** nodos en el que se promueve **registro** (con contenido simple), **elemento de campo**, o  **Atributo de campo** nodos. Para obtener instrucciones paso a paso para crear un esquema de propiedades, vea [cómo crear esquemas de propiedad](../core/how-to-create-property-schemas.md).  
  
 Como alternativa, puede usar el **promoción rápida** característica, que se creará automáticamente y actualizar un esquema de propiedades individual cada vez que promocione un nuevo **elemento de campo**, **atributo de campo** , o **registro** (con contenido simple) nodo.  
  
> [!NOTE]
>  Puede promover un campo como un **campo distintivo** y un **campo de la propiedad**.  
  
> [!NOTE]
>  El **promoción rápida** característica modifica el esquema de propiedades mediante la inserción de una nueva propiedad con el nombre del nodo promocionado.  
  
> [!IMPORTANT]
>  No mueva ni cambie el nombre de un campo en el esquema después de haberlo promocionado. Al mover o cambiar el nombre de un campo del esquema, el Editor de BizTalk no actualiza el XPath que define la ubicación del campo promocionado.  
  
## <a name="xsd-and-clr-data-types"></a>Tipos de datos XSD y CLR  
 En algunos lugares, como en la promoción de propiedades, los tipos de datos XSD se promoción a tipos de datos CLR (Common Language Runtime). La siguiente tabla muestra los tipos de datos XSD que se pueden promocionar y los tipos de datos CLR correspondientes.  
  
|Tipo de datos XSD|Tipo de datos de CLR|  
|-------------------|-------------------|  
|anyURI|String|  
|Boolean|Boolean|  
|Byte|sbyte|  
|Date|DateTime|  
|dateTime|DateTime|  
|Decimal|Decimal|  
|Doble|Doble|  
|ENTITY|String|  
|Float|Único|  
|gDay|DateTime|  
|gMonth|DateTime|  
|gMonthDay|DateTime|  
|gYear|DateTime|  
|gYearMonth|DateTime|  
|ID|String|  
|IDREF|String|  
|int|Int32|  
|Integer|Decimal|  
|Lenguaje|String|  
|Nombre|String|  
|NCName|String|  
|negativeInteger|Decimal|  
|NMTOKEN|String|  
|nonNegativeInteger|Decimal|  
|nonPositiveInteger|Decimal|  
|normalizedString|String|  
|NOTATION|String|  
|positiveInteger|Decimal|  
|QName|String|  
|Short|Int16|  
|String|String|  
|Time|DateTime|  
|Token|String|  
|unsignedByte|Byte|  
|unsignedInt|UInt32|  
|unsignedShort|UInt16|  
  
> [!NOTE]
>  Los tipos de datos XSD de base64Binary, duration, ENTITES, hexBinary, IDREFS, long, NMTOKENS y unsignedLong no se admiten para promoción.  
  
## <a name="limitations-for-promoting-properties"></a>Limitaciones para promocionar propiedades  
 Al promocionar propiedades, tenga en cuenta lo siguiente:  
  
-   Las propiedades promocionadas no pueden poseer más de 256 caracteres de longitud, mientras que en las propiedades escritas no existe limitación.  
  
-   Las propiedades promocionadas se utilizan en el enrutamiento de mensajes y poseen un tamaño limitado por motivos de eficacia en su comparación y almacenamiento. Aunque las propiedades escritas no poseen limitaciones en el tamaño, el empleo de valores excesivamente grandes en el contexto puede afectar al rendimiento, ya que pueden procesarse y transmitirse con el mensaje. Los campos distintivos son los ejemplos de propiedades escritas.  
  
-   Los nodos registro nunca se pueden promocionar como **campos distintivos**.  
  
-   Las propiedades promocionadas se restringen a atributos o elementos que no son de repetición.  
  
-   No promocione a la misma propiedad campos que pertenezcan al mismo nodo raíz. Dichas promociones producen errores de compilación o de implementación.  
  
-   En un contexto de mensaje, hay algunas propiedades que no están disponibles, ya que no se han promocionado.  La propiedad BTS.ReceiveLocationName es de ese tipo. Si puede agregar un nuevo esquema de propiedad o un nuevo proyecto de BizTalk Server al desarrollo, es posible tener acceso a esa propiedad desde una orquestación.  
  
     Los valores de propiedades se identifican mediante el espacio de nombres de destino de propiedad y el nombre de la propiedad.  En el ejemplo siguiente se muestra cómo obtener acceso a la ubicación de recepción en el código.  
  
     `string receiveLocationName =       pInMsg.Context.Read("ReceiveLocationName", sysNamespace);`  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo abrir el cuadro de diálogo de propiedades promocionar](../core/how-to-open-the-promote-properties-dialog-box.md)  
  
-   [Cómo copiar los datos en el contexto del mensaje como campos distintivos](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)  
  
-   [Cómo copiar los datos en el contexto del mensaje como campos de propiedades](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)