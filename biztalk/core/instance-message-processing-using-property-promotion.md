---
title: Instancia con promoción de propiedades de procesamiento de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 753571b8-4609-4ac4-a974-8bd6dfecb077
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 288657d43443582c5a05df5dd6e67059eca572e9
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="instance-message-processing-using-property-promotion"></a>Procesar mensajes de instancia con promoción de propiedades
Promocionar propiedades mediante la **campo de propiedad** método requiere la creación de un esquema de propiedad. Para obtener más información acerca de cómo crear un esquema de propiedades, vea [cómo crear esquemas de propiedad](../core/how-to-create-property-schemas.md). Como con la promoción de propiedades, use el **promocionar propiedades** cuadro de diálogo, que es accesible mediante la **promocionar propiedades** propiedad de la **esquema** nodo esquemas de mensaje.  
  
> [!NOTE]
>  Para obtener acceso a las propiedades promocionadas y usarlas, debe seleccionar una canalización que promocione propiedades. Por ejemplo, si usa la canalización PassthruReceive, no se promocionarán propiedades; esto ocasionará que el enrutamiento basado en contenido y otras funciones no actúen según lo esperado.  
  
 En el **promocionar propiedades** diálogo cuadro, asegúrese de que el **campos de propiedades** ficha está seleccionada en el lado derecho del cuadro de diálogo. A continuación, asegúrese del esquema de propiedades adecuado está incluido en la lista de esquemas de propiedad en la parte superior de la **campos de propiedades** ficha. Si es necesario, utilice el botón de carpeta para seleccionar el esquema de propiedades adecuado mediante la **selector de tipos de BizTalk** cuadro de diálogo. A continuación, expanda los nodos del árbol de esquema en el lado izquierdo del cuadro de diálogo para buscar y seleccionar la **elemento de campo** nodo o **atributo de campo** nodo que desea promocionar como un campo de propiedad y, a continuación, haga clic en  **Agregar**. Por último, utilice la lista desplegable en el **propiedad** columna de la **diccionario de campos de propiedades** tabla para seleccionar un **elemento de campo** nodo en un esquema de propiedad con la que se va a asociar la propiedad promocionada. Para obtener instrucciones detalladas acerca de la promoción de propiedades para campos de propiedades mediante la **promocionar propiedades** cuadro de diálogo, vea [cómo copiar datos en el contexto del mensaje como campos de propiedades](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).  
  
> [!NOTE]
>  También puede promocionar un **registro** nodo a un **elemento de campo** nodo en el esquema de propiedades, pero solo si la **tipo de contenido** propiedad de la **registro**nodo se establece en **SimpleContent**.  
  
> [!NOTE]
>  Una propiedad se puede promocionar varias veces dentro de un esquema si dichas promociones se realizan en nodos raíz diferentes. Esto es así porque el mensaje se valida con respecto a un nodo raíz individual y únicamente las propiedades promocionadas en ese nodo raíz se evalúan en tiempo de ejecución.  
  
 Para quitar un **elemento de campo** nodo o **atributo de campo** nodo del conjunto de propiedades que se va a promocionar como campos de propiedades, seleccione la propiedad promocionada en el **diccionario de campos de propiedades**  de tabla en la **campos de propiedades** ficha y, a continuación, haga clic en **quitar**.  
  
 El **ruta del nodo** columna en el **diccionario de campos de propiedades** tabla muestra la expresión XPath en el nodo de esquema correspondiente a la propiedad promocionada. Puede editar este valor directamente mediante el **Editar XPath de instancia** cuadro de diálogo. Puede abrir este cuadro de diálogo, haga clic en el botón de puntos suspensivos (**...** ) botón que aparece en el extremo derecho de la celda correspondiente cuando se selecciona esa celda. Preste atención cuando edite valores XPath directamente, ya que los XPath que no puede resolver el Editor de BizTalk impedirán realizar correctamente operaciones de validación.  
  
 El Editor de BizTalk también proporciona un comando sofisticado para promocionar las propiedades mediante el **campo de propiedad** mecanismo. Este comando se denomina promoción rápida y está disponible con la **promover &#124; promoción rápida** comando en los menús BizTalk y contextuales. Este comando promociona seleccionado **campo** nodo (o **registro** nodo) a un campo de propiedad que se crea automáticamente en el esquema de propiedad especificado por el **nombre de esquema de propiedades predeterminadas**  propiedad en el **páginas de propiedades** cuadro de diálogo para el esquema contenedor. Para obtener instrucciones paso a paso acerca de la promoción de propiedades para campos de propiedades mediante el comando promoción rápida, consulte [cómo copiar datos en el contexto del mensaje como campos de propiedades](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).  
  
 Cuando promocione una propiedad mediante el mecanismo de campos de propiedades, se agregarán dos fragmentos del lenguaje de definición de esquemas XML (XSD) a la representación XSD del esquema de mensaje. El primer fragmento XSD es un fragmento de anotación asociado con el **esquema** elemento que identifica el esquema de propiedad correspondiente, como en el ejemplo siguiente:  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:imports>  
            <b:namespace prefix="ns0"  
                uri="http://BizTalk_Server_Project1.PropertySchema1"  
                location=".\propertyschema1.xsd" />  
        </b:imports>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
 El segundo fragmento XSD es un fragmento de anotación asociado con el **raíz** elemento (independientemente de si se ha cambiado) que identifica el **elemento de campo** nodo o **campo Atributo** valores de los nodos que se han promocionado mediante el uso de la propiedad de campo mecanismo, como en el ejemplo siguiente:  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:properties>  
            <b:property name="ns0:PromProp1"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/@*[local-  
                 name()='Field_x0020_1']" />  
            <b:property name="ns0:PromProp2"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/*[local-  
                 name()='ProgramManager']/*[local-name()='Name']" />  
        </b:properties>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
## <a name="see-also"></a>Vea también  
 [Formas de usar el contenido de mensaje para el procesamiento de mensajes de Control](../core/ways-to-use-message-content-to-control-message-processing.md)   
 [Cómo copiar los datos en el contexto del mensaje como campos de propiedades](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)