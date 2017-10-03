---
title: "Cómo configurar las opciones avanzadas para un puerto de envío de transporte | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, transport options [send ports]
- configuring, send ports
- send ports, transport options
- managing [send ports], configuring
- managing [send ports], transport options
ms.assetid: b0033e09-3c18-4e53-a470-e12978e61ba1
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 320ed6c1caf288ac1bf9745a351bbd53a46f48db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-transport-advanced-options-for-a-send-port"></a>Cómo configurar opciones avanzadas de transporte para un puerto de envío
Usar la consola de administración de BizTalk Server para configurar las opciones avanzadas para un puerto de envío de transporte. Estas opciones determinan la forma en la que el puerto de envío controla los mensajes, como, por ejemplo, el número de reintentos de envío de un mensaje si éste tiene algún error, así como la programación de la ventana de servicio para el puerto.  
  
> [!NOTE]
> **A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** , puede habilitar la entrega ordenada de puertos de envío dinámicos, según el tipo de adaptador. Esta opción solo está disponible para los tipos de adaptador que se garantiza la entrega ordenada de puertos de envío estáticos, por ejemplo, el adaptador de archivo y el adaptador de FTP.
> 
> Considere la posibilidad de seis mensajes: M1, M2, M3, M4, M5 y M6. M1, M3, M5 están diseñados para una ubicación de archivo. M2, M4 y M6 están diseñados para FTP. El puerto de envío dinámico de entrega ordenada se asegura de que se ordenan M1, M3 y M5; y M2, M4 y M6 ordenan respectivamente. 
> 
> Para los tipos de adaptador que no son compatibles con la entrega ordenada, no hay cualquier disponibles para configurar propiedades de puerto de envío dinámico. Las opciones de transporte se determinan automáticamente en tiempo de ejecución.  
>
> **Para versiones anteriores de BizTalk** que usan puertos dinámicos, no hay ninguna propiedad disponibles para configurar debido a las opciones de transporte se determinan automáticamente en tiempo de ejecución.

  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="controlling-send-port-priority"></a>Controlar la prioridad de puertos de envío  
 El parámetro de configuración Prioridad de Opciones avanzadas de transporte controla el orden de eliminación de los mensajes del cuadro de mensajes. Los puertos de mayor prioridad se procesarán antes que los puertos con una prioridad menor; esto significa que los puertos de más prioridad adquieren una importancia mayor con respecto a otros puertos de envío correspondientes a un host único.  
  
 La prioridad resulta de utilidad en escenarios en los que, para ciertos tipos de solicitud, se requieren bajos tiempos de respuesta. Por ejemplo, en el caso de que haya varios puertos de envío que se conecten a distintos sistemas para efectuar el procesamiento de solicitudes normales e interactivas. Las solicitudes interactivas requieren un tiempo de respuesta bajo, de modo que, al enviar una de estas solicitudes, querrá asegurarse de que se procesa lo antes posible.  
  
 El objetivo de BizTalk Server no es aplicar un criterio justo al procesar los mensajes con distintas prioridades en el cuadro de mensajes. Si hay un mismo número de elementos con dos prioridades distintas en el cuadro de mensajes cuando comienza el procesamiento, los elementos de menor prioridad solo se procesarán una vez concluido el procesamiento de los de prioridad alta. Si el volumen de elementos de prioridad alta es muy alto, puede que los de prioridad baja no lleguen a procesarse nunca. Dicho de otro modo: los elementos de menor prioridad experimentarán privación.  
  
> [!WARNING]
>  Para minimizar el riesgo de privación de mensajes, someta la aplicación a pruebas minuciosas y a cargas realistas para asegurarse de que todos los mensajes se procesan. Si no somete la solución a estas pruebas de un modo adecuado, es posible que queden mensajes sin procesar.  
  
 BizTalk Server efectúa una asignación interna de prioridades a todas las suscripciones. La prioridad puede adoptar cualquier número comprendido entre el 1 (prioridad máxima) y el 10 (prioridad mínima). Dado que la prioridad predeterminada es 7 para la activación de suscripciones y 5 para la correlación de éstas, la correlación de mensajes se efectuará antes que la activación de suscripciones.  
  
## <a name="configure-the-transport-options"></a>Configurar las opciones de transporte 
  
1.  Abra **administración de BizTalk Server**.  
  
2.  Expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk.  
  
3.  Seleccione **puertos de envío**, haga clic en el puerto de envío para configurar y, a continuación, seleccione **propiedades**.  
  
4.  En el panel izquierdo, seleccione **opciones avanzadas de transporte**.  
  
5.  Configure las opciones de transporte como se describe en la tabla siguiente y, a continuación, seleccione **Aceptar**.  Solo algunas de las propiedades siguientes están disponibles para puertos de envío dinámicos.
  
    |Use|Para|  
    |--------------|----------------|  
    |**Número de reintentos**|Especificar el número de veces que el puerto de envío intenta reenviar un mensaje en caso de error. El valor predeterminado es 3. el intervalo permitido es de 0 a 1.000.|  
    |**Intervalo de reintento**|Especificar el intervalo de tiempo (en minutos) que media entre los intentos de reenvío de un mensaje. El valor predeterminado es 5; el intervalo permitido es de 0 a 525.600, ambos inclusive.|  
    |**Prioridad**|Establecer la prioridad del intento de reenvío.|  
    |**Entrega ordenada**|Seleccionar esta casilla para enviar mensajes según su orden de recepción.|  
    |**Dejar de enviar los mensajes subsiguientes en caso de error de mensaje actual**|Seleccionar esta casilla para detener el envío de mensajes sucesivos que siguen a un mensaje con errores. Esta opción solo está disponible cuando la **entrega ordenada** opción está seleccionada.|  
    |**Habilitar enrutamiento para mensajes con errores**|Seleccionar esta opción para habilitar el enrutamiento de mensajes con errores.|  
    |**Habilitar ventana de servicio**|Seleccionar esta opción para especificar el período diario durante el que el puerto de envío se encontrará en funcionamiento mediante la especificación de una hora de inicio y una hora de detención.|  
    |**Hora de inicio**|Especificar la hora a la que el puerto de envío comienza a enviar mensajes todos los días. Esta opción solo está disponible cuando la **habilitar ventana de servicio** opción está seleccionada.|  
    |**Hora de finalización**|Especificar la hora a la que el puerto de envío deja de enviar mensajes todos los días. Esta opción solo está disponible cuando la **habilitar ventana de servicio** opción está seleccionada.|  
  
## <a name="see-also"></a>Vea también  
[Entrega ordenada de mensajes](../core/ordered-delivery-of-messages.md)  
 [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)