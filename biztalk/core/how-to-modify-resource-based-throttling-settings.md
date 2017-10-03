---
title: "Modificar recurso basada en valores de límite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Bts10.settings.HostResource
ms.assetid: 5f8b32a8-d8cc-4045-a8be-0de0bbadcce4
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67207816c96a808118cceb52fc71782955f881cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-resource-based-throttling-settings"></a>Modificación de la configuración de límites basada en recursos
Mediante el uso del Panel de configuración, puede modificar la configuración de limitación basada en recursos de un host dado en todo el Grupo de BizTalk. Estas opciones se aplican a todas las instancias de host asignadas al host dado. En este tema se proporciona el procedimiento paso a paso para modificar esta configuración.  
  
 Para administrar el uso de recursos del sistema (como subprocesos, memoria y tamaño de la base de datos) por parte de un proceso de instancia de host, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa un mecanismo de limitación ajustable que rige el flujo y el procesamiento de mensajes a través de una instancia de host. El mecanismo de limitación de host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda a garantizar que el sistema funcione a un nivel óptimo y sostenible mediante lo siguiente:  
  
-   Moderando la carga de trabajo de la instancia de host.  
  
-   Impidiendo la contención de recursos que puede reducir el rendimiento general del proceso de instancia de host u otros procesos del sistema.  
  
-   Detectando cuándo se están infrautilizando los recursos disponibles.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-modify-the-resource-based-throttling-settings-of-a-host"></a>Procedimiento para modificar la configuración de limitación basada en recursos de un host  
  
1.  En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  
  
2.  En el **panel de configuración de BizTalk** cuadro de diálogo la **Hosts** , haga clic en el **limitación basada en recursos** ficha.  
  
3.  Realice lo siguiente y, a continuación, haga clic en **aplicar** para aplicar las modificaciones y continuar en otra ficha. En caso contrario, haga clic en **Aceptar** para aplicar las modificaciones y salir del panel de configuración.  
  
    |**Use esto**|Para|Valores límite|Valor predeterminado|Actualizar lógica|  
    |------------------|----------------|---------------------|-------------------|-------------------|  
    |**Host**|En la lista desplegable, seleccione el host que representa las instancias en tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|-|-|-|  
    |**Configuración por CPU**||-|-|-|  
    |**Subprocesos**|Especifique el número máximo de subprocesos disponibles en el proceso (por CPU) permitido antes de que empiece la limitación.|[0, valor máximo de tipo entero)|0|-|  
    |**Conexiones de base de datos**|Especifique el número máximo de sesiones de base de datos (por CPU) permitidas antes de que empiece la limitación.|1 – Valor máximo de tipo entero|0|-|  
    |**Mensajes en curso**|Especifique el número máximo de mensajes entregados al Gestor extremo (EPM) o a XLANG que no se han procesado. Esto no incluye los mensajes que se han recuperado de la base de datos pero que aún esperan ser entregados en la cola en memoria.|1 – Valor máximo de tipo entero|1000|-|  
    |**Tamaño de cola de mensajes interna**|Indique el tamaño de la cola en memoria. Esta cola actúa como un marcador de posición temporal para entregar los mensajes.<br /><br /> Establecer un valor grande para este parámetro puede mejorar escenarios de baja latencia en cierta medida ya que se recuperarán de forma proactiva más mensajes de la base de datos de cuadro de mensajes para su procesamiento. Ya que los mensajes de esta cola consumen memoria, sería conveniente establecer este parámetro con un valor inferior para los escenarios que conllevan mensajes grandes y así evitar una limitación basada en memoria del proceso. **Nota:** si modifica este valor, el host debe reiniciarse para que el cambio surta efecto.|1 – Valor máximo de tipo entero|100|-|  
    |**Número de mensajes en la base de datos**|Indique el número total de mensajes publicados por esta instancia de host en las colas de trabajo, estado y suspensión de los host de suscripción.<br /><br /> El **recuento en la base de datos del mensaje** define también indirectamente el umbral para una condición de limitación en función del número de mensajes en la tabla de cola de impresión o la tabla de seguimiento. Si el número de mensajes en la tabla de cola o en la tabla de seguimiento excede este valor 10 veces, se desencadena una condición de limitación.|1 – Valor máximo de tipo entero|50000|-|  
    |**Uso de memoria**||-|-|-|  
    |**Global física**|Especifique (como porcentaje) el uso máximo de memoria virtual permitido en todo el sistema antes de que empiece la limitación.|0: deshabilitar<br /><br /> 1% – 100%<br /><br /> Los valores > 100% se tratan como MB y pueden crecer hasta el máximo int|0|-|  
    |**Virtual de proceso**|Especifique el máximo de memoria de proceso (como porcentaje) permitido antes de que empiece la limitación (como porcentaje o megabytes).|0: deshabilitar<br /><br /> 1% – 100%<br /><br /> Los valores > 100% se tratan como MB y pueden crecer hasta el máximo int|25|-|  
    |**Multiplicador de cola de impresión**|Indique el factor por el que el **recuento en la base de datos del mensaje** umbral se multiplica y, a continuación, se compara con el número de registro actual en la tabla de cola de impresión.<br /><br /> Esto se realiza para determinar si el sistema debe limitar el tamaño de tabla de cola de impresión. Si se establece en 0, el tamaño de la tabla de cola de impresión no se tiene en cuenta para determinar una condición de limitación.|0-1000|10|Los parámetros de limitación leídos del registro deben asignarse uno a uno a parámetros de instancia de host.|  
    |**Multiplicador de datos de seguimiento**|Especificar el factor por el que el **recuento en la base de datos del mensaje** umbral se multiplica y, a continuación, se compara con el número de registro actual en la tabla de seguimiento.<br /><br /> Esto se realiza para determinar si el sistema debe limitar el tamaño de la tabla de seguimiento. Si se establece en 0, el tamaño de la tabla de seguimiento no se tiene en cuenta para determinar una condición de limitación.|0-1000|10|Los parámetros de limitación leídos del registro deben asignarse uno a uno a parámetros de instancia de host.|  
    |**Límite para activar GC**|Especifica cuándo se desencadenará una recolección de elementos no utilizados (GC) de .NET a medida que el consumo de memoria de proceso aumente y se aproxime al umbral. Cuando el consumo de memoria supera este valor de porcentaje del umbral de memoria, se desencadena una GC.|50-100|80|Los parámetros de limitación leídos del registro deben asignarse uno a uno a parámetros de instancia de host.|  
    |**Umbral de memoria por lote**|Indique (como porcentaje) el umbral de memoria más allá del cual se debe limitar la publicación de un lote de mensajes.<br /><br /> El umbral de memoria por lote se calcula multiplicando este factor de porcentaje por el **virtual de proceso** umbral. Si la memoria que se estima necesaria para ejecutar un lote de publicación supera el umbral de memoria por lote, el lote está sujeto a limitación basada en memoria de proceso. En caso contrario, el lote se excluye de la limitación de procesos basada en memoria incluso cuando la memoria de proceso total supera la **virtual de proceso** umbral.<br /><br /> Un valor cero indica que todos los lotes de publicación pueden estar sujetos a limitación basada en memoria de proceso aunque la memoria que se estime necesaria para ejecutar el lote sea mínima.|0%-100%||Los parámetros de limitación leídos del registro deben asignarse uno a uno a parámetros de instancia de host.|  
    |**Severity**||-|-|-|  
    |**Memoria**|Indica la gravedad de una condición de limitación desencadenada por una memoria de proceso. Especifica el valor de porcentaje, este parámetro establece la gravedad de una condición de limitación causada cuando la **virtual de proceso** se supera el umbral.|1 – 1000|500|El menor de todos los valores de instancia de host|  
    |**Tamaño de base de datos**|Controla la gravedad de una condición de limitación desencadenada por el tamaño de una base de datos. Especificado en valor de porcentaje, este parámetro establece la gravedad de una condición de limitación causada cuando la **recuento en la base de datos del mensaje** se superó el umbral.|1 – 1000|1|El menor de todos los valores de instancia de host|  
    |**Mensaje en proceso**|Especifique el tiempo de reacción de limitación cuando el valor de **mensajes en curso** supera el umbral. Esto se especifica en el valor de porcentaje y este parámetro establece la gravedad de una condición de limitación causada cuando el valor de **mensajes en curso** se superó el umbral.|1 – 1000|75|El menor de todos los valores de instancia de host|  
  
    > [!NOTE]
    >  Para restaurar la configuración predeterminada, haga clic en **Restaurar valores predeterminados**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo modificar la configuración de Host](../core/how-to-modify-host-settings.md)