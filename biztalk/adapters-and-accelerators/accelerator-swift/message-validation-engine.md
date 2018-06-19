---
title: Motor de validación de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message validation engine
- errors, validating
- XML validation
- parsing validation
- BRE policies, validating
- errors, messages
- messages, errors
- validating, messages
- validating, BRE policies
- validating, XML
- messages, validating
- validating, errors
- validating, parsing
ms.assetid: 4ba0b75e-665b-4771-b04f-5bc3e90d83f0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbdcb375c04e4c9684b2a805c7a7a7315f46f83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209036"
---
# <a name="message-validation-engine"></a>Motor de validación de mensajes
Una de las características más importantes proporcionadas por [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] es la capacidad para validar totalmente SWIFT mensajes recibidos de los sistemas back-end destinados a la red SWIFT o recibidos desde la red SWIFT (enviada por los socios comerciales). Validar los mensajes salientes de SWIFT garantiza que los mensajes se ajustan a los estándares SWIFT y que la red SWIFT no rechazará los mensajes.  
  
 Validar los mensajes entrantes de SWIFT se asegura de que mensajes procedentes de otras entidades financieras siguen determinados contratos (reglas de negocios) específicos de la relación. En ambos escenarios, la capacidad de validar y capturar errores antes de confirmar un mensaje ayuda a reducir los costes de transacción y el coste total de propiedad (TCO).  
  
 En la lista siguiente se describe las cuatro partes que componen el motor de validación de A4SWIFT:  
  
-   Validación estructural realizada por el analizador de archivos planos  
  
-   Validación de datos realizada por el lector de validación de XML  
  
-   SWIFT validación de regla de red y el uso realizado por el motor de reglas de negocios (BRE)  
  
-   Marcador de mensaje y "mejor esfuerzo" error al recopilar  
  
## <a name="structural-validation-parsing"></a>Validación estructural (Analizar)  
 A4SWIFT analiza los mensajes de archivo sin formato SWIFT con esquemas XSD definidos para cada tipo de mensaje SWIFT según el estándar de SWIFT. Análisis de un archivo sin formato en XML garantiza que el archivo sin formato es estructuralmente correcto. Analizar también produce un XML que es más fácil de leer, manipular o transformar en otros formatos o tipos de mensaje. También puede validar el código XML con el esquema para la validez de los datos y usar el motor de reglas de negocios (BRE) para las evaluaciones más complejas.  
  
 El Desensamblador SWIFT, invoca el analizador de archivos sin formato de BizTalk para analizar los mensajes de archivo sin formato SWIFT invocados por el Desensamblador SWIFT. El Desensamblador SWIFT registra en una colección de errores de los detalles de los errores detectados durante el análisis y siempre intenta continuar con el análisis de los datos en un esfuerzo para recopilar errores estructurales tantos como sea posible en el primer paso. Sin embargo, la mayoría de los errores de análisis son irrecuperables y detener el procesamiento de mensajes en el primer error.  
  
 Para obtener más información acerca de la validación estructural, consulte [trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md).  
  
## <a name="data-validation-xml-validation"></a>Validación de datos (validación de XML)  
 Se pueden definir mensajes SWIFT que superan la validación estructural como XML correcto que cumple las especificaciones que defina los esquemas XSD. A4SWIFT produce un XML para los mensajes de SWIFT estructuralmente válidos durante la fase de análisis. A4SWIFT, a continuación, puede validar este XML es correcto de datos en función de las restricciones definidas en el esquema XSD correspondiente.  
  
 Estas restricciones incluyen tipos de datos, la longitud y los intervalos de valores definidos de acuerdo con el estándar de SWIFT. El Desensamblador SWIFT, invoca el lector para llevar a cabo la validación de datos de validación de XML.  
  
 El Desensamblador SWIFT registra en una colección de errores de los detalles de los errores encontrados durante la validación de XML y continúa la validación de los datos restantes para recopilar errores de validación XML tantos como sea posible en el primer paso. (A diferencia de los análisis, se garantiza la continuación de la validación XML).  
  
 Para obtener más información acerca de la validación de datos, vea [trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md).  
  
## <a name="swift-network-and-usage-rule-validation-bre-validation"></a>Red sencilla y validación de la regla de uso (validación de BRE)  
 A4SWIFT valida XML para los mensajes de SWIFT estructuralmente válidos para la exactitud de nivel de negocio con las directivas del motor de reglas de negocios (BRE). Estas directivas incluyen el cumplimiento de las reglas de red y el uso SWIFT y otras reglas complejas de campos cruzados definidos de acuerdo con el estándar de SWIFT. El Desensamblador SWIFT, invoca el BRE para realizar la validación de nivel de negocio.  
  
 El Desensamblador SWIFT registra en una colección de errores de los detalles de los errores encontrados durante la validación de BRE y continúa la validación de los datos restantes para recopilar errores de validación de BRE tantos como sea posible en el primer paso. (Como la validación de XML, se garantiza la continuación de la validación de BRE).  
  
 Para obtener más información acerca de la validación de regla de red y el uso SWIFT, consulte [trabajar con las directivas del BRE](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md).  
  
## <a name="validation-failures-and-message-marking"></a>Errores de validación y el marcado de mensaje  
 A4SWIFT recopila los errores de validación y detalles a través de cada fase de validación del mensaje: análisis estructural, la validación de XML y la validación de BRE. A4SWIFT recopila estos errores con una heurística "mejor esfuerzo" para recopilar tanta información de error acerca de un mensaje como sea posible. Esta funcionalidad permite que un mensaje de error para que todos los errores capturados e informó de una sola vez, en lugar de tener varias iteraciones de envío, validar, producirá un error, corregir, volver a enviar.  
  
 Los mensajes que tienen al menos un error detectado durante cualquier fase de validación en la colección de errores se consideran no válidos y no se pudieron. A4SWIFT publica estos mensajes en la base de datos de cuadro de mensajes, pero se marcan con propiedades promocionadas para indicar que el mensaje de error al validar y recuentos de errores de informe para cada fase de validación.  
  
 Además de las propiedades promocionadas, A4SWIFT serializa la colección de errores en XML y asocia la colección como una "parte de error" del mensaje de varias partes. El mensaje final está formada por el mensajes con errores en la parte del cuerpo y XML de la colección de errores en la parte de error y se ha mejorado con A4SWIFT promocionadas propiedades que indican un estado de error. El Desensamblador SWIFT publica este mensaje de varias partes en la base de datos de cuadro de mensajes.  
  
 BizTalk puertos de envío u orquestaciones pueden recuperar mensajes con errores de la base de datos de cuadro de mensajes si se suscribe a las propiedades promocionadas de A4SWIFT especiales. Puede hacer que las suscripciones para recuperar todos los mensajes con errores o solo los mensajes con un determinado número de errores de fases de validación concretas.  
  
 Después de recupera un mensaje de error, puede enviarlo a una aplicación de informes, una aplicación de reparación o proceso o un repositorio de error o se puede descartar los cambios.  
  
 Esta capacidad de suscribirse a los mensajes con errores (y diferenciar entre tipos de errores en la suscripción), junto con la recopilación de errores con datos completos de información XML asociado a cada mensaje con errores, constituye un marco de trabajo eficaces para el desarrollo sencillo de errores informes de aplicaciones, como proporcionadas por la reparación de mensajes y la nueva característica de envío que se instala el programa de instalación de A4SWIFT.  
  
 Para obtener más información acerca de errores de validación y el marcado de mensaje, consulte [trabajar con suscripciones de mensajes de error](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).  
  
## <a name="see-also"></a>Vea también  
 [Acelerador de BizTalk para SWIFT en tiempo de ejecución](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)