---
title: ¿Qué es la limitación de host? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host throttling, outbound
- host throttling, inbound
- host throttling, about host throttling
ms.assetid: 36d1818b-c8a2-4f23-bfb3-c034ee242f69
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4730a93b6491f53fc06004ca8bb0dcb0d970cc7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="what-is-host-throttling"></a>¿Qué es la limitación de host?
La mayoría de los procesamientos que tienen lugar en un servidor BizTalk sucede en una entidad lógica conocida como instancia de host de servidor BizTalk Server, que es un proceso que se ejecuta como un servicio de Windows o un proceso de host aislado del servidor BizTalk. Para administrar el uso de recursos por parte de un proceso de instancia de host, BizTalk Server utiliza un mecanismo de limitación ajustable que rige el flujo y el procesamiento de mensajes a través de una instancia de host.  
  
 El mecanismo de limitación modera la carga de trabajo de la instancia de host para garantizar que la carga de trabajo no supera la capacidad de la instancia de host o cualquier instancia de host de nivel inferior. El mecanismo de limitación también evita una condición conocida como contención de recursos que puede reducir el rendimiento general del proceso de instancia de host u otros procesos del sistema. La contención de recursos se produce cuando uno o varios procesos consumen un recurso limitado en su propio detrimento o el de otro proceso. Por ejemplo, el consumo excesivo de memoria o subprocesos puede provocar un error de asignación de memoria o demasiados modificadores de contexto de subproceso que pueden afectar al rendimiento del proceso. Una contención de recursos como esta puede ser perjudicial para el rendimiento general de BizTalk Server.  
  
 El mecanismo de limitación de host también detecta cuando se infrautilizan recursos disponibles. Si se desaprovechan recursos disponibles, el mecanismo de limitación permite que una instancia de host procese mensajes adicionales. El mecanismo de limitación de host supervisa continuamente los recursos disponibles para que se utilicen correctamente y ajusta el flujo de mensajes a través de la instancia de host.  
  
 El mecanismo de limitación de host del servidor BizTalk Server ayuda a garantizar que el sistema funcione a un nivel óptimo y sostenible.  
  
 Los parámetros de configuración de limitación de host se establecen para cada host independientemente en la consola de administración de BizTalk Server. Tenga en cuenta que los parámetros de configuración de limitación que se establecen para el host se aplican a cualquier o todos los controladores de recepción, controladores de envío u orquestaciones que se alojan en las instancias correspondientes de host. Si desea establecer parámetros de limitación que se apliquen sólo a un controlador de recepción, controlador de envío u orquestación entonces debe hacer lo siguiente:  
  
-   Cree un host nuevo y establezca adecuadamente los parámetros de limitación.  
  
-   Configure el controlador de recepción, controlador de envío u orquestación que se ejecuta en este host.  
  
-   Cree una o más instancias de este host para ejecutarse en su servidor BizTalk.  
  
## <a name="inbound-host-throttling"></a>Limitación de host de entrada  
 Host de entrada de limitación, también conocido como *limitación de publicación de mensajes* en BizTalk Server, se aplica a instancias de host que contienen adaptadores de recepción u orquestaciones que publican mensajes en la base de datos de cuadro de mensajes. Una condición de limitación de host de entrada se puede desencadenar bajo las condiciones siguientes:  
  
-   La cantidad de memoria, el número de subprocesos o el número de conexiones de base de datos usados por la instancia de host supera los umbrales de limitación definidos en **panel de configuración** disponible en el grupo de BizTalk y seleccione **Configuración**. Estos valores son puede medibles con contadores del monitor de rendimiento disponibles en el **BizTalk: agente** categoría de objeto de rendimiento.  
  
-   Los host de nivel inferior no pueden procesar los mensajes que están publicados. Esto aumenta el valor de la **recuento en la base de datos del mensaje** parámetro. El umbral en el que el **recuento en la base de datos del mensaje** valor desencadenadores una condición de limitación es configurable en el **Hosts** opción **panel de configuración**. El número de mensajes en la base de datos se puede medir con el **tamaño de base de datos** contador en el **BizTalk: agente** categoría de objeto de rendimiento.  
  
-   El **mensaje tasa entrante de publicación** para el host instancia supera la **tasa saliente de publicación de mensajes\***  especificado **factor de sobrecarga** valor. El **factor de sobrecarga** valor se define en **panel de configuración**, **Hosts** y, a continuación, **limitación basada en tasa**. La publicación tasas entrantes y salientes de mensajes se pueden medir con los contadores de monitor de rendimiento correspondientes en el **BizTalk: agente** categoría de objeto de rendimiento.  
  
-   Se ha modificado el comportamiento de limitación predeterminado. [Mediante el panel de configuración para la optimización de rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) describen los distintos valores que afectan el comportamiento de limitación.  
  
 Dependiendo de la gravedad de la condición de limitación, se realizan las acciones siguientes:  
  
-   Se implementa un retraso progresivo en la lógica de procesamiento de la instancia de host. El retraso se puede implementar cuando un subproceso del Gestor extremo (EPM) recibe un lote de mensajes del adaptador de transporte o cuando el EPM envía un lote de mensajes para publicarlos en la base de datos de cuadro de mensajes. Tanto la duración del retraso de procesamiento como el ritmo al que incrementa la duración aumentan con la gravedad de la condición de limitación.  
  
-   El número de subprocesos que están disponibles para el Gestor extremo (EPM) está restringido. El EPM recibe lotes de mensajes de adaptadores y publica los mensajes en la base de datos de cuadro de mensajes. De manera predeterminada, el EPM está configurado para utilizar 20 subprocesos por CPU. Si el mecanismo de limitación de host detecta una condición de esfuerzo para un procesamiento entrante entonces se puede reducir el número de subprocesos disponibles para el EPM hasta que se elimine la condición de esfuerzo. El EPM no puede procesar mensajes de adaptadores de transporte ni entregar lotes de mensajes a la base de datos de cuadro de mensajes a menos que un subproceso de EPM esté disponible para atender al lote de mensajes de entrada.  
  
-   El uso de memoria y otros recursos se reduce según proceda. BizTalk Server puede enviar instrucciones a otras clases de servicio para limitar el uso de memoria mediante la deshidratación de programaciones de ejecuciones, reducir el tamaño de la caché de memoria y limitando el uso de subprocesos que utilizan mucha memoria.  
  
 **Flujo de mensajes de entrada de adaptador al cuadro de mensajes**  
  
 ![Flujo de mensajes del adaptador al cuadro de mensajes entrantes](../core/media/inboundmsgflow.gif "InboundMsgFlow")  
  
## <a name="outbound-host-throttling"></a>Limitación de host de salida  
 Limitación de peticiones, también conocido como host de salida *limitación de procesamiento de mensajes* en BizTalk Server, se aplica a instancias de host que contienen orquestaciones o adaptadores de envío que reciben y entregan o procesan mensajes que han sido publicar en el cuadro de mensajes. Una condición de limitación de host de salida se puede desencadenar bajo las condiciones siguientes:  
  
-   La cantidad de memoria, el número de subprocesos o el número de conexiones de base de datos usados por la instancia de host supera los umbrales de limitación definidos en **limitación basada en recursos** en **panel de configuración de**. Estos valores son puede medibles con contadores del monitor de rendimiento disponibles en el **BizTalk: agente** categoría de objeto de rendimiento.  
  
-   El **tasa entrante de la entrega de mensajes** para el host instancia supera la **tasa saliente de la entrega de mensajes** \* especificado **factor de sobrecarga** valor . El **factor de sobrecarga** valor se define en el **limitación basada en tasa** ficha **panel de configuración**. Contadores de la entrega de mensajes se pueden medir las tasas entrantes y salientes con el monitor de rendimiento correspondiente en el **BizTalk: agente** categoría de objeto de rendimiento.  
  
-   El número de mensajes que se procesan simultáneamente mediante la instancia de host supera la **mensajes por CPU en curso** \* el número de CPU disponibles en el cuadro. El **mensajes en curso** umbral se define en el **limitación basada en recursos** ficha **panel de configuración**. El número de mensajes que se está procesando simultáneamente en la instancia de host se puede medir con el **número de mensajes en curso** contador de rendimiento en el **BizTalk: agente de** objeto de rendimiento categoría.  
  
-   Se ha modificado el comportamiento de limitación predeterminado. [Mediante el panel de configuración para la optimización de rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) describen los distintos valores que afectan el comportamiento de limitación.  
  
 Dependiendo de la gravedad de la condición de limitación, se realizan las acciones siguientes:  
  
-   Un retraso progresivo en la lógica de procesamiento de la instancia de host se implementa antes de entregar los mensajes al adaptador de transporte de salida o al motor de orquestación para procesar los mensajes. Tanto la duración del retraso de la lógica de procesamiento como el ritmo al que incrementa la duración aumentan con la gravedad de la condición de limitación.  
  
-   El número de mensajes que puede contener la cola en memoria está limitado. La cola en memoria sirve como marcador de posición temporal para entregar mensajes del cuadro de mensajes al agente de mensaje que a su vez entrega mensajes a adaptadores de XLANG y de envío. De forma predeterminada, la cola en memoria está establecida para que contenga 100 mensajes por CPU. Cuando la cola está llena, no se elimina ningún mensaje más de la cola de cuadro de mensajes hasta que la cola en memoria se libere.  
  
-   E tamaño del grupo de subprocesos de Agente de mensaje es limitado. Al limitar el tamaño de grupo de subprocesos de Agente de mensaje, el mecanismo de limitación de host reduce de forma eficaz la cantidad de mensajes que se entrega a XLANG y a adaptadores.  
  
     El tamaño de grupo de subprocesos de agente de mensaje predeterminado se puede modificar cambiando la **subprocesos máximos del motor** valor en el **General** ficha **panel de configuración**. Para obtener más información acerca de cómo modificar este valor, consulte [cómo modificar la configuración General](../core/how-to-modify-general-settings.md).  
  
-   El uso de memoria y otros recursos se reduce según proceda. BizTalk Server puede enviar instrucciones a otras clases de servicio para limitar el uso de memoria mediante la deshidratación de programaciones de ejecuciones, la reducción del tamaño de la memoria caché y la limitación del uso de los subprocesos que requieran una gran cantidad de memoria.  
  
 **Flujo de mensajes salientes desde el cuadro de mensajes a adaptadores y XLANG**  
  
 ![Flujo de mensajes de salida a adaptadores y XLANG](../core/media/outboundmsgflow.gif "OutboundMsgFlow")  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server incorpora la limitación de Host](../core/how-biztalk-server-implements-host-throttling.md)   
 [Mediante el panel de configuración de BizTalk Server ajuste del rendimiento](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)