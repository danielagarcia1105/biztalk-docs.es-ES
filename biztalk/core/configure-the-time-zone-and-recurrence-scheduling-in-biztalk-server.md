---
title: Configurar la zona horaria y la programación de periodicidad en BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60ae7be-747e-4034-8b99-46bd7e25fe67
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ab4cd85af0d15d7b089b106dc33aa77f1a10639
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
ms.locfileid: "25497773"
---
# <a name="configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server"></a>Configurar la zona horaria y la programación de periodicidad en BizTalk Server
Establecer la zona horaria y configurar una programación de periodicidad en sus ubicaciones de recepción en [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , la característica de programación avanzada en las ubicaciones de recepción incluye algunas opciones. Usar las avanzadas opciones de programación, establezca la zona horaria y establecer una programación periódica.

En este tema se muestra cómo configurar estas características.

## <a name="prerequisites"></a>Requisitos previos
Instalar [Feature Pack 2](https://aka.ms/bts2016fp2) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].

## <a name="time-zone"></a>Zona horaria

El **programación** propiedades de una ubicación de recepción incluye un **zona horaria** propiedad. Cuando se establece, la zona horaria que elija en la ubicación de recepción se utiliza en lugar de la zona horaria en el equipo local. 

Todas las fechas y horas en el **programación** propiedades son específicas para la zona horaria que elija. Las programaciones existentes se migran a la zona horaria del servidor que hospeda la base de datos de administración de BizTalk (BizTalkMgmtDb). 

También puede ajustar para el horario de verano (DST). Al activar esta opción, la programación se ajusta automáticamente para el horario de verano de la zona horaria que elija. Esta opción no influye en la programación si:

* La zona horaria especificada no tiene un horario de verano
* No se observa el horario de verano en la zona horaria que elija

## <a name="enable-recurrence-schedule"></a>Habilitar la programación de periodicidad
1. En el **administración de BizTalk Server** de la consola, haga clic en uno de sus ubicaciones de recepción y seleccione **propiedades**. 
2. En el **programación** página, seleccione **habilitar ventana de servicio**. El **Start Time** y **hora de finalización** establecer la hora inicial de la programación se puede ejecutar:

    ![Habilitar ventanas de servicio para el puerto de recepción](../core/media/enable-service-windows-for-receive-port.PNG)

3. Se muestran las opciones de programación adicionales:

    ![Programación avanzada para el puerto de recepción](../core/media/advanced-scheduling-for-receive-port.PNG)

4. El **periodicidad** propiedad ejecuta el puerto de recepción cada día, semana o mes que desee: 

    1. Use la **diaria** periodicidad para ejecutar el puerto de recepción cada *x* número de días especificado, empezando en el **de** fecha seleccionada, y solo dentro el **ventana de servicio**  elija:

        ![Programaciones diarias](../core/media/daily-shcedule.png)

    2. Use el **semanal** periodicidad para ejecutar el puerto de recepción en un día concreto dentro de una semana y solo dentro del **ventana de servicio** elija: 

        ![Programación semanal](../core/media/weekly-shcedule.png)

    3. Use la **mensual** periodicidad para ejecutar el puerto de recepción en una programación mensual. El **días** y **en** opciones están disponibles. 
    
        Use la **días** periodicidad para ejecutar el puerto de recepción en fechas concretas dentro de la **meses** elija: 

        ![Programación mensual](../core/media/monthly-shcedule.PNG)

        Use la **en** periodicidad para ejecutar el puerto de recepción en determinados días del mes:

        ![mensualmente en programación](../core/media/monthly-on-shcedule.PNG)

5. Seleccione **Aceptar** para guardar los cambios. 

## <a name="see-also"></a>Vea también
[Configurar el Feature Pack](../core/configure-the-feature-pack.md)