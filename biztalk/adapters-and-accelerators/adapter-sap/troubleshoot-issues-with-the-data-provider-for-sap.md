---
title: Solucionar problemas relacionados con el proveedor de datos para SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, troubleshooting
- troubleshooting, Data Provider for SAP
ms.assetid: 6fe9baed-0404-4f15-b76e-88cc11c5ff46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba61b75f95fad429c70da42479f22a32fa4e5a65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217988"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-sap"></a><span data-ttu-id="0d2f0-102">Solucionar problemas relacionados con el proveedor de datos para SAP</span><span class="sxs-lookup"><span data-stu-id="0d2f0-102">Troubleshoot Issues with the Data Provider for SAP</span></span>
<span data-ttu-id="0d2f0-103">Esta sección describe el uso de técnicas de solución de problemas para resolver errores de operaciones que pueden surgir al usar [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d2f0-103">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>  
  
##  <a name="BKMK_SAPUnknownParam"></a><span data-ttu-id="0d2f0-104">Error desconocido de parámetro mediante el proveedor de datos para SAP</span><span class="sxs-lookup"><span data-stu-id="0d2f0-104">Unknown Parameter error using the Data Provider for SAP</span></span>  
 <span data-ttu-id="0d2f0-105">**Problema**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-105">**Problem**</span></span>  
  
 <span data-ttu-id="0d2f0-106">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] produce el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="0d2f0-106">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] gives the following error:</span></span>  
  
```  
Microsoft.Data.SAPClient.SAPException: Failed to retrieve data from SAP server --- > Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Unknown Parameter OUT_ZDATATABLE.  
```  
  
 <span data-ttu-id="0d2f0-107">**Causa**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-107">**Cause**</span></span>  
  
 <span data-ttu-id="0d2f0-108">La RFC personalizada, Z_EXTRACT_DATA_OO, instalado en el sistema SAP no es la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-108">The custom RFC, Z_EXTRACT_DATA_OO, installed in your SAP system is not the latest.</span></span> <span data-ttu-id="0d2f0-109">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] usa una RFC personalizada, Z_EXTRACT_DATA_OO, para realizar las operaciones SELECT en la tabla SAP.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-109">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC, Z_EXTRACT_DATA_OO, to perform SELECT operations on the SAP table.</span></span>  
  
 <span data-ttu-id="0d2f0-110">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-110">**Resolution**</span></span>  
  
 <span data-ttu-id="0d2f0-111">Debe actualizar la solicitud de cambio personalizada a la última versión disponible.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-111">You must update the custom RFC to the latest available version.</span></span> <span data-ttu-id="0d2f0-112">Esta RFC, Z_EXTRACT_DATA_OO, está disponible con la adapterpacknoversion.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-112">This RFC, Z_EXTRACT_DATA_OO, is available with the adapterpacknoversion.</span></span> <span data-ttu-id="0d2f0-113">Para obtener más información acerca de cómo instalar y desinstalar la solicitud de cambio personalizada, vea [instalar RFC personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span><span class="sxs-lookup"><span data-stu-id="0d2f0-113">For more information about how to install and uninstall the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
##  <a name="BKMK_SAPOOM"></a><span data-ttu-id="0d2f0-114">Fuera de las excepciones de memoria al seleccionar los datos de una tabla SAP</span><span class="sxs-lookup"><span data-stu-id="0d2f0-114">Out of memory exceptions when selecting data from an SAP table</span></span>  
 <span data-ttu-id="0d2f0-115">**Problema**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-115">**Problem**</span></span>  
  
 <span data-ttu-id="0d2f0-116">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] produce un excepción de memoria insuficiente al seleccionar los datos de un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-116">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] throws an out of memory exception when selecting data from an SAP system.</span></span>  
  
 <span data-ttu-id="0d2f0-117">**Causa**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-117">**Cause**</span></span>  
  
 <span data-ttu-id="0d2f0-118">De forma predeterminada, la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] recupera 10.000 filas a la vez.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-118">By default, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] retrieves 10,000 rows at a time.</span></span> <span data-ttu-id="0d2f0-119">Además, cada lote de filas recuperadas con el sistema SAP se almacena en la memoria.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-119">Also, each batch of rows retrieved from the SAP system is stored in the memory.</span></span> <span data-ttu-id="0d2f0-120">Por lo tanto,</span><span class="sxs-lookup"><span data-stu-id="0d2f0-120">So,</span></span>  
  
-   <span data-ttu-id="0d2f0-121">Si la tabla desde el que se está recuperando datos contiene un gran número de filas, o</span><span class="sxs-lookup"><span data-stu-id="0d2f0-121">If the table from which data is being retrieved contains a large number of rows, or</span></span>  
  
-   <span data-ttu-id="0d2f0-122">Si la tabla contiene columnas de tipos de datos que consumen una cantidad significativa de memoria,</span><span class="sxs-lookup"><span data-stu-id="0d2f0-122">If the table contains columns of data types that consume a significant amount of memory,</span></span>  
  
 <span data-ttu-id="0d2f0-123">El consumo de memoria por el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] aumenta considerablemente y puede provocar un excepción de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-123">The memory consumption by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] increases significantly and may result in an out of memory exception.</span></span>  
  
 <span data-ttu-id="0d2f0-124">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-124">**Resolution**</span></span>  
  
 <span data-ttu-id="0d2f0-125">Puede cambiar el número máximo de filas recuperadas con el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-125">You can change the maximum number of rows retrieved from the SAP system.</span></span> <span data-ttu-id="0d2f0-126">Puede hacerlo mediante la especificación de una opción 'batchsize' con la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-126">You can do so by specifying a 'batchsize' option with the SELECT statement.</span></span> <span data-ttu-id="0d2f0-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0d2f0-127">For example:</span></span>  
  
```  
SELECT * FROM <tablename> OPTION 'batchsize 1000'  
```  
  
 <span data-ttu-id="0d2f0-128">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ahora recupera solo 1000 filas a la vez y, por tanto, no lo consume gran cantidad de memoria.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-128">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] now retrieves only 1000 rows at a time and hence does not consume large amount of memory.</span></span>  
  
##  <a name="BKMK_SAPQueryExcep"></a><span data-ttu-id="0d2f0-129">Excepción al ejecutar una consulta que toma parámetros con valores de fecha</span><span class="sxs-lookup"><span data-stu-id="0d2f0-129">Exception while executing a query that takes parameters with date values</span></span>  
 <span data-ttu-id="0d2f0-130">**Problema**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-130">**Problem**</span></span>  
  
 <span data-ttu-id="0d2f0-131">Obtener la siguiente excepción al ejecutar una consulta mediante el comando EXECQUERY que tiene un parámetro que toma un valor de fecha:</span><span class="sxs-lookup"><span data-stu-id="0d2f0-131">You get the following exception when you execute a query using the EXECQUERY command that has a parameter which takes a date value:</span></span>  
  
```  
ErrorCode=RFC_SYS_EXCEPTION. ErrorGroup=RFC_ERROR_SYSTEM_FAILURE.   
SapErrorMessage=Enter date in the format __.__.____.  
```  
  
 <span data-ttu-id="0d2f0-132">**Causa**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-132">**Cause**</span></span>  
  
 <span data-ttu-id="0d2f0-133">Al ejecutar las consultas que utilizan el comando EXECQUERY, siempre debe especificar valores de fecha en formato AAAAMMDD.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-133">When executing queries using the EXECQUERY command, you must always specify date values in YYYYMMDD format.</span></span>  
  
 <span data-ttu-id="0d2f0-134">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-134">**Resolution**</span></span>  
  
 <span data-ttu-id="0d2f0-135">Asegúrese de que especificar los valores de fecha en formato AAAAMMDD.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-135">Make sure you specify date values in YYYYMMDD format.</span></span> <span data-ttu-id="0d2f0-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0d2f0-136">For example:</span></span>  
  
```  
EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1='20080606'  
```  
  
##  <a name="BKMK_SAPNOVARIANT"></a><span data-ttu-id="0d2f0-137">Excepción de NO_VARIANT ejecutar consultas con el comando EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="0d2f0-137">NO_VARIANT exception executing queries using the EXECQUERY command</span></span>  
 <span data-ttu-id="0d2f0-138">**Problema**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-138">**Problem**</span></span>  
  
 <span data-ttu-id="0d2f0-139">Obtener la siguiente excepción al ejecutar una consulta mediante el comando EXECQUERY:</span><span class="sxs-lookup"><span data-stu-id="0d2f0-139">You get the following exception when you execute a query using the EXECQUERY command:</span></span>  
  
```  
Exception: Details: ErrorCode=RFC_EXCEPTION. ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage=NO_VARIANT.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: <RFC name>  
```  
  
 <span data-ttu-id="0d2f0-140">**Causa**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-140">**Cause**</span></span>  
  
 <span data-ttu-id="0d2f0-141">Puede haber dos causas probables para esta excepción:</span><span class="sxs-lookup"><span data-stu-id="0d2f0-141">There can be two probable causes for this exception:</span></span>  
  
1.  <span data-ttu-id="0d2f0-142">La consulta que está intentando ejecutar tiene variantes definidas en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-142">The query you are trying to execute has variants defined in the SAP system.</span></span> <span data-ttu-id="0d2f0-143">Variantes hacen referencia a un conjunto de criterios de selección que puede especificar al ejecutar una consulta SAP almacenado.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-143">Variants refer to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="0d2f0-144">Por ejemplo, puede usar variantes para especificar valores predeterminados para las consultas.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-144">For example, you can use variants to specify default values for queries.</span></span>  
  
2.  <span data-ttu-id="0d2f0-145">La consulta que está intentando ejecutar ninguna de ellas tiene una variante definida ni espera un valor de parámetro que se pasan.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-145">The query you are trying to execute neither has a variant defined nor it expects a parameter value to be passed.</span></span>  
  
 <span data-ttu-id="0d2f0-146">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="0d2f0-146">**Resolution**</span></span>  
  
1.  <span data-ttu-id="0d2f0-147">Por motivo 1, asegúrese de que especificar el nombre de la variante asociado a la consulta.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-147">For reason 1, make sure you specify the name of the variant associated with the query.</span></span> <span data-ttu-id="0d2f0-148">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0d2f0-148">For example:</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant =  ‘variant1’  
    ```  
  
2.  <span data-ttu-id="0d2f0-149">Por motivo 2, asegúrese de que proporcionar un valor y el nombre del parámetro ficticio al especificar el comando de consulta.</span><span class="sxs-lookup"><span data-stu-id="0d2f0-149">For reason 2, make sure you provide a dummy parameter name and value while specifying the query command.</span></span> <span data-ttu-id="0d2f0-150">Por ejemplo, si "myquery" consulta no requiere ningún parámetro para ejecutar, el comando EXECQUERY debe especificarse como:</span><span class="sxs-lookup"><span data-stu-id="0d2f0-150">For example, if “myquery” query does not require any parameter to execute, the EXECQUERY command must be specified as:</span></span>  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@P1 = 'dummy_value'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0d2f0-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d2f0-151">See Also</span></span>  
[<span data-ttu-id="0d2f0-152">Solucionar problemas del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="0d2f0-152">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)