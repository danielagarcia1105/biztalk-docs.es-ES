---
title: "Definir actividades económicas y vistas en Excel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating business activities
- monitoring business activities [BAM], creating business activities
ms.assetid: 000532f0-cb9a-40ac-a6c5-a8bd4e49f8d0
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91b9d3b213a6a6429759c0bb0d826798afa36da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="defining-business-activities-and-views-in-excel"></a><span data-ttu-id="1bb46-102">Definición de actividades económicas y vistas en Excel</span><span class="sxs-lookup"><span data-stu-id="1bb46-102">Defining Business Activities and Views in Excel</span></span>
<span data-ttu-id="1bb46-103">El primer paso para crear cualquier solución de BAM es identificar los datos que le interesan y la forma en que deben interpretarse.</span><span class="sxs-lookup"><span data-stu-id="1bb46-103">Your first step in creating any BAM solution is to identify what data you're interested in and how that data should be interpreted.</span></span> <span data-ttu-id="1bb46-104">Para ello, debe usar el complemento BAM para Excel.</span><span class="sxs-lookup"><span data-stu-id="1bb46-104">To do this, you use the BAM Add-in for Excel.</span></span> <span data-ttu-id="1bb46-105">Dicho complemento permite definir una lista de los datos de interés definiendo una actividad económica.</span><span class="sxs-lookup"><span data-stu-id="1bb46-105">The add-in allows you to define a wish-list of the data of interest by defining a business activity.</span></span> <span data-ttu-id="1bb46-106">También puede definir la forma en que los datos deben interpretarse y mostrarse a distintas categorías de usuarios empresariales.</span><span class="sxs-lookup"><span data-stu-id="1bb46-106">You can also define the way the data should be interpreted and shown to different categories of business users.</span></span>  
  
 <span data-ttu-id="1bb46-107">El complemento BAM permite al usuario definir agregaciones.</span><span class="sxs-lookup"><span data-stu-id="1bb46-107">The BAM Add-in also enables you to define aggregations.</span></span>  
  
 <span data-ttu-id="1bb46-108">También puede cambiar el nombre de los elementos de actividad; por ejemplo, en los casos en que la terminología habitual de algunos usuarios no coincida con los nombres de los elementos de datos correspondientes de la actividad.</span><span class="sxs-lookup"><span data-stu-id="1bb46-108">You can also rename activity items, for example, where the terminology some users are familiar with does not match the names of the corresponding data items in the activity.</span></span> <span data-ttu-id="1bb46-109">Esto podría deberse, por ejemplo, a que la vista está en otro idioma.</span><span class="sxs-lookup"><span data-stu-id="1bb46-109">One explanation for this is where the view is in a different language.</span></span>  
  
 <span data-ttu-id="1bb46-110">Una vez completada la definición de la actividad, Excel genera datos aleatorios de vista previa que pueden usarse para definir los gráficos deseados y otras formas de presentación.</span><span class="sxs-lookup"><span data-stu-id="1bb46-110">After you complete the activity definition, Excel generates random preview data that you can use to define the desired charts and other means of presentation.</span></span> <span data-ttu-id="1bb46-111">Para obtener más información acerca de los datos de vista previa, consulte [cómo utilizar la tabla dinámica](../core/how-to-use-the-pivottable.md).</span><span class="sxs-lookup"><span data-stu-id="1bb46-111">For more information about preview data, see [How to Use the PivotTable](../core/how-to-use-the-pivottable.md).</span></span>  
  
 <span data-ttu-id="1bb46-112">La definición de actividad completada define los puntos de datos y los eventos que debe recopilar cuando se ejecuta un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="1bb46-112">The completed activity definition defines the data points and events that you need collected when a business process is run.</span></span> <span data-ttu-id="1bb46-113">Puede obtener el complemento BAM para Excel de diversas fuentes.</span><span class="sxs-lookup"><span data-stu-id="1bb46-113">You can get the BAM Add-in from a variety of sources.</span></span>  
  
 <span data-ttu-id="1bb46-114">Puede instalar el XLA del complemento BAM durante la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="1bb46-114">You can install the BAM Add-in XLA during the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="1bb46-115">Para obtener más información, vea [Introducción a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)</span><span class="sxs-lookup"><span data-stu-id="1bb46-115">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)</span></span>  
  
 <span data-ttu-id="1bb46-116">Implementación de BAM. Archivo XLA se instala en una de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="1bb46-116">The BAM.XLA file is installed in one of the following locations:</span></span>  
  
-   <span data-ttu-id="1bb46-117">Si Microsoft Office no está instalado en el equipo, el archivo BAM.xla se instala en el BizTalk Server 20 \Program*xx*carpeta \ExcelDir\.</span><span class="sxs-lookup"><span data-stu-id="1bb46-117">If Microsoft Office is not installed on the computer, then the BAM.xla is installed to the \Program Files\Microsoft BizTalk Server 20*xx*\ExcelDir\ folder.</span></span>  
  
-   <span data-ttu-id="1bb46-118">Si está instalado Microsoft Office, el archivo BAM.xla se instalará en el \Program Office\OFFICE*xx*\Library\ carpeta.</span><span class="sxs-lookup"><span data-stu-id="1bb46-118">If Microsoft Office is installed, the BAM.xla is installed in the \Program Files\Microsoft Office\OFFICE*xx*\Library\ folder.</span></span>  
  
 <span data-ttu-id="1bb46-119">También puede copiar el archivo BAM.xla a su equipo desde una carpeta compartida de otro equipo.</span><span class="sxs-lookup"><span data-stu-id="1bb46-119">You can also copy the BAM.xla to your computer from a shared folder on another computer.</span></span> <span data-ttu-id="1bb46-120">Para registrar el XLA, selecciónelo en la ubicación a la que lo ha copiado.</span><span class="sxs-lookup"><span data-stu-id="1bb46-120">You can then register the XLA by selecting it from the location to which you copied it.</span></span>  
  
 <span data-ttu-id="1bb46-121">Para habilitar el complemento de BAM en la barra de herramientas del menú Excel, haga clic en el **archivo** menú, a continuación, haga clic en **opciones**y, a continuación, haga clic en **Add-Ins**. Seleccione **Business Activity Monitoring**, a continuación, haga clic en **vaya**, en la ventana complementos, active la casilla de verificación junto a **Business Activity Monitoring**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1bb46-121">To enable the BAM Add-in on the Excel menu toolbar, click the **File** menu, then click **Options**, and then click **Add-Ins**. Select **Business Activity Monitoring**, then click **GO**, In the Ad-ins window, select the check box next to **Business Activity Monitoring**, and then click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bb46-122">El uso del complemento BAM impide ejecutar Excel con dos instancias cargadas en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="1bb46-122">Using the BAM Add-in precludes running Excel with two instances loaded into the same process.</span></span>  <span data-ttu-id="1bb46-123">Cuando se usa el complemento, pueden darse varias instancias en el mismo proceso en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="1bb46-123">When using the add-in, multiple instances in the same process can occur in the following situations:</span></span>  
>   
>  <span data-ttu-id="1bb46-124">Cuando se tiene abierta una hoja de cálculo de Excel con el complemento BAM habilitado y se hace doble clic en otra hoja de cálculo de Excel; el programa intenta cargar la hoja de cálculo en la instancia actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="1bb46-124">When you have an Excel spreadsheet open with the BAM Add-in enabled, and you double-click a different Excel spreadsheet, Excel attempts to load the spreadsheet into the currently running instance.</span></span>  
>   
>  <span data-ttu-id="1bb46-125">Cuando se tiene abierta una hoja de cálculo de Excel con el complemento BAM habilitado y se usa la opción de menú Archivo/Abrir para cargar otra hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="1bb46-125">When you have an Excel spreadsheet open, with the BAM Add-in enabled, and you use the File/Open menu option to load another Excel spreadsheet.</span></span>  
  
 <span data-ttu-id="1bb46-126">En estas situaciones, el complemento no podrá usarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="1bb46-126">You cannot use the add-in properly in such situations.</span></span> <span data-ttu-id="1bb46-127">Para abrir varias hojas de cálculo de Excel con el complemento BAM habilitado, debe abrir una copia nueva de Excel y cargar la hoja de cálculo en esa instancia de Excel.</span><span class="sxs-lookup"><span data-stu-id="1bb46-127">To open multiple Excel spreadsheets when you have the BAM Add-in enabled, you must open a new copy of Excel and load the spreadsheet into that instance of Excel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bb46-128">Cuando use BAM.xla en Excel, puede obtener el error "este libro ha perdido su proyecto de VBA, los controles de ActiveX y las demás características relacionadas con la programabilidad".</span><span class="sxs-lookup"><span data-stu-id="1bb46-128">When you use BAM.xla in Excel, you may get the error “This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.”</span></span> <span data-ttu-id="1bb46-129">Para obtener más información acerca del error, consulte [solución de problemas de BAM](../core/troubleshooting-bam.md).</span><span class="sxs-lookup"><span data-stu-id="1bb46-129">For more information about the error, see [Troubleshooting BAM](../core/troubleshooting-bam.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1bb46-130">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1bb46-130">In This Section</span></span>  
  
-   [<span data-ttu-id="1bb46-131">Cómo definir una actividad económica</span><span class="sxs-lookup"><span data-stu-id="1bb46-131">How to Define a Business Activity</span></span>](../core/how-to-define-a-business-activity.md)  
  
-   [<span data-ttu-id="1bb46-132">Definir una vista de SAE</span><span class="sxs-lookup"><span data-stu-id="1bb46-132">Defining a BAM View</span></span>](../core/defining-a-bam-view.md)  
  
## <a name="see-also"></a><span data-ttu-id="1bb46-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bb46-133">See Also</span></span>  
 [<span data-ttu-id="1bb46-134">Supervisión de actividades económicas con BAM</span><span class="sxs-lookup"><span data-stu-id="1bb46-134">Monitoring Business Activities with BAM</span></span>](../core/monitoring-business-activities-with-bam.md)