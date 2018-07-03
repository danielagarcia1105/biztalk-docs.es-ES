---
title: 'TMA de ejemplo: Adaptador de archivo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- DFD, File adapters
- File adapters, TMA
- examples, File adapters
- security examples [TMA], File adapters
ms.assetid: bcb862c0-fe02-4335-8b59-242d28049e3f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8422ae5d3829efc036c85f90fca80ca8f976289
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982853"
---
# <a name="sample-tma-file-adapter"></a>TMA de ejemplo: Adaptador de archivo
En este tema se presenta el análisis de modelo de amenaza (TMA) del escenario del adaptador de archivo de la arquitectura de ejemplo. En la siguiente ilustración se muestra la arquitectura de ejemplo para el escenario del adaptador de archivo.  
  
 **Figura 1 arquitectura de ejemplo para el escenario del adaptador de archivo**  
  
 ![Ejemplo de arquitectura de adaptador de archivo](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")  
  
## <a name="step-1-collect-background-information-file-adapter-scenario"></a>Paso 1. Recopilar información básica (escenario del adaptador de archivo)  
 Esta sección contiene el diagrama de flujo de datos (DFD) del escenario del adaptador de archivo de la arquitectura de ejemplo.  
  
 Toda la información en segundo plano es el mismo para los cuatro escenarios de uso y se ha descrito anteriormente en [información general acerca de escenarios de ejemplo](../core/background-information-for-sample-scenarios.md).  
  
### <a name="data-flow-diagram"></a>Diagrama de flujo de datos  
 La siguiente ilustración muestra el DFD de la arquitectura de ejemplo cuando se utiliza el adaptador de archivo.  
  
 **Figura 2: DFD de la arquitectura de ejemplo del escenario de adaptador de archivo**  
  
 ![Ejemplo de arquitectura para DFD](../core/media/tdi-sec-refarch-dfd-file.gif "TDI_Sec_RefArch_DFD_FILE_")  
  
 El flujo de datos es el siguiente:  
  
1.  Un socio coloca un mensaje (a través del servidor de seguridad 1) en el servidor de archivos de la red perimetral de la intranet.  
  
2.  Una instancia de un host In-Process del adaptador de recepción de archivo realiza sondeos en el servidor de archivos con regularidad para buscar nuevos mensajes (a través del servidor de seguridad 2). Cuando encuentra un nuevo mensaje, lo recupera, realiza el procesamiento inicial y lo coloca en la base de datos de cuadro de mensajes.  
  
3.  Una instancia del host de procesamiento que está suscrito al mensaje lo recoge en la base de datos de cuadro de mensajes, lleva a cabo todo el procesamiento adicional y vuelve a colocarlo en ésta.  
  
4.  Una instancia del host In-Process que tiene el adaptador de envío de archivo recoge el mensaje de la base de datos de cuadro de mensajes. El mensaje se somete a un procesamiento final en la canalización de envío y, a continuación, se envía al servidor de archivos a través de la red y el servidor de seguridad 2.  
  
5.  El socio recoge el mensaje del servidor de archivos.  
  
## <a name="step-2-create-and-analyze-the-threat-model-file-adapter-scenario"></a>Paso 2. Crear y analizar el modelo de amenazas (escenario del adaptador de archivo)  
 Esta sección proporciona los resultados del TMA del escenario del adaptador de archivo de la arquitectura de ejemplo.  
  
- **Identificar puntos de entrada, límites de confianza y flujo de datos -** ver la información básica descrita anteriormente en "Recopilar en segundo plano información de archivo de escenario del adaptador" y "Información general para todos los escenarios."  
  
- **Crear una lista de amenazas identificadas -** utilizamos la siguiente categorización para todas las entradas del DFD para identificar posibles amenazas al escenario: **S**uplantación identificar, **T**lteración con los datos, **R**epudio, **me**ivulgación de información, **d.** enegación de servicio, y **E**levación de privilegios. La siguiente tabla enumera las amenazas que identificamos al usar el adaptador de archivo para enviar y recibir mensajes del servidor de BizTalk Server.  
  
  **Tabla 1: lista de amenazas identificadas**  
  
|Amenaza|Descripción|Asset|Impacto|  
|------------|-----------------|-----------|------------|  
|Un usuario no autorizado puede recuperar datos de la carpeta de destino de los archivos.|Si no ha configurado listas seguras de control de acceso discrecional (DACL) para las carpetas que utiliza el adaptador de archivo, un usuario no autorizado podría descargar mensajes en la ubicación de recepción de archivos o recogerlos en la ubicación de envío de archivos.|Cuerpo del mensaje|Manipulación de datos<br /><br /> Revelación de información|  
|Un usuario no autorizado podría enviar mensajes a BizTalk Server|Si los usuarios tienen permisos de escritura en la carpeta de archivos en la que BizTalk Server recoge los mensajes, un usuario no autorizado podría enviar mensajes a BizTalk Server.|Cuerpo del mensaje|Denegación del servicio<br /><br /> Elevación de privilegios|  
  
## <a name="step-3-review-threats-file-adapter-scenario"></a>Paso 3. Analizar las amenazas (escenario del adaptador de archivo)  
 Esta sección contiene los resultados del análisis de riesgos que se realizó para las amenazas identificadas en el escenario del adaptador de archivo de la arquitectura de ejemplo. Después de la reunión del modelo de amenazas principal, hemos revisado las amenazas y usa las siguientes categorías de impacto para identificar el riesgo de cada amenaza: **d.** años potenciales, **R**apacidad de reproducción, **E**provechamiento, **A**usuarios afectados y **d.** capacidad de descubrimiento.  
  
 La siguiente tabla contiene la evaluación del riesgo de las amenazas que identificamos al usar el adaptador de archivo para enviar y recibir mensajes del servidor de BizTalk Server.  
  
 **Evaluación del riesgo de la tabla 2 para las amenazas identificadas**  
  
|Amenaza|Impacto|Posibilidad del daño|Posibilidad de reproducir la amenaza|Posibilidad de que se aproveche|Usuarios afectados|Posibilidad de descubrir la amenaza|Exposición al riesgo|  
|------------|------------|----------------------|---------------------|--------------------|--------------------|---------------------|-------------------|  
|Un usuario no autorizado puede recuperar datos de la carpeta de destino de los archivos.|Manipulación de datos<br /><br /> Revelación de información|4|7|5|4|6|5.2|  
|Un usuario no autorizado podría enviar mensajes a BizTalk Server|Denegación del servicio<br /><br /> Elevación de privilegios|4|7|5|4|5|5.2|  
  
## <a name="step-4-identify-mitigation-techniques-file-adapter-scenario"></a>Paso 4. Identificar las técnicas de mitigación (escenario del adaptador de archivo)  
 Esta sección contiene algunas técnicas de mitigación para las amenazas identificadas en el escenario del adaptador de archivo de la arquitectura de ejemplo.  
  
 La siguiente tabla enumera las tecnologías y técnicas de mitigación para las amenazas identificadas al usar el adaptador de archivo para enviar y recibir mensajes del servidor BizTalk Server.  
  
 **Tabla 3 tecnologías y técnicas de mitigación**  
  
|Amenaza|Impacto|Exposición al riesgo|Tecnologías y técnicas de mitigación|  
|------------|------------|-------------------|--------------------------------------------|  
|Un usuario no autorizado puede recuperar datos de la carpeta de destino de los archivos.|Manipulación de datos<br /><br /> Revelación de información|5.2|Para la carpeta en la que BizTalk Server recoge los mensajes, utilice una lista segura de control de acceso discrecional (DACL) de la manera siguiente:<br /><br /> -Para la cuenta de servicio para la instancia de host para el host que ejecuta el adaptador de recepción, establecer leer, escribir, eliminar archivos y eliminar permisos de las subcarpetas y archivos en el directorio desde el que la ubicación de recepción de archivo recoge los mensajes.<br />-Para el usuario externo o la aplicación que descarga archivos en esta carpeta, conjunto de permisos de escritura.<br />-Para el grupo de administradores de BizTalk, establezca el control total.<br /><br /> Para la carpeta en la que BizTalk Server descarga los mensajes, utilice una lista segura de control de acceso discrecional (DACL) de la manera siguiente:<br /><br /> -Para la cuenta de servicio para la instancia de host para el host que ejecuta el adaptador de envío, establezca permisos de escritura.<br />-Para el usuario externo o la aplicación que descarga archivos en esta carpeta, conjunto de permisos de lectura.<br />-Para el grupo de administradores de BizTalk, establezca el control total.|  
|Un usuario no autorizado podría enviar mensajes a BizTalk Server|Denegación del servicio<br /><br /> Elevación de privilegios|5.2|Configure listas DACL seguras en los directorios de destino de la ubicación de recepción del modo indicado anteriormente.|  
  
## <a name="see-also"></a>Vea también  
 [Análisis de modelo de amenazas](../core/threat-model-analysis.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenazas](../core/sample-scenarios-for-threat-model-analysis.md)   
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)