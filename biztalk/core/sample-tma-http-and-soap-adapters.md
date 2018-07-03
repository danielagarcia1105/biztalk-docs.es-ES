---
title: 'TMA de ejemplo: Los adaptadores de SOAP y HTTP | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- DFD, HTTP adapters
- security examples [TMA], SOAP adapters
- SOAP adapters, examples
- security examples [TMA], HTTP adapters
- examples, HTTP adapters
- DFD, SOAP adapter
- examples, SOAP adapters
- SOAP adapters, TMA
- HTTP adapters, TMA
ms.assetid: d9a40cff-92a1-4bc9-ae45-3a5857f70222
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd1b58a89ce123350ba3b6d7be0e665d4428429a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011485"
---
# <a name="sample-tma-http-and-soap-adapters"></a>TMA de ejemplo: Los adaptadores de SOAP y HTTP
En este tema se incluye el análisis de modelo de amenazas (TMA) del escenario de los adaptadores de HTTP y SOAP (servicios Web) para la arquitectura de ejemplo. La siguiente ilustración muestra la arquitectura de ejemplo del escenario de los adaptadores de HTTP y SOAP.  
  
 **Figura 1 arquitectura de ejemplo para el escenario de los adaptadores HTTP/SOAP**  
  
 ![Ejemplo de arquitectura de adaptador de SOAP o HTTP](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")  
  
## <a name="step-1-collect-background-information-http-and-soap-adapters-scenario"></a>Paso 1. Recopilar información básica (escenario de los adaptadores HTTP y SOAP)  
 Esta sección contiene el diagrama de flujo de datos (DFD) del escenario de los adaptadores de HTTP y SOAP (Servicios Web) de la arquitectura de ejemplo.  
  
 Toda la información en segundo plano es el mismo para los cuatro escenarios de uso y se ha descrito anteriormente en [información general acerca de escenarios de ejemplo](../core/background-information-for-sample-scenarios.md).  
  
### <a name="data-flow-diagram"></a>Diagrama de flujo de datos  
 En la siguiente ilustración, aparece el DFD de la arquitectura de ejemplo al utilizar los adaptadores de HTTP y SOAP (servicios Web).  
  
 **Figura 2: DFD de la arquitectura de ejemplo del escenario de adaptador HTTP/SOAP**  
  
 ![DFD para la arquitectura de ejemplo](../core/media/tdi-sec-refarch-dfd-http.gif "TDI_Sec_RefArch_DFD_HTTP")  
  
 El flujo de datos es el siguiente:  
  
1.  Un socio o un cliente envía un mensaje mediante HTTP, HTTPS o un servicio Web. El mensaje se enruta a la dirección IP del firewall 1.  
  
2.  El servidor de seguridad 1 retransmite el mensaje a través del servidores de seguridad 2 utilizando un proxy inverso.  
  
3.  El servidor de seguridad 2 enruta el mensaje hacia el servidor BizTalk Server que ejecuta una instancia de un host aislado para el adaptador de recepción HTTP o SOAP. El host aislado procesa el mensaje y lo coloca en la base de datos de cuadro de mensajes.  
  
4.  Una instancia del host de procesamiento que está suscrito al mensaje lo recoge en la base de datos de cuadro de mensajes, lleva a cabo todo el procesamiento adicional y vuelve a colocarlo en ésta.  
  
5.  Una instancia del host aislado que tiene un adaptador de envío HTTP o SOAP recoge el mensaje de la base de datos de cuadro de mensajes. El mensaje se somete a un procesamiento final en la canalización de envío y, a continuación, se devuelve al socio o cliente.  
  
6.  Durante el envío al socio o cliente, el mensaje se enruta a través de los servidores de seguridad 1 y 2 mediante el proxy inverso.  
  
## <a name="step-2-create-and-analyze-the-threat-model-http-and-soap-adapters-scenario"></a>Paso 2. Crear y analizar el modelo de amenazas (escenario de los adaptadores SOAP y HTTP)  
 Esta sección proporciona los resultados del TMA que se ha realizado para el escenario de los adaptadores de HTTP y SOAP (Servicios Web) de la arquitectura de ejemplo.  
  
- **Identificar puntos de entrada, límites de confianza y flujo de datos -** ver información básica descrita anteriormente en el paso 1 y [información general acerca de escenarios de ejemplo](../core/background-information-for-sample-scenarios.md).  
  
- **Crear una lista de amenazas identificadas -** utilizamos la siguiente categorización para todas las entradas del DFD para identificar posibles amenazas al escenario: **S**uplantación identificar, **T**lteración con los datos, **R**epudio, **me**ivulgación de información, **d.** enegación de servicio, y **E**levación de privilegios. La siguiente tabla enumera las amenazas que identificamos al usar los adaptadores de HTTP y SOAP para enviar y recibir mensajes del servidor de BizTalk Server.  
  
  **Tabla 1: lista de amenazas**  
  
|Amenaza|Descripción|Asset|Impacto|  
|------------|-----------------|-----------|------------|  
|Envío de un mensaje de tamaño infinito|Un usuario malintencionado podría enviar un mensaje de tamaño infinito.|Entorno de BizTalk Server|Denegación del servicio|  
|Envío de gran cantidad de mensajes a la ubicación de recepción|Un usuario malintencionado puede enviar una gran cantidad de mensajes válidos o no válidos y saturar la aplicación.|Entorno de BizTalk Server|Denegación del servicio|  
|Lectura del cuerpo de los mensajes en HTTP|Un usuario malintencionado podría interceptar el mensaje durante el tránsito del remitente al servidor de seguridad 1 y leer su contenido.|Carga del mensaje|Revelación de información|  
|Obtención de las credenciales de usuario del mensaje|Si se usa la autenticación básica y el mensaje contiene credenciales de usuario, un usuario malintencionado podría obtener acceso a éstas y utilizarlas para tener acceso a la aplicación.|Credenciales de usuario|Revelación de información<br /><br /> Elevación del privilegio|  
  
## <a name="step-3-review-threats-http-and-soap-adapters-scenario"></a>Paso 3. Analizar las amenazas (escenario de los adaptadores SOAP y HTTP)  
 Esta sección contiene los resultados del análisis de riesgos que se realizó para las amenazas identificadas en el escenario de los adaptadores de HTTP y SOAP (servicios Web) de la arquitectura de ejemplo. Después de la reunión del modelo de amenazas principal, hemos revisado las amenazas y usa las siguientes categorías de impacto para identificar el riesgo de cada amenaza: **d.** años potenciales, **R**apacidad de reproducción, **E**provechamiento, **A**usuarios afectados y **d.** capacidad de descubrimiento.  
  
 La siguiente tabla contiene la evaluación del riesgo de las amenazas que identificamos al usar los adaptadores de HTTP y SOAP para enviar y recibir mensajes del servidor de BizTalk Server.  
  
 **Tabla 2 evaluación del riesgo de amenazas**  
  
|Amenaza|Impacto|Posibilidad del daño|Posibilidad de reproducir la amenaza|Posibilidad de que se aproveche|Usuarios afectados|Posibilidad de descubrir la amenaza|Exposición al riesgo|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|Envío de un mensaje de tamaño infinito|Denegación del servicio|2|3|2|3|2|2.4|  
|Envío de gran cantidad de mensajes a la ubicación de recepción|Denegación del servicio|3|3|1|3|3|2.6|  
|Lectura del cuerpo de los mensajes en HTTP|Revelación de información|3|3|2|3|3|2.8|  
|Obtención de las credenciales de usuario del mensaje|Revelación de información<br /><br /> Elevación del privilegio|3|3|2|3|2|2.6|  
  
## <a name="step-4-identify-mitigation-techniques-http-and-soap-adapters-scenario"></a>Paso 4. Identificar las técnicas de mitigación (escenario de los adaptadores SOAP y HTTP)  
 Esta sección contiene algunas técnicas de mitigación para las amenazas identificadas en el escenario de los adaptadores de HTTP y SOAP (servicios Web) para la arquitectura de ejemplo.  
  
 La siguiente tabla enumera las tecnologías y técnicas de mitigación para las amenazas identificadas al usar los adaptadores de HTTP y SOAP para enviar y recibir mensajes del servidor BizTalk Server.  
  
 **Tabla 3 tecnologías y técnicas de mitigación**  
  
|Amenaza|Impacto|Exposición al riesgo|Tecnologías y técnicas de mitigación|  
|------------|------------|-------------------|--------------------------------------------|  
|Envío de un mensaje de tamaño infinito|Denegación del servicio|2.4|Limitar el tamaño máximo de los mensajes entrantes para cada URL y rechazar los que excedan este límite.<br /><br /> Para obtener más información, consulte [mitigación de ataques de denegación de servicio](../core/mitigating-denial-of-service-attacks.md).|  
|Envío de gran cantidad de mensajes a la ubicación de recepción|Denegación del servicio|2.6|El adaptador de SOAP aprovecha el protocolo HTTP para enviar y recibir mensajes de BizTalk Server. Por consiguiente, debe seguir las recomendaciones de seguridad para proteger los Servicios de Internet Information Server (IIS). Si usa IIS, asegúrese de que sigue las recomendaciones de IIS para configurar el aislamiento de aplicaciones.<br /><br /> Para obtener más información, vea el sitio Web de Microsoft TechNet en [ http://go.microsoft.com/fwlink/?LinkId=60951 ](http://go.microsoft.com/fwlink/?LinkId=60951).<br /><br /> Use la autenticación de clientes y la resolución de entidades para limitar el número de mensajes que se procesan a los que sean válidos y se hayan autorizado.|  
|Lectura del cuerpo de los mensajes en HTTP|Revelación de información|2.8|Se recomienda utilizar S/MIME para proteger el contenido de los mensajes que se envían al servidor BizTalk Server y se reciben de éste.<br /><br /> Se recomienda utilizar la Capa de sockets seguros (SSL) para proteger la transmisión de datos del servidor BizTalk Server y entre los componentes de éste distribuidos en todo el entorno.|  
|Obtención de las credenciales de usuario del mensaje|Revelación de información<br /><br /> Elevación del privilegio|2.6|Si utiliza la autenticación básica, o si no usa el cifrado en el nivel de mensajes, se recomienda emplear SSL tanto para recibir como para enviar mensajes, con lo que se garantizará que las personas no autorizadas no puedan leer las credenciales de usuario.|  
  
## <a name="see-also"></a>Vea también  
 [Análisis de modelo de amenazas](../core/threat-model-analysis.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenazas](../core/sample-scenarios-for-threat-model-analysis.md)   
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)