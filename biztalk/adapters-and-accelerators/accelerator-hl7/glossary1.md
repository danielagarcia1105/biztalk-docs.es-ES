---
title: Glosario de Acelerador para HL7 en BizTalk Server | Documentos de Microsoft
description: Común de términos y definiciones para conocer y aprender a usar el Acelerador de BizTalk para HL7
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffb9c18a-5fe5-448f-b115-0973e9d12952
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d90a98fd1c30aed5bb38cca99774f610a59dedaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204956"
---
# <a name="glossary"></a>Glosario
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 utiliza los siguientes términos y definiciones.

## <a name="a"></a>Un    
 **artefacto**    
 Los artefactos que componen la votación HL7 V3.0 son las entregas resultante de la detección, análisis y las actividades de diseño que dan lugar a la creación de especificaciones de mensaje.  
  
 Dentro de los estándares de HL7 V3.0, los componentes que constituyen la documentación son artefactos. Esto incluye guiones gráficos, roles de aplicación, desencadenar eventos, las especificaciones del modelo de información de mensaje de dominio (D-MIMs), las especificaciones de modelo de información de mensaje se ha refinado (R-MIMs), specificatins(HMDs) jerárquica descripción del mensaje, tipos de mensajes, e interacciones.  
  
 **identificador de artefacto**    
 Un Comité técnico envía y proporciona un identificador único que se asigna mediante la concatenación de la subsección, dominio y el artefacto de código, un número de 6 dígitos no significativos, un código de dominio Kerberos de 2 dígitos y un número de versión de 2 dígitos de cada artefacto.  

## <a name="c"></a>C
  
 **cardinalidad**    
 La propiedad de un elemento de datos (el número de veces que un elemento de datos puede repetirse dentro de una única repetición de una vista de objeto) o una columna en la descripción del mensaje jerárquica (el número mínimo y máximo de apariciones del elemento del mensaje). Consulte la descripción del mensaje jerárquica.  
  
## <a name="d"></a>D   
 **dominio**    
 1. El problema o puede resolverse mediante un conjunto de mensajes HL7 o por un sistema ("dominio de aplicación"). Un área concreta de interés en la atención médica. 
 2. El conjunto de valores posibles de un tipo de datos, un atributo o un componente de tipo de datos. Consulte vocabulario dominio. 
 3. Un grupo de interés en HL7, como administración de farmacia, laboratorio, paciente.  
  
## <a name="e"></a>E 
 **evento**    
 1. Estímulo que provoca un cambio de estado de interés de un objeto. Una señal que invoca el comportamiento de un objeto. Vea el evento de desencadenador. 
 2. Un valor de dominio de vocabulario de ambiente.  
  
 
## <a name="h"></a>H
**Descripción del mensaje jerárquica (HMD)**    
 Especificación de los campos exactos de un mensaje y su agrupación, secuencia, opcionalidad y cardinalidad. Contiene tipos de interacciones de uno o más mensajes o representa uno o más tipos de elemento de mensaje común. Se trata de la estructura de la normativa principal para los mensajes de HL7.  
  
## <a name="m"></a>M  
 **obligatorio**    
 Una columna en la descripción de mensaje jerárquica (HMD). Si la inclusión de un atributo obligatorio, todos los elementos del mensaje en función de este atributo debe contener un valor distinto de null, o deben tener un valor predeterminado que no es null.  
  
  
 **Mensaje**    
 Un conjunto de información se comunica desde una aplicación a otra. Vea el tipo de mensaje y la instancia de mensaje.  
  
 **Marco de desarrollo de mensaje (MDF)**    
 La colección de modelos, métodos y herramientas que componen la metodología para mensajes HL7 V3.0. Los desarrolladores de los estándares de HL7 usar este marco de trabajo. La Guía de V3.0 se resume el contenido de la metodología.  
  
 **elemento Message**    
 Una unidad de estructura dentro de un tipo de mensaje.  
  
 **tipo de elemento de mensaje**    
 Una parte de un tipo de mensaje que describe uno de los elementos del mensaje.  
  
 **instancia de mensaje**    
 Un mensaje con el formato de una transmisión específica. El mismo tipo de mensaje puede describir los mensajes de dos e identificar la interacción del mismo y aún pueden variar en la instancia debido a las variaciones de valores, presencia, o ausencia de los datos que se envían y cardinalidades diferentes de las colecciones. En caso contrario, mensajes idénticos puede instancias diferentes si se envían en distintos momentos o por otro remitente.  
  
 **carga de mensaje**    
 Datos que se realizan en un mensaje.  
  
 **tipo de mensaje**    
 La organización de elementos del mensaje que se especifica en una descripción de mensaje jerárquica (HMD). Cada tipo de mensaje se comunica como parte de una o varias de las interacciones en el modelo de interacción. Un tipo de mensaje en vigor constituye un conjunto de reglas para construir un mensaje determinado en un conjunto específico de datos de instancia. También define las reglas para analizar un mensaje para recuperar los datos de instancia. El tipo de mensaje es independiente de la especificación de la tecnología de implementación, por lo que si los mismos datos se envían con el mismo tipo de mensaje y especificaciones de tecnología de implementación diferentes, el tipo de mensaje puede ser transliteración de uno a otro.  

## <a name="p"></a>P  
 **propiedad**    
 Cualquier atributo, asociación, método o modelo de estado definidos para una clase u objeto. En un HMD, la columna que indica el nombre de la clase, atributo o asociación rol tal y como aparece en el modelo de información de referencia (RIM).  

## <a name="r"></a>L  
 **Modelo de información de referencia (RIM)**    
 El modelo de información de HL7 de que toda la demás información derivan modelos (por ejemplo, R-MIMs) y los mensajes.  
  
 **Modelo de información de mensaje refinados (R-MIM)**    
 Una estructura de información que representa los requisitos para un conjunto de mensajes. Un subconjunto restringido de la LLANTA que puede contener clases adicionales que se clonan desde clases RIM. Contiene los tipos de clases, atributos, las asociaciones y datos que son necesarios para admitir uno o más mensajes descripción de la jerarquía (HMDs). Un solo mensaje puede mostrarse como un canal determinado a través de las clases dentro de un R-MIM.  

## <a name="s"></a>S  
 **escenario**    
 En el modelado de Lenguaje unificado (UML), "una única ruta de acceso de ejecución a través de un caso de uso único". Una declaración de eventos que se definen como una secuencia de interacciones pertinentes de atención médica. El escenario proporciona un conjunto de interacciones que espera el Comité de modelado que aparecen normalmente en el dominio. Normalmente, se crea un diagrama de secuencia para mostrar un grupo de interacciones para un escenario único. Cada escenario se muestra como un subconjunto del modelo de interacción.  
  
 **esquema**    
 1. Una presentación esquemática, un marco estructurado o un plan. 
 2. Un conjunto de requisitos que deben cumplirse para un documento o un conjunto de datos como una expresión válida en el contexto de gramática. Un esquema XML es una especificación de lenguaje de marcado generalizado estándar (SGML) de la estructura de un documento o un conjunto de datos.

## <a name="next-steps"></a>Pasos siguientes
[Entidades - Explorador de configuración de BTAHL7](parties-tab.md)  
[Configuración global: el Explorador de configuración de BTAHL7](global-settings-tab.md)  
[Ayuda de interfaz de usuario de cuadro de cuadro de diálogo Propiedades de transporte MLLP](mllp-transport-properties-dialog-box-ui-help.md)