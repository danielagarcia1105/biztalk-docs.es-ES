---
title: Sugerencias para diseñar un adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bb60988-4e48-4654-9cf4-512dd7c97239
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 306cb2ae9aeca57804a57f0dfa8c1de1bfd0025d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982685"
---
# <a name="tips-for-designing-your-adapter"></a>Sugerencias para diseñar un adaptador
Esta sección contiene sugerencias e ideas que los programadores de adaptadores han aprendido al diseñar adaptadores.  
  
## <a name="handler-properties-should-be-strings-if-used-as-default-configurations"></a>Las propiedades de controlador deben ser cadenas si se usan como configuraciones predeterminadas  
 Parece interesante usar las propiedades en la hoja de propiedades de controlador generado mediante XSD como valores predeterminados para sus **ubicación** propiedades porque si el valor no se establece **ubicación** el tiempo de ejecución automáticamente usa el valor establecido en el controlador. Pero existen varios problemas que reducen la utilidad de esta posibilidad.  
  
 El problema aparece cuando no se sabe si el valor presentado en tiempo de ejecución debe sobrescribirse o no. La forma habitual de hacerlo es definir alguna noción de NULL para los valores y, a continuación, ejecutar una prueba con ese valor. El problema de usar hojas de propiedades basadas en XSD en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es que NULL solo se admite para cadenas. Aunque desee que el adaptador tenga una configuración predeterminada mediante el uso de esta prueba de NULL y esté dispuesto a restringir el adaptador a los tipos de cadena, sigue arriesgándose a obtener una interfaz de usuario de lo más extraño.  
  
 Las hojas de propiedades generado mediante XSD solo admiten la configuración de una propiedad en NULL con el botón secundario de la propiedad, momento en que un **anulan?** aparece el menú contextual y la propiedad puede establecerse en NULL. No existe ninguna información visual que indique si una propiedad es NULL.  
  
## <a name="considerations-for-implementing-schema-generation-wizards"></a>Consideraciones sobre la implementación de asistentes para generación de esquemas  
 Los programadores prefieren escribir código basado en modelos de objetos de tipo seguro. Al principio, manipular XML en el código puede parecer extraño y proclive a errores. Pero algunos trucos y el uso inteligente de la compatibilidad que ofrece .NET Framework pueden simplificarlo todo de manera drástica.  
  
#### <a name="do-not-create-xml-documents-with-string-concatenation"></a>No cree documentos XML con concatenación de cadenas  
 Una de las peores equivocaciones que puede cometer con XML es intentar generarlo mediante la concatenación de cadenas e imprimir las instrucciones en la memoria. Esto consume grandes cantidades de tiempo de la CPU y de memoria. Incluso para el fragmento de código XML más trivial, resulta más fácil utilizar una herramienta como XmlWriter o el modelo de objetos de documento (DOM). Si usa XmlWriter, no use la capacidad de escritura sin formato, porque el escritor pierde el estado del documento.  
  
 En tiempo de ejecución, XmlWriter es preferible a DOM XML por los problemas de consumo elevado de memoria asociados al DOM. Sin embargo, en tiempo de configuración o diseño lo más probable es que no plantee ningún problema. El uso del DOM facilita el uso de consultas XPATH, que pueden constituir una herramienta adicional de gran utilidad.  
  
#### <a name="consider-defining-the-skeleton-of-your-xml-document-as-a-resource"></a>Estudie la posibilidad de definir el esqueleto del documento XML como recurso  
 Si va a generar un documento XML de gran tamaño mediante una herramienta de diseño y ese documento generado siempre sigue la misma estructura básica, puede ser conveniente colocar todo el esqueleto del archivo XML en el proyecto para permitir la realización de cambios cuando sea preciso modificarlo.  
  
 Cargue el código en un modelo de objetos de documento (DOM) y agregue los elementos necesarios al esqueleto del documento usando XPATH para seleccionar el nodo al que desee agregarlos. En este caso, se crea un archivo Lenguaje de descripción de servicios Web (WSDL). El asistente almacena el archivo WSDL del esqueleto en un recurso y agrega los elementos secundarios en el Lenguaje de definición de esquema XML (XSD) generados. Utiliza selectNode con XPath para encontrar el elemento principal correspondiente. Se trata de código de interfaz de usuario, con lo que el rendimiento no constituye un problema y la implementación resultante es limpia, robusta y mantenible.  
  
## <a name="consider-placing-processing-steps-in-the-biztalk-pipeline"></a>Estudie la posibilidad de colocar pasos de procesamiento en la canalización de BizTalk  
 En general, los adaptadores generados en Microsoft quitan del adaptador el procesamiento basado en formato de mensajes y lo colocan en la canalización de BizTalk. Un buen ejemplo de ello es un adaptador para un origen de datos estructurado que no es XML.  
  
 En este caso, el adaptador se limita a obtener los datos, y se usa la canalización de BizTalk para analizarlos y convertirlos a un equivalente de XML. La ventaja es que el propio componente de canalización se convierte en una pieza reutilizable de la arquitectura.  
  
## <a name="make-adapter-behavior-configurable"></a>Permita la configuración del comportamiento del adaptador  
 Una de las conclusiones extraídas del programa beta del adaptador de MQSeries fue que no todos los clientes estaban satisfechos con el mismo comportamiento. Esto se cumplía especialmente en lo relativo al control de errores y al orden. La solución fue hacer que el comportamiento del adaptador fuera configurable. Puede especificar si el adaptador admitirá la ordenación, si los fracasos se moverán a la cola de suspensión o si harán que el adaptador deje de procesar y se deshabilite. Permitir la configuración de este tipo de comportamientos puede simplificar de manera significativa la vida del cliente, que en caso contrario tendría que escribir orquestaciones o secuencias de comandos externas de gran complejidad a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para lograr el mismo resultado.  
  
## <a name="support-correlation-with-message-queues"></a>Admita la correlación con las colas de mensajes  
 Numerosas plataformas de mensajería admiten la noción de un Id. de correlación en el encabezado de mensaje para proporcionar compatibilidad con un escenario de solicitud-respuesta de nivel de aplicación. Algunos ejemplos de ello son MQSeries, MSMQ y SQL Service Broker. Podría parecer interesante asignar el patrón de solicitud-respuesta del sistema de mensajería externo a un adaptador de envío-respuesta de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Sin embargo, esto no tiene sentido por el lugar donde residen las transacciones. En concreto, un envío al sistema de mensajería externa exige una confirmación transaccional antes de que el otro extremo de la cola pueda ver los datos. La recepción también debe ser una transacción independiente.  
  
 La solución en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es:  
  
- Usar conjuntos de correlaciones en la orquestación  
  
- Configurar dos puertos independientes: uno para el envío y otro para la recepción  
  
  En un caso sencillo, la orquestación especifica el Id. de correlación asociado al mensaje por el adaptador. Éste se pasa al adaptador como propiedad de contexto en el mensaje. En un caso más complejo, el escenario llama al sistema de mensajería externa asignar el identificador. En este caso se puede pasar desde el puerto de envío a la orquestación con un mensaje de respuesta. Este mensaje de respuesta se utiliza exclusivamente para devolver el Id., y no es la verdadera respuesta al mensaje.  
  
> [!NOTE]
>  Existe una condición de anticipación en el motor de orquestación que permite que la verdadera respuesta al mensaje llegue antes que la respuesta del Id. correspondiente al envío. Esta condición de anticipación se debe controlar en la propia orquestación.