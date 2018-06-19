---
title: Cómo modificar la configuración de limitación de orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostOrchestration
ms.assetid: 30086994-cb55-4ff7-9940-df197e5e35ce
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f868c0b6d686871211410e8861acbdec118ac302
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254628"
---
# <a name="how-to-modify-orchestration-throttling-settings"></a>Modificación de la configuración de limitación de la orquestación
Mediante el uso del Panel de configuración de BizTalk, puede modificar la configuración de limitación de orquestación de un host dado en todo el Grupo de BizTalk. Estas opciones se aplican a todas las instancias de host asignadas al host dado. En este tema se proporciona el procedimiento paso a paso para modificar esta configuración.  
  
 La orquestación de limitación, especificado en el **btsntsvc.exe.config** de archivos, evitará que una orquestación consuma demasiada memoria limitando el número de mensajes pendientes que puede tener. Todos los mensajes seguirán enviándose al cuadro de mensajes; Sin embargo, no se entregan los mensajes en cola a la orquestación hasta que ésta procese algunos de sus mensajes pendientes.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-modify-the-orchestrations-throttling-settings-of-a-host"></a>Procedimiento para modificar las configuración de limitación de orquestaciones de un host  
  
1.  En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  
  
2.  En el **panel de configuración de BizTalk** cuadro de diálogo la **Hosts** , haga clic en el **limitación de orquestaciones** ficha.  
  
3.  Realice lo siguiente y, a continuación, haga clic en **aplicar** para aplicar las modificaciones y continuar en otra ficha. O haga clic en **Aceptar** para aplicar las modificaciones y salir del panel de configuración.  
  
    |Use|Para|Valores límite|Valor predeterminado|Actualizar lógica|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**Host**|En la lista desplegable, seleccione el host que representa las instancias en tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|-|-|-|  
    |**Comportamiento de deshidratación**|Seleccione el comportamiento de deshidratación del motor de orquestaciones (XLANG). Tenga en cuenta que los demás valores de XLANG son editables solo si selecciona “Personalizado”.<br /><br /> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa estas propiedades de deshidratación para decidir cuándo deshidratar y rehidratar las orquestaciones. En condiciones de carga normal, los valores predeterminados de deshidratación son suficientes pero, si está trabajando con un nivel de carga alto y desea cambiar las características de rendimiento, deberá ajustar los valores. El comportamiento de deshidratación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] depende por completo de la cantidad de memoria disponible y de la cantidad de memoria en uso.|Always<br /><br /> Never<br /><br /> Personalizado|Personalizado|-|  
  
     **Basado en el tiempo**  
  
    |Use|Para|Valores límite|Valor predeterminado|Actualizar lógica|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**Umbral máximo**|Especifique el tiempo de espera máximo que puede estar bloqueada una instancia de orquestaciones antes de que se deshidrate.|(MinThreshold: valor máximo de tipo Entero]|1800 seg.|-|  
    |**Umbral mínimo**|Especifique el tiempo de inactividad mínimo que puede estar bloqueada una instancia de orquestación antes de su deshidratación.|[Valor de 1 – máximo de tipo entero)|1 segundo|-|  
    |**Suscripciones**|Seleccione esta opción para configurar manualmente los valores "pausa en" y "reanudar en" para una suscripción. De forma predeterminada, el sistema se encarga de las suscripciones en tiempo de ejecución.|Activar, Desactivar|Desactivado|-|  
    |**Pausar en**|Especifique el número máximo de mensajes que desea que almacene una suscripción.<br /><br /> Cuando una suscripción tiene un número de mensajes a la espera de ser consumidos mayor o igual al número especificado, los mensajes no se entregan a la instancia de suscripción. El número mínimo de mensajes sería el del valor "reanudar en".<br /><br /> Por ejemplo, si establece **pausar en** valor en 100, significa que una orquestación tiene 100 mensajes pendientes y MessageBox dejará de enviar más mensajes.|(ResumeAt: valor máximo de tipo Entero].<br /><br /> Excepto si ambos son 0.|Desactivado|-|  
    |**Reanudar en**|Especifique el número de mensajes que desea que el cuadro de mensajes reanude el envío de mensajes a la suscripción.<br /><br /> Por ejemplo, establecer el **reanudar en** valor a 50. Cuando el número de mensajes pendientes de la orquestación desciende a 50, especifica que el cuadro de mensajes puede reanudar el envío de mensajes.|[0: valor máximo de tipo Entero)|Desactivado|-|  
  
    > [!NOTE]
    >  Para restaurar la configuración predeterminada, haga clic en **Restaurar valores predeterminados**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo modificar la configuración de Host](../core/how-to-modify-host-settings.md)