---
title: 'TMA de ejemplo: BizTalk adaptador de Message Queue | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security examples [TMA], MSMQ adapters
- architecture, examples
- MSMQ adapters, TMA
- DFD, MSMQ adapters
- MSMQ adapters, data flow
ms.assetid: 15b4a540-2fcd-4668-b4b4-757f23ebd83e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91f37c57c24bdd37c0f2cc0399a797050228aa54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272460"
---
# <a name="sample-tma-biztalk-message-queuing-adapter"></a>TMA de ejemplo: El adaptador de BizTalk para Message Queue
En este tema se presenta el análisis de modelo de amenazas (TMA) para el escenario del adaptador de Message Queue Server de BizTalk de la arquitectura de ejemplo.  
  
## <a name="step-1-collect-background-information-biztalk-message-queuing-adapter-scenario"></a>Paso 1. Recopilar información básica (escenario de adaptador de puesta en cola de mensaje de BizTalk)  
 Esta sección contiene el diagrama de flujo de datos (DFD) del escenario del adaptador de BizTalk para Message Queue de la arquitectura de ejemplo. La siguiente ilustración muestra la arquitectura de ejemplo del escenario de los adaptadores de HTTP y SOAP.  
  
 **Figura 1: arquitectura de ejemplo para el escenario del adaptador de Message Queue Server de BizTalk**  
  
 ![Ejemplo de arquitectura para Message Queue Server de BizTalk](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")  
  
 El resto de información de segundo plano es el mismo para los cuatro escenarios de uso y se ha descrito anteriormente en [información general acerca de escenarios de ejemplo](../core/background-information-for-sample-scenarios.md).  
  
### <a name="data-flow-diagram"></a>Diagrama de flujo de datos  
 En la siguiente ilustración, aparece el DFD de la arquitectura de ejemplo al utilizar el adaptador de BizTalk para Message Queue.  
  
 **Figura 2: DFD de la arquitectura de ejemplo del escenario de adaptador de Message Queue Server de BizTalk**  
  
 ![Ejemplo de arquitectura para Message Queue Server de BizTalk](../core/media/tdi-sec-refarch-dfd-msmq.gif "TDI_Sec_RefArch_DFD_MSMQ")  
  
 El flujo de datos es el siguiente:  
  
1.  Un socio envía un mensaje utilizando Message Queue o BizTalk para Message Queue. El mensaje se empaqueta con el formato adecuado y se envía a través de la red. Si utiliza Active Directory, el mensaje atravesará una serie de enrutadores de colas de mensajes hasta alcanzar su destino (el servidor BizTalk Server que ejecuta una instancia de host del adaptador de recepción de BizTalk para Message Queue).  
  
2.  Una instancia de host en proceso del adaptador de recepción de BizTalk para Message Queue recibe con regularidad el mensaje procedente de un enrutador de Message Queue (a través del servidor de seguridad 2), realiza el procesamiento inicial, envía las respuestas de red correctas del modo definido en el protocolo de red y coloca el mensaje en la base de datos de cuadro de mensajes.  
  
3.  Una instancia del host de procesamiento que está suscrito al mensaje lo recoge en la base de datos de cuadro de mensajes, lleva a cabo todo el procesamiento adicional y vuelve a colocarlo en ésta.  
  
4.  Una instancia del host In-Process que tiene el adaptador de envío de BizTalk para Message Queue recoge el mensaje de la base de datos de cuadro de mensajes. El mensaje se somete a un procesamiento final en la canalización de envío y, a continuación, se envía al socio o la aplicación servidor a través de la red y el servidor de seguridad 2.  
  
## <a name="step-2-create-and-analyze-the-threat-model-biztalk-message-queuing-adapter-scenario"></a>Paso 2. Crear y analizar el modelo de amenazas (escenario del adaptador puesta en cola de mensaje de BizTalk)  
 Esta sección contiene el resultado del TMA del escenario del adaptador de BizTalk para Message Queue de la arquitectura de ejemplo.  
  
-   **Identificar puntos de entrada, límites de confianza y flujo de datos -** ver la información básica descrita en el paso 1 y en [información general acerca de escenarios de ejemplo](../core/background-information-for-sample-scenarios.md).  
  
-   **Crear una lista de amenazas identificadas -** utilizamos la siguiente categorización para todas las entradas de DFD para identificar posibles amenazas para el escenario: **S**poofing identificar, **T** lteración con datos, **R**epudiation, **I**revelación de información, **d.** denegación de servicio, y **E**levación de privilegios. La siguiente tabla contiene la evaluación del riesgo de las amenazas que identificamos al usar el adaptador de BizTalk para Message Queue para enviar y recibir mensajes del servidor de BizTalk Server.  
  
 **Tabla 1: lista de amenazas identificadas**  
  
|Amenaza|Description|Asset|Impacto|  
|------------|-----------------|-----------|------------|  
|Envío de gran cantidad de mensajes a la ubicación de recepción|Un usuario malintencionado puede enviar una gran cantidad de mensajes válidos o no válidos y saturar la aplicación.|Entorno de BizTalk Server|Denegación del servicio|  
|El encabezado del mensaje no está cifrado durante su desplazamiento a través de la red|El encabezado del mensaje está visible durante el tránsito entre la cola y el adaptador de recepción de BizTalk para Message Queue y, por tanto, es posible que los usuarios malintencionados lo lean y manipulen.|Encabezado del mensaje|Manipulación de datos<br /><br /> Revelación de información|  
|Un usuario no autorizado puede establecer una conexión de red con el servidor BizTalk Server que ejecuta el host de Message Queue Server de BizTalk.|No es posible utilizar una lista de acceso discrecional (DACL) para restringir el acceso a la ubicación de recepción de BizTalk para Message Queue. Por consiguiente, cualquier usuario que pueda establecer una conexión de red con el servidor BizTalk Server que ejecuta una instancia de host del adaptador de recepción de BizTalk para Message Queue y el puerto 1801 puede enviar mensajes a la ubicación de recepción de BizTalk para Message Queue.|Entorno de BizTalk Server|Rechazo<br /><br /> Manipulación de datos<br /><br /> Revelación de información<br /><br /> Denegación del servicio<br /><br /> Elevación de privilegios|  
|Un usuario malintencionado podría manipular los mensajes antes que el servidor BizTalk Server los reciba.|Un usuario malintencionado puede interceptar el mensaje mientras está en tránsito y modificarlo.|Cuerpo del mensaje|Manipulación de datos<br /><br /> Revelación de información|  
  
## <a name="step-3-review-threats-biztalk-message-queuing-adapter-scenario"></a>Paso 3. Analizar las amenazas (escenario del adaptador puesta en cola de mensaje de BizTalk)  
 Esta sección contiene los resultados del análisis de riesgos que se realizó para las amenazas identificadas en el escenario del adaptador de BizTalk para Message Queue para la arquitectura de ejemplo. Después de la reunión del modelo de amenazas principal, se analizamos las amenazas y usa las siguientes categorías de impacto para identificar el riesgo de cada amenaza: **d.** años potenciales, **R**apacidad de reproducción, **E**provechamiento, **A**usuarios afectados y **d.** capacidad de descubrimiento.  
  
 En la tabla siguiente enumera la evaluación del riesgo de las amenazas identificadas al usar el adaptador de BizTalk para Message Queue para enviar y recibir mensajes hacia y desde BizTalk Server.  
  
 **Tabla 2 evaluación del riesgo de las amenazas identificadas**  
  
|Amenaza|Impacto|Posibilidad del daño|Posibilidad de reproducir la amenaza|Posibilidad de que se aproveche|Usuarios afectados|Posibilidad de descubrir la amenaza|Exposición al riesgo|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|Envío de gran cantidad de mensajes a la ubicación de recepción|Denegación del servicio|8|7|7|7|5|6.8|  
|El encabezado del mensaje no está cifrado durante su desplazamiento a través de la red|Manipulación de datos<br /><br /> Revelación de información|8|10|8|3|5|6.8|  
|Un usuario no autorizado puede establecer una conexión de red con el servidor BizTalk Server que ejecuta el host de Message Queue Server de BizTalk.|Rechazo<br /><br /> Manipulación de datos<br /><br /> Revelación de información<br /><br /> Denegación del servicio<br /><br /> Elevación de privilegios|8|10|9|9|9|9|  
|Un usuario malintencionado podría manipular los mensajes antes que el servidor BizTalk Server los reciba.|Manipulación de datos<br /><br /> Revelación de información|5|7|6|5|7|6|  
  
## <a name="step-4-identify-mitigation-techniques-biztalk-message-queuing-adapter-scenario"></a>Paso 4. Identificar las técnicas de mitigación (escenario del adaptador puesta en cola de mensaje de BizTalk)  
 Esta sección contiene algunas técnicas de mitigación para las amenazas identificadas en el escenario del adaptador de BizTalk para Message Queue para la arquitectura de ejemplo.  
  
 La siguiente tabla enumera las tecnologías y técnicas de mitigación para las amenazas identificadas al usar el adaptador de BizTalk para Message Queue para enviar y recibir mensajes del servidor BizTalk Server.  
  
 **Tabla 3 tecnologías y técnicas de mitigación**  
  
|Amenaza|Impacto|Exposición al riesgo|Tecnologías y técnicas de mitigación|  
|------------|------------|-------------------|--------------------------------------------|  
|Envío de gran cantidad de mensajes a la ubicación de recepción|Denegación del servicio|6.8|Utilice el adaptador de BizTalk para Message Queue en el modo de autenticación necesaria. Establecer el **necesita autenticación de MSMQ** marca en la ubicación de recepción y **autenticación requerido (quitar mensajes)** en el puerto de recepción.<br /><br /> Configure BizTalk para Message Queue para requerir la autenticación basada en certificados. Este funcionamiento se produce en el nivel de adaptadores y es distinto del componente de resolución de entidades de las canalizaciones de BizTalk. El certificado público puede configurarse para incluirlo en el mensaje entrante. Éste es el único modo de autenticación de clientes disponible para Message Queue Server de BizTalk. Para usar este modo de autenticación de clientes, debe instalar BizTalk para Message Queue con el modo de integración de Active Directory. Si usa esta característica, no olvide activar la **requerir autenticación** ubicación de recepción de la casilla de verificación en el cuadro de diálogo de propiedades de BizTalk para Message Queue.|  
|El encabezado del mensaje no está cifrado durante su desplazamiento a través de la red|Manipulación de datos<br /><br /> Revelación de información|6.8|Use la seguridad de Protocolo Internet (IPSec) para proteger el encabezado y el cuerpo del mensaje en su tránsito de un servidor a otro.|  
|Un usuario no autorizado puede establecer una conexión de red con el servidor BizTalk Server que ejecuta el host de Message Queue Server de BizTalk.|Rechazo<br /><br /> Manipulación de datos<br /><br /> Revelación de información<br /><br /> Denegación del servicio<br /><br /> Elevación de privilegios|9|Cree una canalización personalizada con un componente de canalización de resolución de entidades y configúrelo para usar el Id. de remitente (SID) para resolver la entidad. Establecer el **resolver entidad mediante certificado** propiedad **False**y el **resolver entidad mediante SID** propiedad **True**. Para obtener más información, consulte [componente de canalización de resolución de entidad](../core/party-resolution-pipeline-component.md).<br /><br /> En el puerto de recepción, establezca la **autenticación** propiedad **requerido (quitar mensajes)**.|  
|Un usuario malintencionado podría manipular los mensajes antes que el servidor BizTalk Server los reciba.|Manipulación de datos<br /><br /> Revelación de información|6|Utilice la autenticación del nivel de protocolos para asegurarse de que el mensaje no ha sido manipulado mientras estaba en tránsito. Para usar la autenticación del nivel de protocolos, necesita un enrutador de Message Queue en el dominio de negocio electrónico. Configure el servidor BizTalk Server de la forma siguiente:<br /><br /> -En el **mensajería de BizTalk** página del Administrador de configuración, proporcione el nombre del enrutador.<br />-Para el puerto de recepción, establezca la **autenticación** propiedad **requerido (quitar mensajes)** o **requerido (mantener mensajes)**.<br />-Para el controlador de envío, en la **General** ficha la **enrutador de MSMQ** cuadro Nombre, escriba el nombre del enrutador de Message Queue Server.<br />-Para el puerto de envío, seleccione **utilizar autenticación de MSMQ**.|  
  
## <a name="see-also"></a>Vea también  
 [Análisis de modelo de amenazas](../core/threat-model-analysis.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenaza](../core/sample-scenarios-for-threat-model-analysis.md)   
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)