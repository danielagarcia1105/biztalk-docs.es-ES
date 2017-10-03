---
title: Los esquemas que usan otros esquemas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02954d46-48ce-4cdf-a012-74c212ce8b6d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 563260031e545b5223697d49992c1ae85bae3891
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schemas-that-use-other-schemas"></a>Esquemas que usan otros esquemas

## <a name="overview"></a>Información general
Cuando los esquemas se hacen grandes y complejos o si los esquemas que representan a los distintos tipos de mensajes de instancia tienen algunas partes en común, puede ser útil combinar los esquemas más pequeños en esquemas que definan la estructura de los mensajes de instancia que planea intercambiar con los socios comerciales. Por ejemplo, podría tener varios tipos de mensaje que requieran que una dirección de envío se exprese dentro de ellos. Puede definir la estructura de una dirección de envío en un único esquema y, a continuación, utilizar ese esquema dentro de otros esquemas que definan, por ejemplo, esquemas de mensaje de pedidos, facturas y avisos de envío.  

## <a name="import-include-and-redefine"></a>Importar, incluir y redefinir  
 El lenguaje de definición de esquemas XML (XSD) proporciona tres mecanismos relacionados que permiten usar a la vez varios esquemas que el Editor de BizTalk admite. En la siguiente tabla se resumen las características de estos mecanismos, de acuerdo con la definición de XSD.  
  
|Mecanismo de varios esquemas|Escenario de uso|  
|---------------------------|--------------------|  
|Importar|-Obtiene acceso y utiliza los tipos definidos en el esquema importado.<br />-Debe utilizar tipos en el esquema importado tal cual o derivar tipos nuevos a partir de ellos; no se permite ninguna modificación de tipo.<br />: Proporciona un mecanismo para utilizar tipos definidos en otros espacios de nombres. De hecho, un esquema importado debe tener un espacio de nombres de destino que sea diferente del esquema de importación.<br />-Utiliza el **importar** elemento y su **espacio de nombres** y **schemaLocation** atributos para hacer referencia al otro esquema.|  
|Incluir|-Obtiene acceso y utiliza los tipos definidos en el esquema incluido.<br />-Debe utilizar tipos en el esquema incluido tal cual o derivar tipos nuevos a partir de ellos; no se permite ninguna modificación de tipo.<br />-El esquema incluido debe estar en el mismo espacio de nombres de destino como el esquema de inclusión o el espacio de nombres de destino del esquema incluido debe estar vacío.<br />-Utiliza el **incluyen** elemento y su **schemaLocation** atributo para hacer referencia al otro esquema.|  
|Redefine|-Obtiene acceso y utiliza los tipos definidos en el esquema redefinido.<br />-Pueden utilizar los tipos del esquema redefinido tal cual, derivar tipos nuevos a partir de ellos, o especificar modificaciones en ellos.<br />-El esquema redefinido debe estar en el mismo espacio de nombres de destino como el esquema de redefinición, o el espacio de nombres de destino del esquema redefinido debe estar vacío.<br />-Utiliza el **redefinir** elemento y su **schemaLocation** atributo para hacer referencia al otro esquema. Cualquier redefinición de tipo se especifica con el **redefinir** elemento. **Nota:** mediante el mecanismo redefine es un concepto avanzado de XSD y solo debe utilizarse después de que se tienen conocimientos suficientes sobre cómo y cuándo se debe utilizar.|  
  
> [!NOTE]
>  Para obtener información completa acerca de las diferencias y similitudes entre la importación, incluir y volver a definir mecanismos, consulte las referencias incluidas en [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).  

## <a name="important-details"></a>Detalles importantes  
 Para utilizar un tipo definido en un esquema (Schema1) en otro esquema (Schema2), debe proporcionar una referencia a Schema1 dentro de Schema2. Para ello, use la **importaciones** propiedad de la **esquema** nodo en Schema2. Al hacer clic en el botón de puntos suspensivos (**...** ) botón en el **importaciones** campo de propiedad, el **importaciones** abre el cuadro de diálogo. En el **importar un esquema nuevo como** lista desplegable, seleccione **XSD Import**, **XSD Include**, o **XSD Redefine**. A continuación, haga clic en **agregar** para abrir el **selector de tipos de BizTalk** cuadro de diálogo y examinar dentro de su proyecto de BizTalk para seleccionar **Schema1**.  
  
 Para obtener instrucciones detalladas acerca de estos pasos, consulte [crear esquemas que usan otros esquemas](../core/how-to-create-schemas-that-use-other-schemas.md).  
  
 Cuando se usa el **importaciones** cuadro de diálogo para importar, incluir o redefinir otro esquema, uno o varios de los elementos XSD **importar**, **incluyen**, y **redefinir**  se agrega a la representación XSD del esquema, incluidos los atributos adecuados y los valores de atributo. Además, en el caso de los **importar** , una declaración de prefijo del espacio de nombres del otro esquema se agrega a la **esquema** elemento.  
  
 Todos los tipos globales (como **ComplexTypes**, **SimpleTypes**, grupos de elementos, grupos de atributos) en un esquema importado, incluido o redefinido están automáticamente disponibles para su uso dentro del esquema en el que el esquema anterior es importado, incluido o redefinido. Por ejemplo, global **ComplexTypes** definida en un esquema importado, incluido o redefinido se agregan a la lista desplegable de la **Data Structure Type** propiedad para todos los **registro** nodos en el esquema de importación, inclusión o redefinición. Para obtener más información acerca de esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="see-also"></a>Vea también  
 [Acerca de los esquemas](../core/about-schemas.md)   
 [Crear esquemas que usan otros esquemas](../core/how-to-create-schemas-that-use-other-schemas.md)   
 [Crear referencias a otro nodo o tipo](../core/how-to-create-references-to-another-node-or-type.md)