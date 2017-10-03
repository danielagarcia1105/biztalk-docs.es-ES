---
title: ESB Namespace de agregar y quitar componentes de Namespace | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21df1b21-b73c-4e31-a234-49a1a6b53cc7
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bcbe519cfd8c6796569da4de87f59fa6a16d8a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-add-namespace-and-remove-namespace-components"></a>ESB Namespace de agregar y quitar componentes de Namespace
Muchas compañías eran los primeros usuarios de tecnologías XML en el momento cuando todavía se apareciendo estándares y uso compartido de documentos era raro. Por lo tanto, no estrictamente aplican los requisitos para incluir espacios de nombres de raíz única, que normalmente es el caso de hoy en día.  
  
 Sin embargo, Microsoft BizTalk Server realiza la identificación del documento basándose en una combinación de espacio de nombres de nodo raíz y el nombre del nodo raíz, por lo que son difíciles de identificar si varios documentos que no contengan ningún espacio de nombres para el nodo raíz documento diferente tipos utilizan el mismo nombre de nodo raíz.  
  
 Los componentes de Namespace agregar y quitar Namespace solucionar este problema, lo que se permite agregar espacios de nombres a los documentos cuando se reciben y para quitar el espacio de nombres de los documentos antes de entregarlos. Por lo tanto, los documentos pueden residir en el espacio de nombres predeterminado (o en un espacio de nombres comunes a varios tipos de documento diferente) cuando envía y recibe, pero residen en un espacio de nombres raíz único transitorio durante el procesamiento en el ESB y BizTalk.  
  
 Los componentes también son útiles cuando se integra sistemas heredados que utilizan una definición de tipo de documento (DTD) en lugar de una definición de esquemas XML o que utilizan los analizadores XML heredados que no se pueden crear documentos que contienen un espacio de nombres raíz.  
  
## <a name="installation"></a>Installation  
 Al instalar el núcleo de ESB automáticamente se instala el **agregar Namespace** y **quitar Namespace** componentes en la carpeta de componentes de canalización de BizTalk Server.  
  
## <a name="how-it-works"></a>Funcionamiento  
 El componente de agregar Namespace, agrega un espacio de nombres especificado en un documento XML. El componente puede agregar un único espacio de nombres a un documento. Utiliza el componente de agregar Namespace en un documento que ya tiene un espacio de nombres de nodo raíz no es un escenario admitido porque un único espacio de nombres único es todo lo que es necesario.  
  
 Los componentes no son compatibles con el espacio de nombres y no conservan cualquiera de los valores de espacio de nombres. Sin embargo, el componente de agregar Namespace compara el espacio de nombres solicitado en el espacio de nombres existente del mensaje y simplemente devuelve el mensaje original a la canalización si coinciden.  
  
 Los programadores incluyen el componente de Namespace agregar en una canalización de recepción o una canalización de envío y establecer las propiedades adecuadas. Las siguientes de validación se realizan en tiempo de ejecución:  
  
-   El **XPaths** propiedad o el **NamespaceBase** propiedad debe contener un valor.  
  
-   El **separador** propiedad puede contener solo caracteres válidos (como  **/**  o  **\\** ) o una cadena vacía.  
  
-   El **NamespacePrefix** valor de propiedad no puede ser uno de los valores reservados (**ns0** a **ns6**) y debe ser numérica alfa.  
  
 Cualquier variación de esas reglas hace que el componente producir una excepción en tiempo de ejecución, suspender el mensaje (marcado como **suspendido: reanudables**) y escribir una entrada en el registro de eventos de aplicación de Windows.  
  
 El componente de Namespace quitar quita todos los espacios de nombres de raíz de un documento XML. El número de espacios de nombres que se puede quitar el componente de un solo documento está restringido por la memoria física disponible para almacenar el nodo actual durante el procesamiento. Sin embargo, el componente utiliza estándar streaming procesos de mensajes de canalización de BizTalk Server 2009 y carga solamente el nodo actual en el documento en la memoria en lugar de cargar todo el documento.  
  
 El componente de Namespace quitar también vuelve a codifica el documento a la codificación especificada (**ascii, unicode/utf16,** o **utf8**) y se puede quitar la marca de orden de bytes (BOM) desde el principio de la secuencia, si Obligatorio.  
  
## <a name="using-the-add-namespace-and-remove-namespace-components"></a>Mediante el Namespace de agregar y quitar componentes de Namespace  
 Los desarrolladores pueden usar el componente de Namespace agregar en cualquiera de las siguientes circunstancias:  
  
-   El mensaje entrante no tiene ningún espacio de nombres raíz.  
  
-   El mensaje entrante utiliza datos de elemento o atributo para describir el tipo de mensaje.  
  
-   Los datos que describe el tipo de mensaje son coherentes y están disponibles mediante consultas XPath.  
  
 Los componentes de Namespace agregar y quitar Namespace pueden residir en cualquier fase de una canalización de recepción o una canalización de envío. Se pueden encadenar instancias del componente si es necesario, por ejemplo, como si se utiliza el componente de quitar Namespace seguido por el componente de agregar Namespace para cambiar el espacio de nombres raíz de un documento.  
  
 Si tiene varias ubicaciones de recepción que requieren el uso de estos componentes, puede crear una sola canalización y utilizar el servidor BizTalk Server "por cada instancia de" configuración del componente para establecer las propiedades del componente para cada instancia de envío o la canalización de recepción. Con BizTalk Server 2009, puede establecer las propiedades de forma por instancia para las canalizaciones, lo que significa que puede volver a usar una sola canalización en varias ubicaciones de recepción y quizás tiene propiedades de componente diferente para cada instancia. Se trata de una configuración de tiempo de ejecución que permite a los administradores a realizar el cambio mediante la consola de administración de BizTalk Server sin necesidad de cambios en el código o volver a implementar.  
  
## <a name="component-properties"></a>Propiedades de componente  
 El componente de agregar Namespace expone cinco propiedades públicas:  
  
-   **NamespacePrefix**. Este es el prefijo del espacio de nombres, se inserta entre el **xmlns:** parte y siguiente signo de igual (=) de inicio de sesión. Para evitar conflictos con prefijos de espacio de nombres de esquema de BizTalk estándares, evite el uso de los valores **ns0** a través de **ns9**.  
  
-   **NamespaceBase**. Esta es la sección estática del espacio de nombres que se agregará el prefijo del resultado generado por los valores de la **separador** y **XPaths** propiedades.  
  
-   **ExtractionNodeXPath**. Se trata de una instrucción XPath que se resuelve en un único elemento en el documento que contiene los valores de elemento o atributo que desea usar para las partes del espacio de nombres generadas.  
  
-   **XPaths**. Se trata de una canalización (**&#124;** ) lista delimitada de consultas XPath utilizadas para extraer todos los componentes que se combinan para formar el espacio de nombres.  
  
-   **Separador de**. Se trata el separador que se va a usar entre los segmentos de espacio de nombres. El valor más común es una barra diagonal ( **/**  ), pero puede ser una cadena vacía, si es necesario.  
  
> [!NOTE]
>  Todos los nodos XML, como los nombres de elementos y atributos distinguen mayúsculas de minúsculas.  
  
 El componente de quitar Namespace expone dos propiedades públicas:  
  
-   **Codificación**. Se trata de la codificación para el mensaje de salida, uno de los siguientes valores: **ascii, unicode/utf16,** o **utf8**.  
  
-   **RemoveByteOrderMark**. Se trata de una propiedad booleana que indica si el componente debe quitar la marca de orden de bytes (normalmente **0xEFBB, 0xBFFFFE,** o **0xFEFF**) desde el principio de la secuencia del documento XML.  
  
 Para obtener un ejemplo de cómo usar estos componentes, consulte [instalar y ejecutar el ejemplo del componente Namespace](../esb-toolkit/installing-and-running-the-namespace-component-sample.md).