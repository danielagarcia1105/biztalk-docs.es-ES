---
title: Actualizar configuración de grupo | Microsoft Docs
description: Cambiar la configuración de rendimiento del grupo mediante la administración de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe0cbeb8-23d6-45cf-8535-c989914f5124
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22bdc81d3db5a9b64d500d90c428339c0ebfc09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966677"
---
# <a name="how-to-update-the-biztalk-group-settings"></a>Cómo actualizar la configuración del grupo de BizTalk
Mediante el panel de configuración, se puede modificar la información de configuración que se usa en todos los equipos de un grupo de BizTalk determinado. En este tema se proporciona el procedimiento paso a paso para modificar la configuración de rendimiento a nivel de grupo en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esta configuración es aplicable a todos los equipos de un grupo determinado.  

> [!NOTE]
>  También puede modificar la configuración de host y de instancia de host. Para obtener más información, consulte [cómo modificar la configuración del Host](../core/how-to-modify-host-settings.md) y [cómo modificar la configuración de instancia de Host](../core/how-to-modify-host-instance-settings.md).  

 La configuración actual de BizTalk Server puede exportarse a un archivo XML. Posteriormente, puede importarse dicha configuración en el panel de configuraciones, en lugar de configurar nuevos valores. Para obtener información sobre la importación o exportación de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración, consulte [importación o exportación usando configuración de panel de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md) y [importación o exportación de configuración de BizTalk mediante BTSTask](how-to-import-biztalk-settings-using-btstask.md). 

## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe iniciado sesión como miembro del grupo Administradores de BizTalk Server.  

## <a name="update-the-group-level-settings"></a>Actualizar la configuración de nivel de grupo  

1. En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  

2. En el **panel de configuración de BizTalk** cuadro de diálogo el **grupo** página, realice lo siguiente:  


   |                       Use                        |                                                                                                                                                                                          Para                                                                                                                                                                                           |          Valores límite          | Valor predeterminado |                                                Actualizar lógica                                                |
   |-------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|---------------|-------------------------------------------------------------------------------------------------------------|
   |          **Intervalo de actualización de configuración**           |                                                                                                                        Establecer el intervalo en el que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] actualiza la configuración de mensajería.                                                                                                                        |             1 - 43200             |       -       |                                                      -                                                      |
   |              **Umbral de lote de mensajes**              |                                                                                                                                    Si el tamaño total del lote de mensajes entrantes excede este valor, el lote se divide en lotes más pequeños y se procesa.                                                                                                                                    |           1 - 10000000            |    102400     | Copia el valor de HKEY_LOCAL_MACHINE\Software\Microsoft\BizTalk Server\3.0\Administration\TransformThreshold |
   |                **Tamaño del mensaje grande**                 |                                                                                                                                       Configurar el tamaño del umbral de un mensaje individual que desencadena la transmisión por secuencias en un lote o durante las transformaciones.                                                                                                                                       |           1 - 10000000            |    1000000    |           Máximo de la existente **tamaño del mensaje grande** y **LargeMessageFragmentSize** valores.           |
   |              **Seguimiento e informes**               |                                                                                                                                                                                                                                                                                                                                                                                               |                 -                 |       -       |                                                      -                                                      |
   | **Intervalo de muestreo de contador de rendimiento de cuadro de mensaje** |                                                                       Establecer el intervalo de actualización de los contadores de rendimiento.<br /><br /> El intervalo equilibra la carga en la base de datos frente al grado de actualización de los contadores. Cuanto mayor es el valor, menor es la frecuencia de actualización de datos y, por lo tanto, menor es la carga en la base de datos.                                                                        | 1 – Valor máximo de tipo entero |       -       |               Valor más grande en cualquier equipo del grupo de BizTalk si existe. Si no es así, predeterminado.                |
   |            **Habilitar el seguimiento de nivel de grupo**            | Seleccione esta opción para activar el seguimiento a nivel de grupo para BizTalk Server.<br /><br /> Si se desactiva el seguimiento global, se deshabilitan los interceptores de seguimiento de todo el grupo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Es decir, BizTalk Server no realizará ningún seguimiento de los eventos en las tablas de seguimiento. **Nota:** esta configuración no afecta al seguimiento BAM. |              Activar, Desactivar              |      Activado       |                                                      -                                                      |


3. Haga clic en **aplicar** para aplicar las modificaciones y continuar en otra pestaña. O haga clic en **Aceptar** para aplicar las modificaciones y salir del panel de configuración.  

   > [!NOTE]
   >  Para restaurar la configuración predeterminada, haga clic en **Restaurar valores predeterminados**.  

## <a name="see-also"></a>Vea también  
 [Uso del panel de configuración para ajustar el rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)