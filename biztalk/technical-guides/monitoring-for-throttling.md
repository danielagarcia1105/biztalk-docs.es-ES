---
title: Supervisión de limitación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d1d4c72-6942-4572-b27f-c58d37c94062
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d60b9f3deb77df927eb055b4504b809b421ae663
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299764"
---
# <a name="monitoring-for-throttling"></a>Supervisión de limitación
El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración supervisa los contadores de rendimiento que indican el estado de limitación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. A continuación se enumeran algunos factores claves para comprender acerca de la limitación.  
  
-   Limitación según la velocidad es por host y se basa en la tasa de mensajes entrantes frente a mensajes salientes.  
  
-   Para la limitación de entrega (**MsgBox -> puerto de envío u orquestación**), velocidad de entrada es la velocidad a la que se reciben mensajes desde el cuadro de mensaje. Velocidad de salida es la velocidad a la que los mensajes se entregan correctamente a través de los adaptadores.  
  
-   Para la limitación de publicación (**adaptadores de recepción** o **orquestaciones -> MsgBox),** velocidad entrante es la velocidad a la que se reciben mensajes de los adaptadores y velocidad de salida es la frecuencia de los mensajes es conectar en el cuadro de mensajes.  
  
-   No existe ningún mecanismo de limitación entre hosts que no sean de total de mensajes en la base de datos.  
  
 Para obtener información adicional, consulte el tema [cómo BizTalk Server implementa la limitación de Host](http://go.microsoft.com/fwlink/?LinkID=155286) (http://go.microsoft.com/fwlink/?LinkID=155286) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]incorpora autolimitación que contribuye a evitar la sobrecarga del servidor en función de varios parámetros. Una sobrecarga temporal que da lugar a una limitación no es un evento significativo operativamente hablando. Por el contrario, una limitación persistente constituye un evento inesperado en un entorno estable que podría indicar la existencia de problemas subyacentes en el nivel de la infraestructura. El módulo de administración de proporciona una supervisión proactiva de las condiciones en las que se producen las limitaciones persistentes con reglas de umbral de rendimiento.  
  
 Cuatro seguimiento de uso y rendimiento reglas supervisan para largos períodos de limitación provocados por cuatro condiciones distintas, como se indica en la tabla siguiente.  
  
|Condición|Regla|  
|---------------|----------|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]memoria de proceso de servicio|Advertencia: BizTalk Throttled en memoria de proceso alta durante un período significativo|  
|Número de mensajes procesados|Advertencia: BizTalk Throttled en alta Inprocess recuento de mensajes durante un período significativo|  
|Número de subprocesos en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proceso|Advertencia: BizTalk Throttled en gran número de subprocesos durante un período significativo|  
|Tamaño de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las colas de la base de datos|Advertencia: BizTalk Throttled on High Database Size durante un período significativo|  
  
 Estas reglas de umbral usan proveedores de datos en función de los contadores de rendimiento de indicador de estado de limitación. Para obtener más información acerca de estos contadores de rendimiento, consulte la sección [contadores de rendimiento](http://go.microsoft.com/fwlink/?LinkId=157269) (http://go.microsoft.com/fwlink/?LinkId=157269) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 Estas reglas están configuradas para activar una alerta si el promedio de un número determinado de muestras supera un umbral determinado (el valor predeterminado es 30). Por ejemplo, "Advertencia: BizTalk Throttled on High Database Size durante un período significativo" es una regla que supervisa el estado de limitación de todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesos en un equipo determinado. Esta regla usa un proveedor de datos basado en la limitación estado indicador rendimiento contador "agente de mensaje-tamaño excesivo tamaño base de datos." Si el valor de este contador de rendimiento es 1, el proceso asociado se encuentra limitado a causa del excesivo tamaño de la base de datos.  
  
 La regla anterior está configurada para tomar un promedio de 30 muestras y genere una alerta si el promedio de los ejemplos es superior a 0,6. Puesto que cada ejemplo se toma a intervalos de un minuto, esto implica que en los últimos 30 minutos, por lo menos uno o varios procesos de BizTalk Server en ese equipo estaban sujeto a limitación debido a un tamaño de base de datos alta, 60 por ciento del tiempo.  
  
 Puede que esta heurística no se ajuste a su escenario de aplicaciones particular. En función del comportamiento histórico en su entorno tal como se describe antes, debe configurar estas reglas con los valores correctos, ya sea:  
  
-   Ajuste de los ejemplos.  
  
-   Ajustar el valor de umbral.  
  
-   Si es necesario, modificar el intervalo de muestreo para el proveedor.