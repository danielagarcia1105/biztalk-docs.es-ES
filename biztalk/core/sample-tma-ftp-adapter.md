---
title: 'TMA de ejemplo: Adaptador de FTP | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- examples, FTP adapters
- security examples [TMA], FTP adapters
- FTP adapters, TMA
- DFD, FTP adapters
ms.assetid: c648f84a-c83a-44f0-adc9-a3f98b597506
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1dc1a7779b3dde57c1546ace3cd5ea191152d0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988095"
---
# <a name="sample-tma-ftp-adapter"></a>TMA de ejemplo: Adaptador de FTP
En este tema se presenta el análisis de modelo de amenaza (TMA) del escenario del adaptador de FTP de la arquitectura de ejemplo.  
  
 La siguiente ilustración muestra la arquitectura de ejemplo del escenario del adaptador de FTP.  
  
 **Figura 1 arquitectura de ejemplo para el escenario del adaptador de FTP**  
  
 ![Ejemplo de arquitectura de adaptador de FTP](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")  
  
## <a name="step-1-collect-background-information-ftp-adapter-scenario"></a>Paso 1. Recopilar información básica (escenario del adaptador de FTP)  
 Esta sección contiene el diagrama de flujo de datos (DFD) del escenario del adaptador de FTP de la arquitectura de ejemplo.  
  
 Toda la información en segundo plano es el mismo para los cuatro escenarios de uso y se ha descrito anteriormente en [información general acerca de escenarios de ejemplo](../core/background-information-for-sample-scenarios.md).  
  
### <a name="data-flow-diagram"></a>Diagrama de flujo de datos  
 La siguiente ilustración muestra el DFD de la arquitectura de ejemplo cuando se utiliza el adaptador de FTP.  
  
 **Figura 2: DFD de la arquitectura de ejemplo del escenario de adaptador FTP**  
  
 ![DFD para adaptador de FTP](../core/media/tdi-sec-refarch-dfd-ftp.gif "TDI_Sec_RefArch_DFD_FTP")  
  
 El flujo de datos es el siguiente:  
  
1.  Un socio o un cliente envía un mensaje al servidor FTP. El mensaje se enruta a la dirección IP del firewall 1.  
  
2.  El servidor de seguridad 1 recibe el mensaje y lo enruta hacia el servidor FTP ubicado en la red perimetral de Internet.  
  
3.  Una instancia de un host In-Process del adaptador de recepción FTP realiza sondeos en el servidor FTP con regularidad para buscar nuevos mensajes (a través del servidor de seguridad 2). Cuando encuentra un nuevo mensaje, lo recupera, realiza el procesamiento inicial y lo coloca en la base de datos de cuadro de mensajes.  
  
4.  Una instancia del host de procesamiento que está suscrito al mensaje lo recoge en la base de datos de cuadro de mensajes, lleva a cabo todo el procesamiento adicional y vuelve a colocarlo en ésta.  
  
5.  Una instancia del host In-Process que tiene el adaptador de envío FTP recoge el mensaje de la base de datos de cuadro de mensajes. El mensaje se somete a un procesamiento final en la canalización de envío y, a continuación, se envía al servidor FTP a través de la red y el servidor de seguridad 2.  
  
6.  A continuación, el servidor FTP enruta el mensaje hacia el socio o cliente a través del servidor de seguridad 1.  
  
## <a name="step-2-create-and-analyze-the-threat-model-ftp-adapter-scenario"></a>Paso 2. Crear y analizar el modelo de amenazas (escenario del adaptador de FTP)  
 Esta sección contiene los resultados del TMA del escenario del adaptador de FTP de la arquitectura de ejemplo.  
  
- **Identificar puntos de entrada, límites de confianza y flujo de datos -** ver la información básica descrita en el paso 1 y en [información general acerca de escenarios de ejemplo](../core/background-information-for-sample-scenarios.md).  
  
- **Crear una lista de amenazas identificadas -** utilizamos la siguiente categorización para todas las entradas del DFD para identificar posibles amenazas al escenario: **S**uplantación identificar, **T**lteración con los datos, **R**epudio, **me**ivulgación de información, **d.** enegación de servicio, y **E**levación de privilegios. La siguiente tabla enumera las amenazas que identificamos al usar el adaptador de FTP para enviar y recibir mensajes del servidor de BizTalk Server.  
  
  **Tabla 1: lista de las amenazas identificadas**  
  
|Amenaza|Descripción|Asset|Impacto|  
|------------|-----------------|-----------|------------|  
|El protocolo FTP no está protegido|La contraseña y el Id. de usuario del protocolo FTP se envían como texto sin cifrar. Un usuario malintencionado podría realizar un seguimiento de la red para obtener acceso a las credenciales. Los datos están expuestos.|Credenciales de usuario|Suplantación de identidad<br /><br /> Manipulación de datos<br /><br /> Revelación de información|  
|El servidor FTP está expuesto a ataques de servidores DHCP no autorizados.|Si el URI no contiene la contraseña del usuario pero está especificado en el controlador, la contraseña del controlador se está enviando actualmente al servidor FTP en el tiempo de ejecución. Si un servidor FTP deshonesto está escuchando las llamadas de autenticación, puede que se valga de este método para averiguar las contraseñas. Una posible solución es habilitar o deshabilitar el uso de la contraseña en el nivel del controlador.|Servidor FTP|Suplantación de identidad<br /><br /> Manipulación de datos<br /><br /> Revelación de información|  
  
## <a name="step-3-review-threats-ftp-adapter-scenario"></a>Paso 3. Analizar las amenazas (escenario del adaptador de FTP)  
 Esta sección contiene los resultados del análisis de riesgos que se realizó para las amenazas identificadas en el escenario del adaptador de FTP de la arquitectura de ejemplo. Después de la reunión del modelo de amenazas principal, hemos revisado las amenazas y usa el usan categorías para identificar el riesgo de cada amenaza afecta a la siguiente: **d.** años potenciales, **R**apacidad de reproducción, **E**provechamiento, **A**usuarios afectados y **d.** capacidad de descubrimiento.  
  
 La siguiente tabla contiene la evaluación del riesgo de las amenazas que identificamos al usar el adaptador de FTP para enviar y recibir mensajes del servidor de BizTalk Server.  
  
 **Evaluación del riesgo de la tabla 2 para las amenazas identificadas**  
  
|Amenaza|Impacto|Posibilidad del daño|Posibilidad de reproducir la amenaza|Posibilidad de que se aproveche|Usuarios afectados|Posibilidad de descubrir la amenaza|Exposición al riesgo|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|El protocolo FTP no está protegido|Suplantación de identidad<br /><br /> Manipulación de datos<br /><br /> Revelación de información|9|9|2|10|5|7|  
|El servidor FTP está expuesto a ataques de servidores DHCP no autorizados.|Suplantación de identidad<br /><br /> Manipulación de datos<br /><br /> Revelación de información|5|5|2|10|5|5.4|  
  
## <a name="step-4-identify-mitigation-techniques-ftp-adapter-scenario"></a>Paso 4. Identificar las técnicas de mitigación (escenario del adaptador de FTP)  
 Esta sección contiene algunas técnicas de mitigación para las amenazas identificadas en el escenario del adaptador de FTP de la arquitectura de ejemplo.  
  
 La siguiente tabla enumera las tecnologías y técnicas de mitigación para las amenazas identificadas al usar el adaptador de FTP para enviar y recibir mensajes del servidor BizTalk Server.  
  
 **Tabla 3 tecnologías y técnicas de mitigación**  
  
|Amenaza|Impacto|Exposición al riesgo|Tecnologías y técnicas de mitigación|  
|------------|------------|-------------------|--------------------------------------------|  
|El protocolo FTP no está protegido|Suplantación de identidad<br /><br /> Manipulación de datos<br /><br /> Revelación de información|7|El adaptador de FTP debe usarse en un entorno seguro y a través de una línea protegida.|  
|El servidor FTP está expuesto a ataques de servidores DHCP no autorizados.|Suplantación de identidad<br /><br /> Manipulación de datos<br /><br /> Revelación de información|5.4|Se recomienda colocar el servidor FTP remoto en una ubicación segura. Debe garantizar la seguridad física y de red de este servidor para minimizar los ataques de servidores DHCP no autorizados.|  
  
## <a name="see-also"></a>Vea también  
 [Análisis de modelo de amenazas](../core/threat-model-analysis.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenazas](../core/sample-scenarios-for-threat-model-analysis.md)   
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)