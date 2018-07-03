---
title: Supervisión de aplicaciones | Microsoft Docs
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
ms.openlocfilehash: 0d1a7e4e0d4cb0f4e6899159da6c6c06a83e9165
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010301"
---
# <a name="monitoring-applications"></a>Supervisión de aplicaciones
Configuración de Microsoft System Center Operations Manager para supervisar BizTalk aplicaciones normalmente pueden dividirse en un proceso de cuatro pasos progresivo como sigue:  
  
1. **Modificar las reglas existentes o copiar reglas a un módulo de administración personalizado para supervisar una aplicación personalizada de BizTalk**  
  
    Deberá copiar muchas de estas reglas varias veces. Esto sucede si se está supervisando un número de recursos compartidos de archivos, por ejemplo. En este escenario, se copiaría la regla base una vez para cada recurso compartido de archivos con la dirección del recurso compartido de archivo agregada en el campo de descripción en el **criterios** pestaña de la regla. Al agregar la dirección, Operations Manager generará una alerta para cada recurso compartido de archivos individuales. Al copiar una regla existente, asegúrese de seleccionar **habilitar** deshabilitar regla invalidaciones para esta regla o recibirá alertas duplicadas.  
  
    Otro elemento que se debe agregar a cada regla que se crea es información de conocimientos en el **conocimiento** pestaña de la propiedad de regla. Estos datos se adjunta a la notificación de que se desencadena cuando se envía una alerta de Operations Manager. La eficacia de esta característica queda clara cuando se incluyen los pasos que pueden ayudar a resolver el error.  
  
2. **Creación de acciones para cada regla definida**  
  
    Crear o copiar una regla es realmente el primer paso en el proceso. El siguiente paso es realizar alguna acción en función de esa regla. Si no hay ninguna acción en función de una regla no importa que nunca se supervisa el evento. La acción realizada con más frecuencia es un operador o un administrador que se ha producido un error de la alerta. Operations Manager también proporciona un número de otras acciones que se puede usar cuando se desencadena un evento. Estas acciones incluyen:  
  
   -   A partir de una secuencia de comandos  
  
   -   Enviar una captura de Protocolo Simple de administración de redes (SNMP) (en SNMP, los agentes supervisan la actividad en los distintos dispositivos en la red y los informes a la estación de trabajo de la consola de red)  
  
   -   Enviar una notificación a un grupo de notificación  
  
   -   Ejecutar un comando o archivo por lotes  
  
   -   Actualizar una variable de estado  
  
   -   Transferir un archivo  
  
   -   Llamar a un método en un ensamblado de código administrado  
  
3. **Crear procesos iterativos para automatizar las tareas manuales**  
  
    El paso siguiente es un proceso iterativo y sobrepasa el mecanismo básico de alertas. Con Operations Manager podrá invocar el script y código. NET, el proceso de automatizar las tareas manuales en función de los eventos producidos es una característica de guardar eficaz y tiempo. Un ejemplo de esto es ejecutar una secuencia de comandos para iniciar automáticamente un puerto, si se registra un mensaje de evento deshabilitado o detenido. Este proceso es iterativo, ya que se pueden automatizar muchos procesos.  
  
4. **Usar reglas de umbral para automatizar las tareas manuales**  
  
    El siguiente paso de procesamiento es ir más allá de las alertas reactivo y usar reglas de umbral. El módulo de administración de BizTalk Server no contiene ninguna regla de umbral de forma predeterminada. Esto es porque estas reglas normalmente son específicas para la aplicación personalizada y son diferentes para cada aplicación. Un umbral personifica una regla de negocios con respecto a la aplicación personalizada y proporciona un medio de un sistema de supervisión proactivo. Puede usar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporcionadas con la herramienta de análisis de rendimiento de los registros (PAL) para definir las reglas de plantillas de umbral.  
  
    Un ejemplo de este tipo de regla de umbral es medir cuando las CPU en un servidor ejecutan de forma coherente por encima del 75 por ciento durante un período de tiempo específico. Esto podría indicar que necesita escalar horizontalmente el sistema. Aún otro ejemplo es donde crea una regla de umbral que supervisa un único conjunto de contadores. Esta regla, a continuación, podría invocar el código para inicializar instancias de host de BizTalk en un servidor de copia de seguridad configurado previamente durante los períodos de gran demanda.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de BizTalk Server con System Center Operations Manager 2007](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)