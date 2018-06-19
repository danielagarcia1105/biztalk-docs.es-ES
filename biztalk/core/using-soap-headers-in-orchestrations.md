---
title: Usar encabezados SOAP en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, code samples
- SOAP headers, creating
- SOAP headers, properties
- Web services, SOAP headers
- orchestrations, SOAP headers
- creating, SOAP headers
ms.assetid: 4754dd23-386b-4093-8ea4-4da6b4d9279c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faae7013c824926adea67feab296e1993f93e326
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288540"
---
# <a name="using-soap-headers-in-orchestrations"></a>Usar encabezados SOAP en orquestaciones
Las orquestaciones usan esquemas de propiedades para definir las propiedades de contexto de encabezados SOAP. Use el Editor de BizTalk para establecer las propiedades de contexto de encabezados SOAP.  
  
## <a name="defining-soap-header-context-properties-with-property-schemas"></a>Definir propiedades de contexto de encabezados SOAP con esquemas de propiedades  
 Necesitará un esquema de propiedades para usar propiedades de contexto de encabezados SOAP definidas en orquestaciones. El esquema de propiedad debe tener el espacio de nombres de destino de **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**y el **Property Schema Base** propiedad establecida en  **MessageContextPropertyBase**. Cada nombre de elemento raíz del esquema de propiedades debe coincidir con el nombre de elemento raíz del encabezado SOAP definido. Entonces podrá establecer valores para las propiedades de contexto que usen el espacio de nombres del esquema de propiedades y el nombre de la propiedad.  
  
> [!NOTE]
>  El espacio de nombres del esquema de propiedad es diferente del espacio de nombres del esquema de destino (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**). Su espacio de nombres puede ser cualquier cadena; no obstante, suele tener de forma predeterminada el nombre del proyecto.  
  
 El siguiente código muestra cómo asignar una propiedad de contexto de encabezado SOAP donde es el espacio de nombres del esquema de propiedad **SOAPHeader** con un nombre de propiedad de **OrigDest**:  
  
```  
requestMessageInstance(SOAPHeader.OrigDest) = stringVar;  
```  
  
 Para obtener más información sobre propiedades de contexto y esquemas de propiedades, vea [esquemas de propiedades](../core/property-schemas.md).  
  
## <a name="using-biztalk-editor-to-set-soap-header-context-properties"></a>Usar el Editor de BizTalk para establecer las propiedades de contexto de encabezados SOAP  
 Respecto a las orquestaciones, las propiedades de contexto del encabezado SOAP están establecidas como cadenas que contienen datos XML. Establezca estas cadenas mediante el Editor de expresiones de BizTalk en un **asignación de mensajes** o **expresión** forma.  
  
 El siguiente ejemplo muestra la configuración de la cadena de la propiedad de contexto:  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = "<?xml version=\"1.0\"?>  
<OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
<Origination>Home</Origination>  
<Destination>Work</Destination>  
</OrigDest>"  
```  
  
## <a name="using-biztalk-editor-to-create-an-instance-of-a-soap-header-root-element"></a>Usar el Editor de BizTalk para crear una instancia de un elemento raíz de encabezado SOAP  
 La configuración del encabezado SOAP a la cadena correcta puede ser una tarea difícil. Al agregar una referencia Web a un proyecto de BizTalk, todas las partes del mensaje Web se agregan a Reference.xsd como elementos raíz. Reference.xsd también contiene elementos raíz para cada encabezado SOAP definido. Para asegurar que establece el encabezado SOAP con la cadena correcta, debe usar el Editor de BizTalk para crear una instancia del elemento raíz del encabezado SOAP para Reference.xsd. Puede usar los datos de instancia generados directamente en los datos de instancia para contener los datos reales.  
  
 Para obtener más información acerca de cómo utilizar el Editor de BizTalk para generar datos de instancia, consulte [cómo generar mensajes de instancia](../core/how-to-generate-instance-messages.md).  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a>Crear un XmlDocument para establecer propiedades de contexto  
 Puede establecer las propiedades de contexto mediante la creación de un **XmlDocument** y escribir el valor de cadena de la **XmlDocument** a la propiedad de contexto. Declare una variable de tipo **XMLDocument** y asigne los datos XML.  
  
 En el ejemplo siguiente se muestra la configuración de declaración de una variable de tipo **XMLDocument** y asigne los datos XML:  
  
```  
xmlDoc.LoadXml("<?xml version=\"1.0\"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination>Home</Origination><Destination>Work</Destination></OrigDest>");  
```  
  
 El siguiente ejemplo muestra la configuración de la propiedad de contexto:  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = xmlDoc.OuterXml;  
```  
  
 Para obtener más información acerca de cómo utilizar el Editor de expresiones de BizTalk, consulte [requisitos y limitaciones para las expresiones](../core/requirements-and-limitations-for-expressions.md). Para obtener más información sobre cómo llamar a las clases. NET, vea [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).  
  
## <a name="creating-soap-headers-for-a-soap-request"></a>Crear encabezados SOAP para una solicitud SOAP  
 Cuando cree encabezados SOAP para la solicitud SOAP, debe asegurarse de que ha creado los encabezados SOAP correctamente. El adaptador de SOAP no comprueba el contenido de las propiedades de contexto del encabezado SOAP.  
  
> [!NOTE]
>  Si el encabezado SOAP es incorrecto, BizTalk no puede enviar la solicitud SOAP al servicio Web.  
  
 La respuesta SOAP que devuelve BizTalk al servicio Web también puede contener encabezados SOAP. Sólo puede obtener acceso a estos encabezados SOAP si son encabezados SOAP definidos.  
  
> [!NOTE]
>  Los servicios Web consumidos sólo admiten encabezados SOAP definidos.  
  
 Para obtener más información acerca de los encabezados SOAP definidos, consulte [Using SOAP Headers](../core/using-soap-headers.md). Los encabezados SOAP de respuesta están establecidos como propiedades de contexto que usan la misma sintaxis que los encabezados SOAP de solicitud.  
  
 El siguiente código muestra cómo obtener acceso a los encabezados SOAP de respuesta:  
  
```  
stringVar = ResponseMessageInstance(SOAPHeader.OrigDest);  
```  
  
 Los valores contenidos en las propiedades de contexto son cadenas que contienen datos XML. Establezca estas cadenas mediante el Editor de expresiones de BizTalk en un **asignación de mensajes** o **expresión** forma. Cargar la cadena en un **XmlDocument** y utilizar consultas XPath para obtener acceso a campos específicos.  
  
 Para obtener más información acerca de cómo crear documentos XML en el Editor de expresiones de BizTalk, consulte [lenguaje XLANG s](../core/xlang-s-language.md).  
  
## <a name="see-also"></a>Vea también  
 [Lenguaje XLANG-s.](../core/xlang-s-language.md)   
 [Encabezados SOAP con servicios Web consumidos](../core/soap-headers-with-consumed-web-services.md)