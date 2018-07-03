---
title: Glosario de Acelerador para HL7 en BizTalk Server | Microsoft Docs
description: Términos comunes y definiciones para conocer y aprenda a usar el Acelerador de BizTalk para HL7
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
ms.openlocfilehash: b632f494766974079ec13dd0803ae776c96adfe2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997885"
---
# <a name="glossary"></a>Glosario
Acelerador de Microsoft BizTalk para HL7 utiliza los siguientes términos y definiciones.

## <a name="a"></a>Un    
 **Artefacto**    
 Los artefactos que componen la votación de HL7 V3.0 son las entregas resultantes de la detección, análisis y las actividades de diseño que dan lugar a la creación de especificaciones del mensaje.  
  
 Dentro de los estándares de HL7 V3.0, los componentes que constituyen la documentación son artefactos. Esto incluye los guiones gráficos, roles de aplicación, eventos de desencadenador, las especificaciones del modelo de información de mensaje de dominio (D-MIMs), especificaciones refinando el modelo de información de mensaje (R-MIMs), specificatins(HMDs) jerárquica descripción del mensaje, tipos de mensajes, e interacciones.  
  
 **identificador del artefacto**    
 Un Comité técnico envía y proporciona un identificador único que se asigna mediante la concatenación de la subsección, dominio y el artefacto de código, un número de 6 dígitos no significativos, un código de dominio Kerberos de 2 dígitos y un número de versión de 2 dígitos de cada artefacto.  

## <a name="c"></a>C
  
 **cardinalidad**    
 La propiedad de un elemento de datos (el número de veces que un elemento de datos puede repetir dentro de una única repetición de una vista de objetos) o una columna en la descripción del mensaje jerárquica (el número mínimo y máximo de apariciones del elemento message). Consulte la descripción del mensaje jerárquica.  
  
## <a name="d"></a>D   
 **Dominio**    
 1. El problema o asunto solucionarse mediante un conjunto de mensajes de HL7 o un sistema ("dominio de aplicación"). Un área determinada de interés en la atención médica. 
 2. El conjunto de valores posibles de un tipo de datos, un atributo o un componente de tipo de datos. Consulte vocabulario dominio. 
 3. Un grupo de interés dentro de HL7, como la administración de farmacia, laboratorio, paciente.  
  
## <a name="e"></a>E 
 **Evento**    
 1. Un estímulo que provoca un cambio de estado importantes de un objeto. Una señal que invoca el comportamiento de un objeto. Ver eventos de desencadenador. 
 2. Un valor de dominio de vocabulario para estado de ánimo.  
  
 
## <a name="h"></a>H
**Descripción del mensaje jerárquica (HMD)**    
 Especificación de los campos exactos de un mensaje y su agrupación, la secuencia, opcionalidad y cardinalidad. Contiene tipos de mensaje para una o varias de las interacciones o representa uno o varios tipos de elemento de mensaje común. Se trata de la estructura de la normativa principal para los mensajes de HL7.  
  
## <a name="m"></a>M  
 **obligatorio**    
 Una columna en la descripción de mensaje jerárquica (HMD). Si la inclusión de un atributo obligatorio, todos los elementos del mensaje en función de este atributo debe contener un valor distinto de null o deben tener un valor predeterminado que no es null.  
  
  
 **Mensaje**    
 Un paquete de información se comunica desde una aplicación a otra. Vea el tipo de mensaje y la instancia de mensaje.  
  
 **Marco de desarrollo de mensaje (MDF)**    
 La colección de modelos, métodos y herramientas que componen la metodología para especificar los mensajes de HL7 V3.0. Los desarrolladores de los estándares de HL7 usar este marco de trabajo. La guía V3.0 se resume el contenido de la metodología.  
  
 **elemento Message**    
 Una unidad de estructura dentro de un tipo de mensaje.  
  
 **tipo de elemento de mensaje**    
 Una parte de un tipo de mensaje que describe uno de los elementos del mensaje.  
  
 **instancia de mensaje**    
 Un mensaje que tiene el formato para una transmisión específica. El mismo tipo de mensaje puede describir dos mensajes e identificar con la misma interacción y aún varían en la instancia debido a las variaciones de valores, presencia, o la ausencia de los datos que se envían y diferentes cardinalidades de las colecciones. En caso contrario, los mensajes idénticos pueden ser instancias diferentes si se envían en distintos momentos o por otro remitente.  
  
 **carga del mensaje**    
 Transportan datos en un mensaje.  
  
 **Tipo de mensaje**    
 La organización de los elementos de mensajes que se especifica en una descripción de mensaje jerárquica (HMD). Cada tipo de mensaje se comunica como parte de una o varias de las interacciones en el modelo de interacción. Un tipo de mensaje en vigor constituye un conjunto de reglas para construir un mensaje determinado en un conjunto específico de datos de instancia. También define las reglas para analizar un mensaje para recuperar los datos de instancia. El tipo de mensaje es independiente de la especificación de la tecnología de implementación, por lo que si los mismos datos se envían mediante el mismo tipo de mensaje y las especificaciones de tecnología de implementación diferente, el tipo de mensaje puede ser transliteración de uno a otro.  

## <a name="p"></a>P  
 **Propiedad**    
 Cualquier atributo, asociación, método o modelo de estado definidos para una clase u objeto. En un HMD, la columna que indica el nombre de la clase, atributo o asociación rol tal y como aparece en el modelo de información de referencia (RIM).  

## <a name="r"></a>R  
 **Modelo de información de referencia (RIM)**    
 El modelo de información de HL7 de que toda la demás información derivan modelos (por ejemplo, R-MIMs) y los mensajes.  
  
 **Modelo de información de mensaje refinados (R-MIM)**    
 Una estructura de información que representa los requisitos para un conjunto de mensajes. Un subconjunto restringido de la LLANTA que puede contener clases adicionales que se clonan desde clases RIM. Contiene los tipos de clases, atributos, las asociaciones y datos que son necesarios para admitir uno o más mensajes descripción de la jerarquía (HMDs). Un solo mensaje puede mostrarse como una ruta concreta a través de las clases dentro de un R-MIM.  

## <a name="s"></a>S  
 **Escenario**    
 En el modelado de Lenguaje unificado (UML), "una sola ruta de acceso de ejecución a través de un caso de uso único". Una declaración de eventos que se define como una secuencia de interacciones pertinentes en la atención médica. El escenario proporciona un conjunto de interacciones que espera el Comité de modelado suelen producirse en el dominio. Normalmente, se crea un diagrama de secuencia para mostrar un grupo de interacciones de un escenario único. Cada escenario se muestra como un subconjunto del modelo de interacción.  
  
 **schema**    
 1. Una presentación de la forma de diagrama, un marco de trabajo estructurado o un plan. 
 2. Un conjunto de requisitos que deben cumplirse para un documento o un conjunto de datos que puedan ser una expresión válida dentro del contexto de gramática. Un esquema XML es una especificación de lenguaje de marcado generalizado estándar (SGML) de la estructura de un documento o un conjunto de datos.

## <a name="next-steps"></a>Pasos siguientes
[Entidades: Explorador de configuración de BTAHL7](parties-tab.md)  
[Configuración global: Explorador de configuración de BTAHL7](global-settings-tab.md)  
[Ayuda de la UI de cuadro de diálogo MLLP transporte propiedades](mllp-transport-properties-dialog-box-ui-help.md)