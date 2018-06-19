---
title: Crear esquemas con el Editor de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03fac91b-5b67-4baf-968c-294c525d3018
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9e4c6496f43a9602ad56bc0e095d98f2da90d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238940"
---
# <a name="create-schemas-using-biztalk-editor"></a>Crear esquemas con el Editor de BizTalk

## <a name="overview"></a>Información general
El Editor de BizTalk es una herramienta que se ejecuta en el entorno Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Permite crear, editar y administrar esquemas para usarlos con una aplicación. El Editor de BizTalk utiliza un sistema gráfico propio de registros y campos jerárquicos para representar la estructura de los mensajes de instancia, además del lenguaje de definición de esquemas XML (XSD) para almacenar los esquemas que define. No importa el formato en el que se intercambien los mensajes de instancia. Por ejemplo, supongamos que intercambia archivos sin formato con un socio comercial. Cuando BizTalk Server procese esos archivos sin formato, los convertirá en formato XML y de formato XML para que se ajusten a un esquema XSD definido en el Editor de BizTalk.  
  
 Los esquemas creados con el Editor de BizTalk se pueden usar dentro de un proceso empresarial de orquestaciones, como se muestra en la siguiente ilustración.  
  
 ![](../core/media/ebiz-dev-busprcsh.gif "ebiz_dev_busprcsh")  
  
 Los ensambladores y desensambladores también utilizan esquemas para traducir los mensajes de instancia de un formato a otro; por ejemplo, entre un formato de archivo sin formato y XML. Los esquemas también desempeñan un importante rol en la transformación de los mensajes de instancia, donde los datos de un mensaje de instancia se utilizan para crear un mensaje de instancia con una estructura diferente. El nuevo mensaje de instancia puede ser semánticamente equivalente, como las distintas representaciones de un pedido, o puede ser distinto pero de un tipo de mensaje de instancia relacionado que necesita parte o la totalidad de los datos del mensaje de instancia original en el contenido.  
  
 Un motivo importante para traducir todos los mensajes de instancia a un formato XML que se ajuste a un esquema XSD es simplificar el proceso de transformar un mensaje de una estructura a otra. Las estructuras de los mensajes tienen normalmente una semántica equivalente a pesar de tener diferencias sintácticas. Por ejemplo, su empresa y un socio comercial pueden realizar los pedidos de compra con una estructura distinta pero con la misma información básica, lo que permite la transformación la transformación de unos a otros de forma automática. Al convertir en primer lugar todos los mensajes de instancia en un formato XML regido por un esquema XSD correspondiente, los mensajes de instancia se pueden volver a traducir entre los formatos XML y no XML, así como transformarse de una estructura XML en otra. Para obtener más información acerca de la diferencia entre traducción de mensaje de instancia y transformación de mensajes de instancia, consulte [transformación de datos](../core/data-transformation.md).  
  
 La herramienta complementaria del Editor de BizTalk dentro del entorno Microsoft Visual Studio es el Asignador de BizTalk. Después de usar el Editor de BizTalk para crear los esquemas que definen la estructura y el formato de un par de mensajes de instancia relacionados, utilice el Asignador de BizTalk para establecer de forma gráfica cómo transformar un mensaje de instancia que se ajusta a un esquema (el esquema y mensaje de instancia de origen) en un mensaje de instancia que se ajuste a otro esquema (el esquema y mensaje de instancia de destino). La especificación de esas transformaciones se implementa mediante XSLT (Transformación de lenguaje de hojas de estilo extensible) y se mantiene como archivos denominados asignaciones. Para obtener información conceptual y de procedimiento sobre el asignador de BizTalk, consulte [crear asignaciones usando asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md). Para obtener información de referencia sobre las propiedades de asignador de BizTalk y functoids, consulte el **referencia de asignación de propiedad** y **referencia de Functoid**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
 El Editor de BizTalk le permite abrir un esquema en blanco sin ninguna estructura, abrir un esquema XSD existente o generar un esquema desde un origen que no sea XSD. Al generar un esquema desde un origen que no sea XSD, el Editor de BizTalk interpreta la estructura del origen y crea un esquema que es una representación XSD del mismo. Puede editar los registros y campos que aparecen en la vista de árbol de esquema del Editor de BizTalk y, a continuación, guardar la estructura como un esquema de BizTalk.  
  
 Para obtener información sobre el uso de métodos abreviados de teclado para el Editor de BizTalk, consulte [métodos abreviados de teclado del Editor de BizTalk](../core/biztalk-editor-keyboard-shortcuts.md).  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Planear la creación de esquemas](../core/planning-for-schema-creation.md)  
  
-   [Acerca de los mensajes de instancia](../core/about-instance-messages.md)  
  
-   [Acerca de los esquemas](../core/about-schemas.md)  
  
-   [Usar el Editor de BizTalk](../core/using-biztalk-editor.md)  
  
-   [Creación de esquemas](../core/creating-schemas.md)  
  
-   [Crear esquemas con el Asistente para esquemas de archivo sin formato de BizTalk](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)  
  
-   [Comprobación de esquemas](../core/testing-schemas.md)  
  
-   [Extender el Editor de BizTalk](../core/extending-biztalk-editor.md)  
  
-   [Consideraciones al crear esquemas](../core/considerations-when-creating-schemas.md)  
  
-   [Problemas conocidos con la generación de esquemas y validación](../core/known-issues-with-schema-generation-and-validation.md)