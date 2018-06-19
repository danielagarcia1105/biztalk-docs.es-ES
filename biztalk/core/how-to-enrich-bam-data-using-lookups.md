---
title: Cómo enriquecer datos de BAM mediante búsquedas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, data lookups
ms.assetid: 8d10659e-97d6-4cd1-9b4d-307afd43c763
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43b42b42158bc3b3c179d624340a97a890072a17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253916"
---
# <a name="how-to-enrich-bam-data-using-lookups"></a><span data-ttu-id="10e8e-102">Cómo enriquecer datos de BAM mediante búsquedas</span><span class="sxs-lookup"><span data-stu-id="10e8e-102">How to Enrich BAM Data Using Lookups</span></span>
<span data-ttu-id="10e8e-103">Hay casos en los que los datos que están disponibles en el tiempo de funcionamiento no contienen todo lo necesario para realizar informes.</span><span class="sxs-lookup"><span data-stu-id="10e8e-103">There are cases in which the data that is available at operation time does not contain everything you need for reporting purposes.</span></span> <span data-ttu-id="10e8e-104">Por ejemplo, puede que se haya instalado un ProductID pero no un ProductName en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="10e8e-104">For example, you may have a ProductID but not a ProductName at runtime.</span></span> <span data-ttu-id="10e8e-105">Ya que la actividad de BAM representa una abstracción independiente de cómo se recopilan los datos realmente, debería contener un elemento con el mismo nombre que los datos finales que desea ver en el “ProductName” del informe.</span><span class="sxs-lookup"><span data-stu-id="10e8e-105">Since the BAM Activity represents an abstraction independent of how the data is actually collected, it should contain an item named as the final data that you want to see in the report "ProductName".</span></span> <span data-ttu-id="10e8e-106">Como el resto de elementos, puede utilizarse en construcciones interpretativas, como grupos de hitos, duraciones, dimensiones y medidas.</span><span class="sxs-lookup"><span data-stu-id="10e8e-106">Just like any other item, you can use this in interpretive constructs such as milestone groups, durations, dimensions, and measures.</span></span> <span data-ttu-id="10e8e-107">Ya que ProductName no está disponible en tiempo de ejecución, debe obtener algunos datos adicionales que sean suficientes para realizar la búsqueda, como el ProductID.</span><span class="sxs-lookup"><span data-stu-id="10e8e-107">Since the ProductName is not available at runtime, you must get some additional data that is sufficient for performing a lookup, such as the ProductID.</span></span>  
  
 <span data-ttu-id="10e8e-108">Debe recopilar los datos de la misma columna, en lugar de los datos que necesita para los informes.</span><span class="sxs-lookup"><span data-stu-id="10e8e-108">You should collect the data in the same column, instead of the data that you need for reports.</span></span> <span data-ttu-id="10e8e-109">Por ejemplo, debe recopilar el ProductID en lugar del ProductName en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="10e8e-109">For example, you should collect the ProductID instead of ProductName at runtime.</span></span> <span data-ttu-id="10e8e-110">Si son necesarias más columnas, deberá crear más elementos en la actividad, pero no utilizarlos en ninguna vista.</span><span class="sxs-lookup"><span data-stu-id="10e8e-110">If more columns are required, you may create more items in the activity but not use them in any View.</span></span>  
  
### <a name="to-enrich-bam-data-via-lookups"></a><span data-ttu-id="10e8e-111">Para enriquecer datos de BAM mediante búsquedas</span><span class="sxs-lookup"><span data-stu-id="10e8e-111">To enrich BAM data via lookups</span></span>  
  
1.  <span data-ttu-id="10e8e-112">Implemente su definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="10e8e-112">Deploy your BAM definition.</span></span>  
  
2.  <span data-ttu-id="10e8e-113">En SQL Server Management Studio, agregue el servidor que contiene los datos de interés como servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="10e8e-113">In SQL Server Management Studio, add the server that contains the data of interest as a remote server.</span></span>  
  
3.  <span data-ttu-id="10e8e-114">Localice el paquete de análisis de datos denominado BAM_AN_`<View Name>`.</span><span class="sxs-lookup"><span data-stu-id="10e8e-114">Locate the data analysis package named BAM_AN_`<View Name>`.</span></span> <span data-ttu-id="10e8e-115">Por ejemplo, si la vista es SalesMgr, será BAM_AN_SalesMgr.</span><span class="sxs-lookup"><span data-stu-id="10e8e-115">For example if the view is SalesMgr, this will be BAM_AN_SalesMgr.</span></span>  
  
4.  <span data-ttu-id="10e8e-116">Aumente el zoom de la vista del paquete (p.ej. 100%).</span><span class="sxs-lookup"><span data-stu-id="10e8e-116">Set the zoom to magnify the view of the package (e.g. 100%)</span></span>  
  
5.  <span data-ttu-id="10e8e-117">Agregue la conexión de SQL que utilizará en las búsquedas.</span><span class="sxs-lookup"><span data-stu-id="10e8e-117">Add a SQL connection that you will be using in the lookups.</span></span>  
  
6.  <span data-ttu-id="10e8e-118">Encuentre la tarea Transformar datos después del paso “Fase de limpieza”.</span><span class="sxs-lookup"><span data-stu-id="10e8e-118">Locate the transform data task after the step "Cleanup Staging".</span></span> <span data-ttu-id="10e8e-119">En este momento se transportan los datos de la base de datos PrimaryImport a la base de datos StarSchema.</span><span class="sxs-lookup"><span data-stu-id="10e8e-119">This is where you move the data from the PrimaryImport to the StarSchema database.</span></span> <span data-ttu-id="10e8e-120">Hay dos instancias de esta tarea: uno para las actividades completadas y otra para la que está en curso.</span><span class="sxs-lookup"><span data-stu-id="10e8e-120">There are two instances of this task—one for the completed activities, and another for the one that is in progress.</span></span> <span data-ttu-id="10e8e-121">Aplique el resto de pasos a las dos tareas.</span><span class="sxs-lookup"><span data-stu-id="10e8e-121">Apply all the rest of the steps to both tasks.</span></span>  
  
7.  <span data-ttu-id="10e8e-122">Haga clic en la transformación.</span><span class="sxs-lookup"><span data-stu-id="10e8e-122">Click the transformation.</span></span>  
  
8.  <span data-ttu-id="10e8e-123">Seleccione Búsquedas y agregue su búsqueda “LookupProductByID” mediante la conexión de búsqueda (consulte Libros en pantalla de SQL Server para búsquedas).</span><span class="sxs-lookup"><span data-stu-id="10e8e-123">Select Lookups; add your lookup "LookupProductByID" using the lookup connection (see SQL books online for lookups).</span></span> <span data-ttu-id="10e8e-124">Por ejemplo, si la búsqueda es una tabla sencilla “LookupProduct”, con columnas ProductID y ProductName, el texto de la búsqueda será:</span><span class="sxs-lookup"><span data-stu-id="10e8e-124">If for example the lookup is a simple table "LookupProduct", the with columns ProductID and ProductName, the text of the lookup will be:</span></span>  
  
    ```  
    SELECT ProductName  
    FROM   LookupProduct  
    WHERE ProductID=?  
    ```  
  
9. <span data-ttu-id="10e8e-125">Haga clic en la pestaña Transformación. Elimine la transformación de datos predeterminada “Transformación”, y cree una transformación ActiveX en su lugar.</span><span class="sxs-lookup"><span data-stu-id="10e8e-125">Click the Transformations tab. Delete the default data transformation "Transform", and create ActiveX transformation instead.</span></span> <span data-ttu-id="10e8e-126">Haga clic en Columnas de origen y agregue todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="10e8e-126">Click Source Columns and add all columns.</span></span> <span data-ttu-id="10e8e-127">Haga clic en Columnas de destino y agregue todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="10e8e-127">Click Destination Columns and add all columns.</span></span>  
  
10. <span data-ttu-id="10e8e-128">Haga clic en la pestaña General y, a continuación, en Propiedades.</span><span class="sxs-lookup"><span data-stu-id="10e8e-128">Click the General tab, and then Properties.</span></span> <span data-ttu-id="10e8e-129">Esto da lugar a la generación automática de una secuencia de comandos que realiza una transformación trivial de la copia, tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="10e8e-129">This results in automatic generation of a script that performs the trivial copy transformation as shown:</span></span>  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("ProductName") = DTSSource("ProductName")  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
11. <span data-ttu-id="10e8e-130">Cambie el valor mediante la búsqueda, tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="10e8e-130">Change the value by using the lookup as shown:</span></span>  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("Product")= _  
                      DTSLookups( "LookupProductByID" ).Execute(  _                                  DTSSource("Product"))  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
12. <span data-ttu-id="10e8e-131">Guarde y ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="10e8e-131">Save and then run the package.</span></span>  
  
13. <span data-ttu-id="10e8e-132">Asegúrese de que el cubo OLAP recibe los datos apropiados.</span><span class="sxs-lookup"><span data-stu-id="10e8e-132">Ensure that the correct data ends up in the OLAP cube.</span></span> <span data-ttu-id="10e8e-133">Debería guardar el paquete como VBScript o archivo de almacenamiento estructurado, ya que contiene su código personalizado, no solo el que se generó automáticamente desde BAM.</span><span class="sxs-lookup"><span data-stu-id="10e8e-133">You should save the package as VBScript or a structured storage file, because it contains your custom code, not just the auto-generated steps from BAM.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10e8e-134">La búsqueda solo funciona para los informes programados que se realizan con DTS y OLAP.</span><span class="sxs-lookup"><span data-stu-id="10e8e-134">The lookup works only for the scheduled reports that you perform with DTS and OLAP.</span></span> <span data-ttu-id="10e8e-135">Si necesita datos diferentes de los que recopiló en la agregación en tiempo real, recupere los datos antes de llamar a la API de BAM.</span><span class="sxs-lookup"><span data-stu-id="10e8e-135">If you need different data than what is collected in the real-time aggregation, then you must retrieve the data before calling the BAM API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e8e-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="10e8e-136">See Also</span></span>  
 <span data-ttu-id="10e8e-137">[Uso de la actividad económica de supervisión](../core/using-business-activity-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="10e8e-137">[Using Business Activity Monitoring](../core/using-business-activity-monitoring.md) </span></span>  
 [<span data-ttu-id="10e8e-138">Implementar archivos XML de BAM localizados</span><span class="sxs-lookup"><span data-stu-id="10e8e-138">Deploying Localized BAM XML Files</span></span>](../core/deploying-localized-bam-xml-files.md)