---
title: Lo ESB Namespace de agregar y quitar componentes de Namespace | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21df1b21-b73c-4e31-a234-49a1a6b53cc7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef25458cdf578930f46bdb702feb283a171d1529
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971429"
---
# <a name="the-esb-add-namespace-and-remove-namespace-components"></a>Lo ESB Namespace de agregar y quitar componentes de Namespace
Muchas empresas estaban los usuarios pioneros de tecnologías XML en el momento cuando todavía se emergentes estándares y compartir documentos era poco común. Por lo tanto, no es estrictamente exigir los requisitos para incluir espacios de nombres raíz único, que normalmente es el caso de hoy en día.  
  
 Sin embargo, Microsoft BizTalk Server realiza la identificación de documentos según una combinación de espacio de nombres de nodo raíz y el nombre del nodo raíz, por lo que son difíciles de identificar si varios documentos que no tengan ningún espacio de nombres para el nodo raíz documento diferente tipos usan el mismo nombre de nodo raíz.  
  
 Los componentes de Namespace agregar y quitar Namespace solucionan este problema, lo que permite agregar espacios de nombres a los documentos cuando se reciben y quitar el espacio de nombres de los documentos antes de entregarlos. Por lo tanto, los documentos pueden residir en el espacio de nombres predeterminado (o en un espacio de nombres común a varios tipos de documento diferente) al que se envían y reciben pero que residen en un espacio de nombres raíz único transitorios durante el procesamiento en el ESB y BizTalk.  
  
 Los componentes también son útiles cuando la integración de sistemas heredados que usan una definición de tipo de documento (DTD) en lugar de una definición de esquemas XML o que usan los analizadores XML heredados que no se pueden crear documentos que contienen un espacio de nombres raíz.  
  
## <a name="installation"></a>Installation  
 Instalar automáticamente el núcleo de ESB se instala el **agregar Namespace** y **quitar Namespace** componentes en la carpeta de componentes de canalización de BizTalk Server.  
  
## <a name="how-it-works"></a>Funcionamiento  
 El componente agregar Namespace, agrega un espacio de nombres especificado en un documento XML. El componente puede agregar un único espacio de nombres a un documento. Mediante el componente de Namespace agregar en un documento que ya tiene un espacio de nombres del nodo raíz no es un escenario admitido, porque un único espacio de nombres único es todo lo que es necesario.  
  
 Los componentes no son compatibles con espacio de nombres y no conservan cualquiera de los valores de espacio de nombres. Sin embargo, el componente agregar Namespace compara el espacio de nombres solicitado en el espacio de nombres existente del mensaje y devuelve simplemente el mensaje original a la canalización si coinciden.  
  
 Los desarrolladores incluyen el componente Namespace agregar en una canalización de recepción o una canalización de envío y establecer las propiedades adecuadas. La siguiente validación se realiza en tiempo de ejecución:  
  
- El **XPaths** propiedad o el **NamespaceBase** propiedad debe contener un valor.  
  
- El **separador** propiedad puede contener solo caracteres válidos (como **/** o **\\**) o una cadena vacía.  
  
- El **NamespacePrefix** valor de propiedad no puede ser uno de los valores de reservado (**ns0** a **ns6**) y debe ser alfa numérica.  
  
  Cualquier variación de esas reglas hace que el componente producir una excepción en tiempo de ejecución, suspender el mensaje (marcado como **reanudable, suspendido**) y escribir una entrada en el registro de eventos de aplicación de Windows.  
  
  El componente Namespace quitar quita todos los espacios de nombres raíz de un documento XML. El número de espacios de nombres que se puede quitar el componente de un solo documento está restringido por la memoria física disponible para almacenar el nodo actual durante el procesamiento. Sin embargo, el componente usa estándar streaming los procesos de mensajes de canalización de BizTalk Server 2009 y carga solamente el nodo actual en el documento en la memoria en lugar de cargar todo el documento.  
  
  El componente Namespace quitar también vuelve a codifica el documento a la codificación especificada (**ascii, unicode o utf16,** o **utf8**) y se puede quitar la marca de orden de bytes (BOM) desde el principio de la secuencia, si Obligatorio.  
  
## <a name="using-the-add-namespace-and-remove-namespace-components"></a>Mediante el Namespace de agregar y quitar componentes de Namespace  
 Los desarrolladores podrían utilizar el componente agregar Namespace en cualquiera de las siguientes circunstancias:  
  
- El mensaje entrante no tiene ningún espacio de nombres raíz.  
  
- El mensaje entrante usa datos de elemento o atributo para describir el tipo de mensaje.  
  
- Los datos que describe el tipo de mensaje son coherentes y disponibles mediante consultas XPath.  
  
  Los componentes de Namespace agregar y quitar Namespace pueden residir en cualquier etapa de una canalización de recepción o una canalización de envío. Puede encadenar las instancias del componente si es necesario, tal como si está usando el componente quitar Namespace seguido por el componente agregar Namespace para cambiar el espacio de nombres raíz de un documento.  
  
  Si tiene varias ubicaciones de recepción que requieren el uso de estos componentes, puede crear una única canalización y utilizar el servidor BizTalk Server "por cada instancia de" configuración de componentes para establecer las propiedades del componente para cada instancia de envío o la canalización de recepción. Con BizTalk Server 2009, puede establecer propiedades en una base por instancia para las canalizaciones, lo que significa que puede reutilizar una sola canalización entre varias ubicaciones de recepción y quizás tienen propiedades de componente diferente para cada instancia. Se trata de una configuración de tiempo de ejecución que permite a los administradores realizar el cambio mediante la consola de administración de BizTalk Server sin necesidad de realizar cambios en el código o volver a implementar.  
  
## <a name="component-properties"></a>Propiedades de componente  
 El componente agregar Namespace expone cinco propiedades públicas:  
  
-   **NamespacePrefix**. Este es el prefijo del espacio de nombres, se inserta entre el **xmlns:** parte y el siguiente igual (=) inicia sesión. Para evitar conflictos con los prefijos de espacio de nombres de esquema de BizTalk estándares, evite el uso de los valores **ns0** a través de **ns9**.  
  
-   **NamespaceBase**. Esta es la sección estática del espacio de nombres que se agregará el prefijo del resultado generado por los valores de la **separador** y **XPaths** propiedades.  
  
-   **ExtractionNodeXPath**. Se trata de una instrucción XPath que se resuelve en un único elemento en el documento que contiene los valores de atributo o elemento que desea usar para las partes del espacio de nombres generadas.  
  
-   **XPaths**. Se trata de una canalización (**&#124;** ) lista delimitada de consultas XPath utilizadas para extraer cada uno de los componentes que se combinan para formar el espacio de nombres.  
  
-   **Separador**. Se trata el separador que se va a usar entre los segmentos de espacio de nombres. El valor más común es una barra diagonal (**/** ), pero puede ser una cadena vacía, si es necesario.  
  
> [!NOTE]
>  Todos los nodos XML, como los nombres de elementos y atributos distinguen mayúsculas de minúsculas.  
  
 El componente quitar Namespace expone dos propiedades públicas:  
  
- **Codificación**. Se trata de la codificación para el mensaje de salida, uno de los siguientes valores: **ascii, unicode o utf16,** o **utf8**.  
  
- **RemoveByteOrderMark**. Se trata de una propiedad booleana que indica si el componente debe quitar la marca de orden de bytes (normalmente **0xEFBB, 0xBFFFFE,** o **0xFEFF**) desde el principio de la secuencia de documentos XML.  
  
  Para obtener un ejemplo de cómo utilizar estos componentes, consulte [instalar y ejecutar el ejemplo del componente Namespace](../esb-toolkit/installing-and-running-the-namespace-component-sample.md).