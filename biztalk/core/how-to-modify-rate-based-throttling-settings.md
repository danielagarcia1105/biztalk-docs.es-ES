---
title: Tasa basada en valores de límite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostRate
ms.assetid: a99dfb29-dee6-4a43-8d34-45179d9d0b5e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be54bd3d986143b3f267655bbcb003967e50238f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255892"
---
# <a name="how-to-modify-rate-based-throttling-settings"></a>Modificación de la configuración de limitación según la velocidad
La limitación según la velocidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se aplica a instancias de host que contienen orquestaciones o adaptadores de envío que reciben y entregan o procesan mensajes que se han publicado en el cuadro de mensajes. Mediante el uso de [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], puede modificar las opciones de configuración de la limitación según la velocidad de un host determinado, en un grupo de BizTalk. Estas opciones se aplican a todas las instancias de host asignadas al host dado. En este tema se proporciona el procedimiento paso a paso para modificar esta configuración.  
  
 La condición de limitación según la velocidad se puede desencadenar bajo las condiciones siguientes:  
  
-   La cantidad de memoria, el número de subprocesos o el número de conexiones de base de datos usadas por la instancia de host excede de los umbrales de limitación.  
  
-   La velocidad de entrada de entrega de mensajes para la instancia de host excede de la velocidad de salida de entrega de mensajes * el valor (porcentaje) del factor de sobrecarga de velocidad especificado.  
  
-   El número de mensajes que la instancia de host procesa simultáneamente excede de los mensajes en curso por CPU * el número de CPU disponibles en el equipo  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-modify-the-rate-based-throttling-settings-of-a-host"></a>Procedimiento para modificar las opciones de la limitación según la velocidad para un host  
  
1.  En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  
  
2.  En el **panel de configuración de BizTalk** cuadro de diálogo la **Hosts** , haga clic en el **limitación según la velocidad** ficha.  
  
3.  Haga lo siguiente y haga clic en **aplicar** para aplicar las modificaciones y continuar en otra ficha. En caso contrario, haga clic en **Aceptar** para aplicar las modificaciones y salir del panel de configuración.  
  
    |Use|Para|Valores límite|Valor predeterminado|Actualizar lógica|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**Host**|En la lista desplegable, seleccione el host que representa las instancias en tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|-|-|-|  
  
     **Publicar**  
  
    |Use|Para|Valores límite|Valor predeterminado|Actualizar lógica|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**Número mínimo de muestras**|Especifique el número mínimo de mensajes [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realizará una muestra para la **duración de la ventana de muestreo** antes de considerar la limitación basada en tasas.<br /><br /> Si el número real de muestras en una ventana de muestreo descender por debajo de este valor, se descartan las muestras y no se aplica la limitación. Este valor debería ser coherente con una tasa con la que se pueden publicar mensajes con una carga media. Por ejemplo, si se espera que su sistema controle 1.000 documentos por segundo con una carga Media, a continuación, este parámetro debe establecerse en 1.000 \* ventana duración muestras en segundos (o más exactamente 1 \* **ventana de muestreo duración** (segundos)). Si el valor se establece demasiado bajo, el sistema puede experimentar una condición de limitación en condiciones de baja carga. Si el valor se configura demasiado alto, puede que no haya suficientes muestras para que esta técnica sea efectiva.|1 – Valor máximo de tipo entero|100|-|  
    |**Duración de la ventana de muestreo**|Especifique la ventana de tiempo (medida en segundos) que se usa para calcular la tasa de publicación a partir de las muestras recopiladas. La duración debe aumentarse si la latencia necesaria para publicar un mensaje único es alta.|1 – Valor máximo de tipo entero|15000|-|  
    |**Factor de sobrecarga**|Especifique el porcentaje para controlar cuánto permite que sea mayor la tasa de solicitud que la tasa de finalización antes de que se produzca una condición de limitación.<br /><br /> Por ejemplo, si se publican los mensajes a una tasa de 200 por segundo y este parámetro se establece en 125, el sistema permite la publicación de hasta 250 mensajes por segundo (125% * 200 = 250) antes de aplicar la limitación. Si especifica un valor demasiado pequeño para este parámetro, es posible que el sistema limite de una forma más agresiva y se pueda provocar una sobrelimitación. Si especifica un valor demasiado grande para este parámetro, es posible que cause una infralimitación e impida al mecanismo de limitación que reconozca una condición legítima de limitación.|1 – Valor máximo de tipo entero|125|-|  
    |**Retraso máximo de limitación**|Especifique el retraso máximo (en milisegundos) que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] impone a una instancia de mensaje debido a la limitación. El retraso real depende de la gravedad de la condición de limitación.|1 – Valor máximo de tipo entero|300000|-|  
    |**Reemplazo de limitación**|Especifique si desea reemplazar la limitación de publicación de mensajes.|0: no invalidar<br /><br /> 1: iniciar condición de limitación<br /><br /> 2: no limitar|0|Los parámetros de limitación leídos del registro deben asignarse uno a uno a parámetros de instancia de host.|  
    |**Gravedad del reemplazo de limitación**|Especifique la gravedad de una condición de limitación de entrada.<br /><br /> Un valor mayor aumenta la gravedad de una condición de limitación de entrada iniciada cuando **reemplazo de limitación** está establecido en 1.|1 – 1000|100|El menor de todos los valores de instancia de host.|  
  
     **Entrega**  
  
    |Use|Para|Valores límite|Valor predeterminado|Actualizar lógica|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**Número mínimo de muestras**|Especifique el número mínimo de mensajes de BizTalk realizará una muestra para la **duración de la ventana de muestreo** antes de considerar la limitación basada en tasas.<br /><br /> Si el número real de muestras en una ventana de muestreo cae por debajo de este valor, se descartan las muestras y no se aplica la limitación. Este valor debería ser coherente con una tasa con la que se pueden entregar mensajes con una carga media. Por ejemplo, si se espera que su sistema controle 1.000 documentos por segundo con una carga Media, a continuación, este parámetro debe establecerse en 1.000 \* ventana duración muestras en segundos (o más exactamente 1 \* **duración de la ventana de ejemplo**  (segundos) para este escenario).<br /><br /> Si el valor se establece demasiado bajo, el sistema puede experimentar una condición de limitación en condiciones de baja carga. Si el valor se configura demasiado alto, puede que no haya suficientes muestras para que esta técnica sea efectiva.|1 – Valor máximo de tipo entero|100|-|  
    |**Duración de la ventana de muestreo**|Especifique la ventana de tiempo (en segundos) que se usa para calcular la tasa de procesamiento a partir de las muestras recopiladas. La duración debe aumentarse si la latencia necesaria para procesar un mensaje único es alta.|1 – Valor máximo de tipo entero|15000|-|  
    |**Factor de sobrecarga**|Especifique el porcentaje para controlar cuánto permite que sea mayor la tasa de entrega al motor de orquestaciones o de mensajería que la tasa de finalización antes de que se produzca una condición de limitación.<br /><br /> Por ejemplo, si los mensajes se procesan a una tasa de 200 por segundo y este parámetro se establece en 125, el sistema permite el procesamiento de hasta 250 mensajes por segundo (125% * 200 = 250) antes de aplicar la limitación. Especificar un valor demasiado pequeño para este parámetro hace que el sistema limite de una forma más agresiva y podría provocar una sobrelimitación. Si especifica un valor demasiado grande para este parámetro causará una infralimitación e impedirá al mecanismo de limitación que reconozca una condición legítima de limitación.|1 – Valor máximo de tipo entero|125|-|  
    |**Retraso máximo de limitación**|Especifique el retraso máximo que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] impone a una instancia de mensaje debido a la limitación. El retraso real depende de la gravedad de la condición de limitación.|1 – Valor máximo de tipo entero|300000|-|  
    |**Reemplazo de limitación**|Especifique si desea reemplazar la limitación de entrega de mensajes.|0: no invalidar<br /><br /> 1: iniciar condición de limitación<br /><br /> 2: no limitar|0|Los parámetros de limitación leídos del registro deben asignarse uno a uno a parámetros de instancia de host.|  
    |**Gravedad del reemplazo de limitación**|Especifique la gravedad de la condición de limitación de salida.<br /><br /> Un valor mayor aumenta la gravedad de una condición de limitación de salida iniciada cuando **reemplazo de limitación** está establecido en 1.|1 – 1000|100|El menor de todos los valores de instancia de host.|  
  
    > [!NOTE]
    >  Para restaurar la configuración predeterminada, haga clic en **Restaurar valores predeterminados**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo modificar la configuración de Host](../core/how-to-modify-host-settings.md)