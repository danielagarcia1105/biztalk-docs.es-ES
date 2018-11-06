---
title: Configurar la zona horaria y la programación de periodicidad en BizTalk Server | Microsoft Docs
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
ms.openlocfilehash: fe12e4fe81705d178520f02591f8179e47606f6c
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753308"
---
# <a name="configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server"></a>Configurar la zona horaria y la programación de periodicidad en BizTalk Server
Establezca la zona horaria y configurar una programación de periodicidad en sus ubicaciones de recepción en [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , la característica de programación avanzada en las ubicaciones de recepción incluye algunas opciones. Uso de las opciones de programación, establezca la zona horaria y también establecer una programación de periodicidad avanzada.

Este tema muestra cómo configurar estas características.

## <a name="prerequisites"></a>Requisitos previos
Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].

## <a name="time-zone"></a>Zona horaria

El **programación** incluye las propiedades de una ubicación de recepción un **zona horaria** propiedad. Cuando se establece, se usa la zona horaria que elija en la ubicación de recepción en lugar de la zona horaria en el equipo local. 

Todas las fechas y horas en el **programación** propiedades son específicas de la zona horaria que elija. Las programaciones existentes se migran a la zona horaria del servidor que hospeda la base de datos de administración de BizTalk (BizTalkMgmtDb). 

También puede ajustar para el horario de verano (DST). Cuando está activada, la programación se ajusta automáticamente para el horario de verano de la zona horaria que elija. Esta opción no influye en la programación si:

* La zona horaria especificada no tiene un horario de verano
* No se aplica el horario de verano en la zona horaria que elija

## <a name="enable-recurrence-schedule"></a>Habilitar la programación de periodicidad
1. En el **administración de BizTalk Server** de consola, haga clic en uno de sus ubicaciones de recepción y seleccione **propiedades**. 
2. En el **programación** página, seleccione **habilitar ventana de servicio**. El **Start Time** y **hora de finalización** establecer la hora inicial de la programación se puede ejecutar:

    ![Habilitar servicio de Windows para el puerto de recepción](../core/media/enable-service-windows-for-receive-port.PNG)

3. Se muestran las opciones de programación adicionales:

    ![Programación avanzada para el puerto de recepción](../core/media/advanced-scheduling-for-receive-port.PNG)

4. El **periodicidad** propiedad ejecuta cada día, semana o mes que elija el puerto de recepción: 

    1. Use la **diaria** periodicidad para el puerto de recepción de ejecutar cada *x* número de días, empezando en el **desde** fecha seleccionada, y solo dentro el **ventana de servicio**  elija:

        ![Programación diaria](../core/media/daily-schedule.png)

    2. Use la **semanal** periodicidad para ejecutar el puerto de recepción en un día concreto dentro de una semana y solo dentro del **ventana de servicio** elija: 

        ![Programación semanal](../core/media/weekly-schedule.png)

    3. Use la **mensual** periodicidad para ejecutar el puerto de recepción según una programación mensual. El **días** y **en** opciones están disponibles. 
    
        Use la **días** periodicidad para ejecutar el puerto de recepción en fechas concretas dentro de la **meses** elija: 

        ![Programación mensual](../core/media/monthly-schedule.PNG)

        Use la **en** periodicidad para ejecutar el puerto de recepción en días específicos del mes:

        ![mensualmente en programación](../core/media/monthly-on-schedule.PNG)

5. Seleccione **Aceptar** para guardar los cambios. 

## <a name="see-also"></a>Vea también
[Configuración del Feature Pack](../core/configure-the-feature-pack.md)
