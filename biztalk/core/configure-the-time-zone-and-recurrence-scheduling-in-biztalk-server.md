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
# <a name="configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server"></a><span data-ttu-id="81f84-102">Configurar la zona horaria y la programación de periodicidad en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="81f84-102">Configure the time zone and recurrence scheduling in BizTalk Server</span></span>
<span data-ttu-id="81f84-103">Establezca la zona horaria y configurar una programación de periodicidad en sus ubicaciones de recepción en [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81f84-103">Set the timezone and configure a recurrence schedule on your receive locations in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="81f84-104">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , la característica de programación avanzada en las ubicaciones de recepción incluye algunas opciones.</span><span class="sxs-lookup"><span data-stu-id="81f84-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, the advanced scheduling feature on receive locations includes some options.</span></span> <span data-ttu-id="81f84-105">Uso de las opciones de programación, establezca la zona horaria y también establecer una programación de periodicidad avanzada.</span><span class="sxs-lookup"><span data-stu-id="81f84-105">Using the advanced scheduling options, set the time zone, and also set a recurrence schedule.</span></span>

<span data-ttu-id="81f84-106">Este tema muestra cómo configurar estas características.</span><span class="sxs-lookup"><span data-stu-id="81f84-106">This topic shows you how to configure these features.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="81f84-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="81f84-107">Prerequisites</span></span>
<span data-ttu-id="81f84-108">Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81f84-108">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="time-zone"></a><span data-ttu-id="81f84-109">Zona horaria</span><span class="sxs-lookup"><span data-stu-id="81f84-109">Time zone</span></span>

<span data-ttu-id="81f84-110">El **programación** incluye las propiedades de una ubicación de recepción un **zona horaria** propiedad.</span><span class="sxs-lookup"><span data-stu-id="81f84-110">The **Schedule** properties of a receive location includes a **Time Zone** property.</span></span> <span data-ttu-id="81f84-111">Cuando se establece, se usa la zona horaria que elija en la ubicación de recepción en lugar de la zona horaria en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="81f84-111">When set, the time zone you choose in the receive location is used instead of the time zone on the local computer.</span></span> 

<span data-ttu-id="81f84-112">Todas las fechas y horas en el **programación** propiedades son específicas de la zona horaria que elija.</span><span class="sxs-lookup"><span data-stu-id="81f84-112">All dates and times in the **Schedule** properties are specific to the time zone you choose.</span></span> <span data-ttu-id="81f84-113">Las programaciones existentes se migran a la zona horaria del servidor que hospeda la base de datos de administración de BizTalk (BizTalkMgmtDb).</span><span class="sxs-lookup"><span data-stu-id="81f84-113">Any existing schedules are migrated to the time zone of the server hosting the BizTalk Management database (BizTalkMgmtDb).</span></span> 

<span data-ttu-id="81f84-114">También puede ajustar para el horario de verano (DST).</span><span class="sxs-lookup"><span data-stu-id="81f84-114">You can also adjust for daylight saving time (DST).</span></span> <span data-ttu-id="81f84-115">Cuando está activada, la programación se ajusta automáticamente para el horario de verano de la zona horaria que elija.</span><span class="sxs-lookup"><span data-stu-id="81f84-115">When checked, the schedule automatically adjusts to the daylight saving time of the time zone you choose.</span></span> <span data-ttu-id="81f84-116">Esta opción no influye en la programación si:</span><span class="sxs-lookup"><span data-stu-id="81f84-116">This option has no impact on the schedule if:</span></span>

* <span data-ttu-id="81f84-117">La zona horaria especificada no tiene un horario de verano</span><span class="sxs-lookup"><span data-stu-id="81f84-117">The specified time zone does not have a daylight saving time</span></span>
* <span data-ttu-id="81f84-118">No se aplica el horario de verano en la zona horaria que elija</span><span class="sxs-lookup"><span data-stu-id="81f84-118">Daylight saving time is not observed in the time zone you choose</span></span>

## <a name="enable-recurrence-schedule"></a><span data-ttu-id="81f84-119">Habilitar la programación de periodicidad</span><span class="sxs-lookup"><span data-stu-id="81f84-119">Enable recurrence schedule</span></span>
1. <span data-ttu-id="81f84-120">En el **administración de BizTalk Server** de consola, haga clic en uno de sus ubicaciones de recepción y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="81f84-120">In the **BizTalk Server Administration** console, right-click one of your receive locations, and select **Properties**.</span></span> 
2. <span data-ttu-id="81f84-121">En el **programación** página, seleccione **habilitar ventana de servicio**.</span><span class="sxs-lookup"><span data-stu-id="81f84-121">On the **Scheduling** page, select **Enable service window**.</span></span> <span data-ttu-id="81f84-122">El **Start Time** y **hora de finalización** establecer la hora inicial de la programación se puede ejecutar:</span><span class="sxs-lookup"><span data-stu-id="81f84-122">The **Start Time** and **Stop time** set the initial time the schedule is allowed to run:</span></span>

    ![Habilitar servicio de Windows para el puerto de recepción](../core/media/enable-service-windows-for-receive-port.PNG)

3. <span data-ttu-id="81f84-124">Se muestran las opciones de programación adicionales:</span><span class="sxs-lookup"><span data-stu-id="81f84-124">The additional scheduling options are displayed:</span></span>

    ![Programación avanzada para el puerto de recepción](../core/media/advanced-scheduling-for-receive-port.PNG)

4. <span data-ttu-id="81f84-126">El **periodicidad** propiedad ejecuta cada día, semana o mes que elija el puerto de recepción:</span><span class="sxs-lookup"><span data-stu-id="81f84-126">The **Recurrence** property runs the receive port every day, week, or month that you choose:</span></span> 

    1. <span data-ttu-id="81f84-127">Use la **diaria** periodicidad para el puerto de recepción de ejecutar cada *x* número de días, empezando en el **desde** fecha seleccionada, y solo dentro el **ventana de servicio**  elija:</span><span class="sxs-lookup"><span data-stu-id="81f84-127">Use the **Daily** recurrence to run the receive port every *x* number of days, starting on the **From** date you choose, and only within the **service window** you choose:</span></span>

        ![Programación diaria](../core/media/daily-schedule.png)

    2. <span data-ttu-id="81f84-129">Use la **semanal** periodicidad para ejecutar el puerto de recepción en un día concreto dentro de una semana y solo dentro del **ventana de servicio** elija:</span><span class="sxs-lookup"><span data-stu-id="81f84-129">Use the **Weekly** recurrence to run the receive port on a specific day within a week, and only within the **service window** you choose:</span></span> 

        ![Programación semanal](../core/media/weekly-schedule.png)

    3. <span data-ttu-id="81f84-131">Use la **mensual** periodicidad para ejecutar el puerto de recepción según una programación mensual.</span><span class="sxs-lookup"><span data-stu-id="81f84-131">Use the **Monthly** recurrence to run the receive port on a monthly schedule.</span></span> <span data-ttu-id="81f84-132">El **días** y **en** opciones están disponibles.</span><span class="sxs-lookup"><span data-stu-id="81f84-132">The **Days** and **On** options are available.</span></span> 
    
        <span data-ttu-id="81f84-133">Use la **días** periodicidad para ejecutar el puerto de recepción en fechas concretas dentro de la **meses** elija:</span><span class="sxs-lookup"><span data-stu-id="81f84-133">Use the **Days** recurrence to run the receive port on specific dates within the **months** you choose:</span></span> 

        ![Programación mensual](../core/media/monthly-schedule.PNG)

        <span data-ttu-id="81f84-135">Use la **en** periodicidad para ejecutar el puerto de recepción en días específicos del mes:</span><span class="sxs-lookup"><span data-stu-id="81f84-135">Use the **On** recurrence to run the receive port on specific days of the month:</span></span>

        ![mensualmente en programación](../core/media/monthly-on-schedule.PNG)

5. <span data-ttu-id="81f84-137">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="81f84-137">Select **OK** to save your changes.</span></span> 

## <a name="see-also"></a><span data-ttu-id="81f84-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="81f84-138">See also</span></span>
[<span data-ttu-id="81f84-139">Configuración del Feature Pack</span><span class="sxs-lookup"><span data-stu-id="81f84-139">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)
