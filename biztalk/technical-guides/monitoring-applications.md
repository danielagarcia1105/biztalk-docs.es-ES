---
title: Supervisión de aplicaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4be98ba2-6acd-4dee-b6ea-db71bbd368f0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67c937ae0edb1698991ad111622a582ebfc64d76
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008997"
---
# <a name="monitoring-applications"></a>Supervisión de aplicaciones
Configuración de Microsoft System Center Operations Manager para supervisar BizTalk aplicaciones normalmente pueden dividirse en un proceso de cuatro pasos progresivo como sigue:  
  
1.  **Modifique las reglas existentes o copiar reglas en un módulo de administración personalizado para supervisar una aplicación personalizada de BizTalk**  
  
     Debe copiar muchas de estas reglas varias veces. Esto sucede si se supervisa un número de recursos compartidos de archivos, por ejemplo. En este escenario, se copiaría la regla base una vez para cada recurso compartido de archivos con la dirección del recurso compartido de archivo agregada en el campo de descripción en el **criterios** pestaña de la regla. Al agregar la dirección, Operations Manager generará una alerta para cada recurso compartido de archivos individuales. Cuando copia una regla existente, asegúrese de seleccionar **habilitar** deshabilitar regla invalidaciones para esta regla o va a recibir las alertas duplicadas.  
  
     Otro elemento que se debe agregar a cada regla que se crea es información de conocimientos en el **Base de conocimiento** pestaña de la propiedad de regla. Estos datos se adjuntarán a la notificación de que se produce cuando se envía una alerta de Operations Manager. La eficacia de esta característica está justificada si se incluyen los pasos que pueden ayudar a resolver el error.  
  
2.  **Crear acciones para cada regla definida**  
  
     Crear o copiar una regla es en realidad el primer paso en el proceso. El siguiente paso es realizar alguna acción en función de esa regla. Si no hay ninguna acción había basado en una regla, a continuación, realmente no es importante que nunca se supervisa el evento. La acción realizada con más frecuencia es un operador o un administrador que se ha producido un error de la alerta. Operations Manager también proporciona un número de otras acciones que se puede usar cuando se desencadena un evento. Estas acciones incluyen:  
  
    -   A partir de una secuencia de comandos  
  
    -   Enviar una captura de Protocolo Simple de administración de redes (SNMP) (en SNMP, los agentes supervisan la actividad en los diversos dispositivos de la red y los informes a la estación de trabajo de la consola de red)  
  
    -   Enviar una notificación a un grupo de notificación  
  
    -   Ejecutar un comando o archivo por lotes  
  
    -   Actualizar una variable de estado  
  
    -   Transferir un archivo  
  
    -   Llamar a un método en un ensamblado de código administrado  
  
3.  **Crear procesos iterativos para automatizar las tareas manuales**  
  
     El paso siguiente es un proceso iterativo y sobrepasa el mecanismo básico de alertas. Con Operations Manager podrá invocar el script y código de .NET, el proceso de automatizar las tareas manuales en función de eventos que se produzcan es una característica de guardar eficaz y el tiempo. Un ejemplo de esto es ejecutar un script para iniciar automáticamente un puerto si se registra un mensaje de evento detenido o deshabilitado. Este proceso es iterativo, ya que se pueden automatizar muchos procesos.  
  
4.  **Usar reglas de umbral para automatizar las tareas manuales**  
  
     El siguiente paso en el procesamiento es algo más que el sistema de alertas reactivos y usar reglas de umbral. El módulo de administración de BizTalk Server no contiene ninguna regla de umbral de forma predeterminada. Esto es porque estas reglas se suele ser específicas de la aplicación personalizada y son diferentes para cada aplicación. Un umbral personifica una regla de negocios con respecto a la aplicación personalizada y proporciona un medio de un sistema de supervisión proactivo. Puede usar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] plantillas de umbral que se proporciona con la herramienta de análisis de rendimiento de registros (PAL) para definir las reglas.  
  
     Un ejemplo de dicha regla de umbral es medir cuando las CPU en un servidor ejecutan constantemente por encima del 75 por ciento durante un período de tiempo específico. Esto podría indicar que necesite escalar el sistema. Aún otro ejemplo es que cree una regla de umbral que supervisa un único conjunto de contadores. Esta regla, a continuación, podría invocar el código para inicializar las instancias de host de BizTalk en un servidor de copia de seguridad configurada previamente durante los períodos de gran demanda.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de BizTalk Server con System Center Operations Manager 2007](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)