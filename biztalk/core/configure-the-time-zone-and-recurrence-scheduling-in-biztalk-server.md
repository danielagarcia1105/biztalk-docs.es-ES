---
title: "Configurar la zona horaria y la programación de periodicidad en BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d60ae7be-747e-4034-8b99-46bd7e25fe67
caps.latest.revision: "5"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 918d12e2dc96723327f4d0b0d2b0f0d435d6e42e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server"></a><span data-ttu-id="c772f-102">Configurar la zona horaria y la programación de periodicidad en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c772f-102">Configure the time zone and recurrence scheduling in BizTalk Server</span></span>
<span data-ttu-id="c772f-103">Establecer la zona horaria y configurar una programación de periodicidad en sus ubicaciones de recepción en [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c772f-103">Set the timezone and configure a recurrence schedule on your receive locations in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="c772f-104">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , la característica de programación avanzada en las ubicaciones de recepción incluye algunas opciones.</span><span class="sxs-lookup"><span data-stu-id="c772f-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, the advanced scheduling feature on receive locations includes some options.</span></span> <span data-ttu-id="c772f-105">Usar las avanzadas opciones de programación, establezca la zona horaria y establecer una programación periódica.</span><span class="sxs-lookup"><span data-stu-id="c772f-105">Using the advanced scheduling options, set the time zone, and also set a recurrence schedule.</span></span>

<span data-ttu-id="c772f-106">En este tema se muestra cómo configurar estas características.</span><span class="sxs-lookup"><span data-stu-id="c772f-106">This topic shows you how to configure these features.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c772f-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c772f-107">Prerequisites</span></span>
<span data-ttu-id="c772f-108">Instalar [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c772f-108">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="time-zone"></a><span data-ttu-id="c772f-109">Zona horaria</span><span class="sxs-lookup"><span data-stu-id="c772f-109">Time zone</span></span>

<span data-ttu-id="c772f-110">El **programación** propiedades de una ubicación de recepción incluye un **zona horaria** propiedad.</span><span class="sxs-lookup"><span data-stu-id="c772f-110">The **Schedule** properties of a receive location includes a **Time Zone** property.</span></span> <span data-ttu-id="c772f-111">Cuando se establece, la zona horaria que elija en la ubicación de recepción se utiliza en lugar de la zona horaria en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="c772f-111">When set, the time zone you choose in the receive location is used instead of the time zone on the local computer.</span></span> 

<span data-ttu-id="c772f-112">Todas las fechas y horas en el **programación** propiedades son específicas para la zona horaria que elija.</span><span class="sxs-lookup"><span data-stu-id="c772f-112">All dates and times in the **Schedule** properties are specific to the time zone you choose.</span></span> <span data-ttu-id="c772f-113">Las programaciones existentes se migran a la zona horaria del servidor que hospeda la base de datos de administración de BizTalk (BizTalkMgmtDb).</span><span class="sxs-lookup"><span data-stu-id="c772f-113">Any existing schedules are migrated to the time zone of the server hosting the BizTalk Management database (BizTalkMgmtDb).</span></span> 

<span data-ttu-id="c772f-114">También puede ajustar para el horario de verano (DST).</span><span class="sxs-lookup"><span data-stu-id="c772f-114">You can also adjust for daylight saving time (DST).</span></span> <span data-ttu-id="c772f-115">Al activar esta opción, la programación se ajusta automáticamente para el horario de verano de la zona horaria que elija.</span><span class="sxs-lookup"><span data-stu-id="c772f-115">When checked, the schedule automatically adjusts to the daylight saving time of the time zone you choose.</span></span> <span data-ttu-id="c772f-116">Esta opción no influye en la programación si:</span><span class="sxs-lookup"><span data-stu-id="c772f-116">This option has no impact on the schedule if:</span></span>

* <span data-ttu-id="c772f-117">La zona horaria especificada no tiene un horario de verano</span><span class="sxs-lookup"><span data-stu-id="c772f-117">The specified time zone does not have a daylight saving time</span></span>
* <span data-ttu-id="c772f-118">No se observa el horario de verano en la zona horaria que elija</span><span class="sxs-lookup"><span data-stu-id="c772f-118">Daylight saving time is not observed in the time zone you choose</span></span>

## <a name="enable-recurrence-schedule"></a><span data-ttu-id="c772f-119">Habilitar la programación de periodicidad</span><span class="sxs-lookup"><span data-stu-id="c772f-119">Enable recurrence schedule</span></span>
1. <span data-ttu-id="c772f-120">En el **administración de BizTalk Server** de la consola, haga clic en uno de sus ubicaciones de recepción y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c772f-120">In the **BizTalk Server Administration** console, right-click one of your receive locations, and select **Properties**.</span></span> 
2. <span data-ttu-id="c772f-121">En el **programación** página, seleccione **habilitar ventana de servicio**.</span><span class="sxs-lookup"><span data-stu-id="c772f-121">On the **Scheduling** page, select **Enable service window**.</span></span> <span data-ttu-id="c772f-122">El **Start Time** y **hora de finalización** establecer la hora inicial de la programación se puede ejecutar:</span><span class="sxs-lookup"><span data-stu-id="c772f-122">The **Start Time** and **Stop time** set the initial time the schedule is allowed to run:</span></span>

    ![Habilitar ventanas de servicio para el puerto de recepción](../core/media/enable-service-windows-for-receive-port.PNG)

3. <span data-ttu-id="c772f-124">Se muestran las opciones de programación adicionales:</span><span class="sxs-lookup"><span data-stu-id="c772f-124">The additional scheduling options are displayed:</span></span>

    ![Programación avanzada para el puerto de recepción](../core/media/advanced-scheduling-for-receive-port.PNG)

4. <span data-ttu-id="c772f-126">El **periodicidad** propiedad ejecuta el puerto de recepción cada día, semana o mes que desee:</span><span class="sxs-lookup"><span data-stu-id="c772f-126">The **Recurrence** property runs the receive port every day, week, or month that you choose:</span></span> 

    1. <span data-ttu-id="c772f-127">Use la **diaria** periodicidad para ejecutar el puerto de recepción cada *x* número de días especificado, empezando en el **de** fecha seleccionada, y solo dentro el **ventana de servicio**  elija:</span><span class="sxs-lookup"><span data-stu-id="c772f-127">Use the **Daily** recurrence to run the receive port every *x* number of days, starting on the **From** date you choose, and only within the **service window** you choose:</span></span>

        ![Programaciones diarias](../core/media/daily-shcedule.png)

    2. <span data-ttu-id="c772f-129">Use el **semanal** periodicidad para ejecutar el puerto de recepción en un día concreto dentro de una semana y solo dentro del **ventana de servicio** elija:</span><span class="sxs-lookup"><span data-stu-id="c772f-129">Use the **Weekly** recurrence to run the receive port on a specific day within a week, and only within the **service window** you choose:</span></span> 

        ![Programación semanal](../core/media/weekly-shcedule.png)

    3. <span data-ttu-id="c772f-131">Use la **mensual** periodicidad para ejecutar el puerto de recepción en una programación mensual.</span><span class="sxs-lookup"><span data-stu-id="c772f-131">Use the **Monthly** recurrence to run the receive port on a monthly schedule.</span></span> <span data-ttu-id="c772f-132">El **días** y **en** opciones están disponibles.</span><span class="sxs-lookup"><span data-stu-id="c772f-132">The **Days** and **On** options are available.</span></span> 
    
        <span data-ttu-id="c772f-133">Use la **días** periodicidad para ejecutar el puerto de recepción en fechas concretas dentro de la **meses** elija:</span><span class="sxs-lookup"><span data-stu-id="c772f-133">Use the **Days** recurrence to run the receive port on specific dates within the **months** you choose:</span></span> 

        ![Programación mensual](../core/media/monthly-shcedule.PNG)

        <span data-ttu-id="c772f-135">Use la **en** periodicidad para ejecutar el puerto de recepción en determinados días del mes:</span><span class="sxs-lookup"><span data-stu-id="c772f-135">Use the **On** recurrence to run the receive port on on specific days of the month:</span></span>

        ![mensualmente en programación](../core/media/monthly-on-shcedule.PNG)

5. <span data-ttu-id="c772f-137">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="c772f-137">Select **OK** to save your changes.</span></span> 

## <a name="see-also"></a><span data-ttu-id="c772f-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="c772f-138">See also</span></span>
[<span data-ttu-id="c772f-139">Configurar el Feature Pack</span><span class="sxs-lookup"><span data-stu-id="c772f-139">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)