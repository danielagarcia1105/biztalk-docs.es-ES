---
title: Cómo modificar la configuración General | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostGeneral
ms.assetid: f0c90b44-e713-4d27-b125-833a747ab758
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a07a49d4905b13c33f87dcc694ca69c1a044fd2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255988"
---
# <a name="how-to-modify-general-settings"></a>Modificación de la configuración general
Mediante el panel de configuración, se pueden modificar los valores de la configuración general de un host determinado de un grupo de BizTalk. En este tema se proporcionan instrucciones paso a paso para realizar esta operación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-modify-the-general-settings-of-a-host"></a>Procedimiento para modificar la configuración general de un host  
  
1.  En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  
  
2.  En el **panel de configuración de BizTalk** cuadro de diálogo, en la **Hosts** página, haga clic en el **General** ficha.  
  
3.  Realice lo siguiente y, a continuación, haga clic en **aplicar** para aplicar las modificaciones y continuar en otra ficha. O haga clic en **Aceptar** para aplicar las modificaciones y salir del panel de configuración.  
  
    |Use|Para|Valores límite|Valor predeterminado|Actualizar lógica|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |Host|En la lista desplegable, seleccione el host que representa las instancias en tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|-|-||  
    |**Mover los datos de seguimiento a DTA DB**|Indicar si el host carga el componente de seguimiento de BizTalk para procesar la supervisión de estado y datos empresariales.<br /><br /> Si la activa, el host actual tendrá acceso de lectura y escritura a las tablas de seguimiento en la base de datos de cuadro de mensajes, así como en la base de datos de seguimiento. Por tanto, los objetos que se ejecuten en este host tendrán también acceso de lectura y escritura a estas bases de datos.<br /><br /> Si no activa esta casilla, el host actual solo tendrá privilegios de escritura para las tablas de seguimiento en la base de datos de cuadro de mensajes y no tendrá acceso a la base de datos de seguimiento.|Activar, Desactivar|Activado||  
    |**Autenticación de confianza**|Indica si se puede confiar en un host de BizTalk para recopilar información de autenticación.<br /><br /> Mediante la especificación de los hosts son de confianza y cuáles no, puede definir los límites de seguridad en qué usuario objetos y el código pueden ser de confianza o no de confianza.|Activar, Desactivar|Desactivado||  
    |**Sólo de 32 bits**|Indica si se debe crear el proceso de instancia de host como 32 bits en ambos servidores de 32 y 64 bits.|Activar, Desactivar|Activado||  
    |**Dominio de aplicación predeterminado para adaptador aislado**|Indica si el adaptador aislado se ejecuta en el dominio de aplicación predeterminado o en el dominio del usuario que llama.<br /><br /> De forma predeterminada, todos los objetos del motor de mensajería se crean en el dominio del usuario que llama. Si por alguna razón el servicio Web está inactivo durante un período de tiempo prolongado, IIS descarga el dominio del usuario que llama. Cuando esto ocurre, todos los servicios del proceso de alojamiento dejan de poder usarse.<br /><br /> Si se selecciona el dominio de aplicación predeterminado, los objetos del motor de mensajería de BizTalk se crean en el dominio de aplicación predeterminado, en lugar de los dominios de aplicación propios. Y nunca se descarga el dominio de aplicación predeterminado.<br /><br /> Esta opción solo está disponible si se ha creado alguna de las instancias de host en el dominio de aplicación predeterminado.|Activar, Desactivar|Desactivado|TRUE si cualquiera de las instancias de host para el host se establecen así. FALSE en caso contrario.|  
    |**Comportamiento heredado de espacio en blanco**|Especifique si desea conservar los espacios en blanco al crear asignaciones.|Activar, Desactivar|Desactivado|Para cada instancia de host en un equipo, el valor es TRUE si la máquina tiene el valor del registro > 0. Para cada host, el valor es TRUE si cualquiera de la instancia de host tiene establecido como TRUE.|  
    |**Permitir varias respuestas**|Indique si desea habilitar múltiples respuestas para que se devuelvan a una ubicación de recepción bidireccional.|Activar, Desactivar|Desactivado|Si es TRUE para cualquier instancia de host de un host, establezca la configuración de host = TRUE. De lo contrario, FALSE.|  
    |**Tiempo de espera de respuesta**|Especifique el tiempo de espera predeterminado para los mensajes de solicitud-respuesta.|1 – Valor máximo de tipo entero|20|Hosts en proceso: valor más alto para una instancia de host<br /><br /> Hosts aislados: valor más alto en un equipo|  
    |**Subprocesos máximos del motor**|Indique el número máximo de subprocesos del motor de mensajería por CPU.<br /><br /> Esta opción especifica el número máximo de subprocesos que puede utilizar el Gestor extremo (EPM). El EPM empieza por el número de subprocesos equivalentes al 10 % de este valor y agrega subprocesos hasta el valor especificado cuando aumenta la carga. El número de subprocesos asignados se reduce al disminuir la carga o según sea necesario para la limitación.<br /><br /> **Tenga en cuenta** si modifica este valor, el host debe reiniciarse para que el cambio surta efecto.|[1,50]|20|-|  
    |**Mostrar contadores de rendimiento para**|Seleccione el servicio para el que desea mostrar los contadores de rendimiento.<br /><br /> Si se define como Mensajería, el Monitor de rendimiento mostrará los contadores del Agente de mensaje para la Mensajería. Si el host contiene orquestaciones, no se mostrarán resultados del Agente de mensaje para las instancias de orquestación (XLANG).<br /><br /> Si el host solo contiene orquestaciones, cambie la **Mostrar contadores de rendimiento para** si se establece en orquestaciones para mostrar los contadores del agente de mensajes para las instancias de orquestación. Si el host solo contiene puertos de recepción y envío, deje activada la opción Mensajería para mostrar los contadores del Agente de mensaje para instancias de Mensajería.|Mensajería, orquestaciones|Mensajería|Si todas las instancias de host de un host tienen el mismo valor, elija el valor para el host. Si hay un conflicto o ningún valor establecido, elija la opción predeterminada.|  
  
     **Intervalos de sondeo**  
  
    |Use|Para|Valores límite|Valor predeterminado|Actualizar lógica|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**Mensajería**|Establezca el intervalo de sondeo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en milisegundos cuando la instancia de host de BizTalk busque nuevos mensajes en el cuadro de mensaje.|1 – Valor máximo de tipo entero|500|Valor existente|  
    |**Orquestaciones**|Establezca el intervalo de sondeo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en milisegundos cuando la instancia de host de BizTalk busque nuevas orquestaciones en la base de datos.|1 – Valor máximo de tipo entero|500|Valor existente|  
  
    > [!NOTE]
    >  Para restaurar la configuración predeterminada, haga clic en **Restaurar valores predeterminados**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo modificar la configuración de Host](../core/how-to-modify-host-settings.md)