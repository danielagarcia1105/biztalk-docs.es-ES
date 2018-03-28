---
title: Propiedades predeterminadas de deshidratación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68c59def-d73b-4880-9884-ccbe5d982f4b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff78b1e096f1a73675ffc02550794f5a300f5614
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="dehydration-default-properties"></a>Propiedades predeterminadas de deshidratación
A continuación se proporcionan los nombres de las propiedades de deshidratación y sus valores predeterminados. Estas propiedades se pueden configurar en [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] o como XML en el archivo de configuración de BizTalk (BTSNTSvc.exe.config o BTSNTSvc64.exe.config). Los valores del archivo de configuración de BizTalk se aplican antes. A continuación, se aplica la configuración de [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]. Las propiedades de deshidratación se leen cuando se inician todas las instancias de host que contienen una orquestación.  
  
> [!IMPORTANT]
>  No toda la configuración de orquestación se expone en [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]. Para esta configuración, se usa el archivo de configuración de BizTalk (BTSNTSvc.exe.config o BTSNTSvc64.exe.config). Cuando se usa el archivo de configuración de BizTalk, muchas propiedades no aparecen en la lista. Sin embargo, estas propiedades se aplican con sus valores predeterminados aunque no se especifiquen explícitamente en el archivo de configuración.  
  
 Para cambiar los valores predeterminados, puede usar [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] o agregarlos explícitamente al archivo de configuración de BizTalk. Para obtener más información, consulte [uso del panel de configuración para la optimización de rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) y [archivo BTSNTSvc.exe.config](../core/btsntsvc-exe-config-file.md).  
  
 **Deshidratación**  
  
-   **MaxThreshold** = 1800  
  
-   **MinThreshold** = 1  
  
-   **ConstantThreshold** = -1  
  
 **VirtualMemoryThrottlingCriteria**  
  
-   **OptimalUsage** = 900  
  
-   **MaximalUsage** =  1300  
  
-   **IsActive** = true  
  
 **PrivateMemoryThrottlingCriteria**  
  
-   **OptimalUsage** = 50  
  
-   **MaximalUsage** =  350  
  
-   **IsActive** = true  
  
 **PhysicalMemoryThrottlingCriteria**  
  
-   **OptimalUsage** = 90  
  
-   **MaximalUsage** =  95  
  
-   **IsActive** = false  
  
 Cada una de estas propiedades se describe a continuación de forma detallada.  
  
## <a name="dehydration"></a>Deshidratación  
 **MaxThreshold** y **MinThreshold** son la parte superior y reducir los límites, en segundos, del tiempo que puede estar bloqueada una orquestación en una suscripción (es decir, bloqueada por una recepción, escucha o retraso) antes de su deshidratación. También habrá un valor calculado en tiempo de ejecución, denominado **TestThreshold**, y su valor, en segundos, entre **MinThreshold** y **MaxThreshold**.  
  
 Si establece un valor además del valor predeterminado de -1 para **ConstantThreshold**, no habrá un valor de tiempo de ejecución **TestThreshold**. Cuando se bloquea una orquestación en una suscripción, y el historial de cuánto tiempo se han bloqueado todas las instancias de esa orquestación en esa suscripción es mayor que el valor de **TestThreshold**, aparecerán de la orquestación deshidratar. En caso contrario, si el historial es inferior a **TestThreshold** valor no se deshidratará la orquestación. Además, aunque el historial indique que deshidratación no llevará a cabo, si el tiempo de bloqueo actual llega a 2 ***TestThreshold**, a continuación, llevará a cabo la deshidratación. El historial queda definido por el promedio de los últimos diez intervalos de tiempo de espera en segundos o por cuantos tiempos de espera haya en el historial si su número es inferior a diez.  
  
 Cuando el valor de **TestThreshold** tiende hacia **MinThreshold** como uso de memoria aumenta, se llama "memoria según la limitación de deshidratación". Esta limitación permite que haya más instancias de orquestación activas porque, cuando cualquiera de ellas está bloqueada esperando alguna actividad (es decir, esperando un mensaje o un retraso), se pueden deshidratar y extraerse de la memoria. **TestThreshold** es una función de reducción continua del uso de memoria, y es inversamente proporcional al uso de memoria.  
  
 A continuación se proporcionan descripciones de cada una de las propiedades de deshidratación:  
  
-   **MaxThreshold**: los límites superiores, en segundos, del tiempo que puede estar bloqueada una orquestación en una suscripción antes de su deshidratación.  
  
-   **MinThreshold**: los límites inferiores, en segundos, del tiempo que puede estar bloqueada una orquestación en una suscripción antes de su deshidratación.  
  
-   **ConstantThreshold**: el umbral dinámico, que generalmente fluctúa entre los valores mínimos y máximo especificados. Sin embargo, puede convertir el umbral en un valor fijo si define esta propiedad. Un valor de -1 indica al motor que no utilice un umbral constante. No defina esta propiedad con un valor distinto de -1 porque deshabilitará la limitación basada en la deshidratación.  
  
## <a name="virtualmemorythrottlingcriteria"></a>VirtualMemoryThrottlingCriteria  
 En la actualidad, la memoria virtual puede convertirse en un cuello de botella en equipos de 32 bits debido a la fragmentación no administrada de montones, por lo que debe establecer una limitación también según este recurso. Debe volver a realizar la configuración si /3GB está definido o si los hosts se ejecutan en una plataforma de 64 bits. Los usos óptimo y máximo se expresan en MB.  
  
 A continuación se proporcionan descripciones de cada una de las propiedades de VirtualMemoryThrottlingCriteria:  
  
-   **OptimalUsage**: la cantidad de uso de memoria virtual en qué deshidratación limitación empieza a surtir efecto. En este momento, **TestThreshold** tiene el valor **MaxThreshold** y cualquier uso de memoria mayor **OptimalUsage** hace **TestThreshold**sea inferior a **MaxThreshold**.  
  
-   **MaximalUsage**: la cantidad de uso de memoria virtual en que deshidratación limitación es como máximo. En este momento, **TestThreshold** tiene el valor **MinThreshold** y cualquier uso de memoria inferior a **MaximalUsage** hace **TestThreshold** debe ser mayor que **MinThreshold**.  
  
-   **IsActive**: un valor booleano que indica si la limitación de memoria virtual está activa.  
  
## <a name="privatememorythrottlingcriteria"></a>PrivateMemoryThrottlingCriteria  
 Esta propiedad resulta un criterio útil para la limitación, pero los valores adecuados dependen de si el equipo está ejecutando otros servicios de Windows. Si el equipo dispone de mucha memoria y no se comparte con otros servicios de Windows, podrá aumentar estos valores de forma significativa.  
  
 A continuación se proporcionan descripciones de cada una de las propiedades de PrivateMemoryThrottlingCriteria:  
  
-   **OptimalUsage**: la cantidad de uso de memoria privada, en MB, en qué deshidratación limitación empieza a surtir efecto. En este momento **TestThreshold** tiene el valor **MaxThreshold** y cualquier uso de memoria mayor **OptimalUsage** hace **TestThreshold**sea inferior a **MaxThreshold**.  
  
-   **MaximalUsage**: la cantidad de uso de memoria privada, en MB, en qué deshidratación limitación se encuentra en su punto máximo. En este momento **TestThreshold** tiene el valor **MinThreshold** y cualquier uso de memoria inferior a **MaximalUsage** hace **TestThreshold** debe ser mayor que **MinThreshold**.  
  
-   **IsActive**: un valor booleano que indica si la limitación de memoria privada está activa.  
  
## <a name="physicalmemorythrottlingcriteria"></a>PhysicalMemoryThrottlingCriteria  
 También existe una limitación de memoria física donde las cifras se expresan como el porcentaje de memoria utilizado en lugar de como la cantidad de MB. Esta propiedad está deshabilitada de forma predeterminada, pero puede habilitarla si es necesario.  
  
 A continuación se proporcionan descripciones de cada una de las propiedades de PhysicalMemoryThrottlingCriteria:  
  
-   **OptimalUsage**: el porcentaje óptimo de memoria física que se utilizará para las instancias de host.  
  
-   **MaximalUsage**: el porcentaje máximo de memoria física que se utilizará para las instancias de host.  
  
-   **IsActive**: valor booleano que indica si la limitación de memoria física está activa.  
  
## <a name="dehydration-properties-behavior"></a>Comportamiento de las propiedades de deshidratación  
 BizTalk Server utiliza estas propiedades de deshidratación para decidir cuándo deshidratar y rehidratar las orquestaciones. En condiciones de carga normal, los valores predeterminados de deshidratación son suficientes pero, si está trabajando con un nivel de carga alto y desea cambiar las características de rendimiento, deberá ajustarlos por sí mismo.  
  
 El comportamiento de la deshidratación de BizTalk Server depende por completo de la cantidad de memoria disponible y de la cantidad de memoria en uso. El comportamiento de la deshidratación es distinto con cantidades de memoria diferentes y existen diferencias en el uso de la memoria entre hosts de 32 y 64 bits.  
  
 Las propiedades de deshidratación establecen diferencias entre Bytes privados y Bytes virtuales en lo que respecta al host de orquestación:  
  
-   **Bytes virtuales**. Se trata de tamaño debe aplicarse, en bytes, del espacio de direcciones virtuales que el proceso está usando. El uso del espacio de direcciones virtuales no implica necesariamente un uso equivalente de páginas de disco o de memoria principal. Sin embargo, el espacio virtual es finito y el proceso puede limitar su capacidad para cargar bibliotecas.  
  
-   **Bytes privados**. se trata del tamaño actual, expresado en bytes, de la memoria que este proceso ha asignado y que no puede compartirse con otros procesos.