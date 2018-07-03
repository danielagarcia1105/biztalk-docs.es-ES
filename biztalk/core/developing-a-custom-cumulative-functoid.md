---
title: Desarrollar un Functoid acumulado personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ea2c5fa-ed50-4b76-aee9-0d4adf9e6d8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8763f557c5bacb13b3fbc1542216d9eb9be8d319
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008533"
---
# <a name="developing-a-custom-cumulative-functoid"></a><span data-ttu-id="d150f-102">Desarrollar un functoid acumulativo personalizado</span><span class="sxs-lookup"><span data-stu-id="d150f-102">Developing a Custom Cumulative Functoid</span></span>
<span data-ttu-id="d150f-103">Utilice un functoid acumulado personalizado para realizar operaciones de acumulación para los valores que aparecen varias veces en un mensaje de instancia.</span><span class="sxs-lookup"><span data-stu-id="d150f-103">Use a custom cumulative functoid to perform accumulation operations for values that occur multiple times within an instance message.</span></span>  
  
 <span data-ttu-id="d150f-104">Debe implementar tres funciones al desarrollar un functoid acumulativo.</span><span class="sxs-lookup"><span data-stu-id="d150f-104">You must implement three functions when developing a cumulative functoid.</span></span> <span data-ttu-id="d150f-105">Las tres funciones corresponden a las acciones de inicializar, acumular y obtener que la asignación necesita para realizar la acumulación.</span><span class="sxs-lookup"><span data-stu-id="d150f-105">The three functions correspond to the initialize, cumulate, and get actions that the map needs to perform the accumulation.</span></span> <span data-ttu-id="d150f-106">Antes de describir estas funciones, es importante abordar el tema de la seguridad de los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d150f-106">Before discussing these functions it is important to discuss thread safety.</span></span>  
  
## <a name="writing-a-thread-safe-functoid"></a><span data-ttu-id="d150f-107">Escribir un functoid que sea seguro para subprocesos</span><span class="sxs-lookup"><span data-stu-id="d150f-107">Writing a Thread-Safe Functoid</span></span>  
 <span data-ttu-id="d150f-108">El código de un functoid debe ser seguro para subprocesos, ya que se pueden ejecutar simultáneamente varias instancias de una asignación en circunstancias de mucha actividad.</span><span class="sxs-lookup"><span data-stu-id="d150f-108">The functoid code must be thread-safe because under stress conditions multiple instances of a map may be running concurrently.</span></span> <span data-ttu-id="d150f-109">Algunos de los puntos que debe recordar son:</span><span class="sxs-lookup"><span data-stu-id="d150f-109">Some of the points to remember include:</span></span>  
  
- <span data-ttu-id="d150f-110">El estado estático debe ser seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d150f-110">Static state must be thread-safe.</span></span>  
  
- <span data-ttu-id="d150f-111">El estado de la instancia no siempre tiene que ser seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d150f-111">Instance state does not always need to be thread-safe.</span></span>  
  
- <span data-ttu-id="d150f-112">El diseño debe tener en cuenta la ejecución en condiciones de mucha actividad.</span><span class="sxs-lookup"><span data-stu-id="d150f-112">Design with consideration for running under high-stress conditions.</span></span> <span data-ttu-id="d150f-113">Evite los bloqueos en la medida de lo posible.</span><span class="sxs-lookup"><span data-stu-id="d150f-113">Avoid taking locks whenever possible.</span></span>  
  
- <span data-ttu-id="d150f-114">Evite la necesidad de sincronización si es posible.</span><span class="sxs-lookup"><span data-stu-id="d150f-114">Avoid the need for synchronization if possible.</span></span>  
  
  <span data-ttu-id="d150f-115">BizTalk Server proporciona un mecanismo sencillo para reducir la complejidad de escritura de un functoid acumulado que sea seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d150f-115">BizTalk Server provides a simple mechanism to reduce the complexity of writing a thread-safe cumulative functoid.</span></span> <span data-ttu-id="d150f-116">Las tres funciones tienen el mismo primer parámetro, un valor de índice entero.</span><span class="sxs-lookup"><span data-stu-id="d150f-116">All three functions have the same first parameter, an integer index value.</span></span> <span data-ttu-id="d150f-117">BizTalk Server asigna un número único al valor de índice cuando llama a la función de inicialización.</span><span class="sxs-lookup"><span data-stu-id="d150f-117">BizTalk Server assigns a unique number to the index value when it calls your initialization function.</span></span> <span data-ttu-id="d150f-118">Puede usar este valor como un índice en una matriz que almacene los valores acumulados, tal como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="d150f-118">You can use this value as an index into an array that holds accumulating values, as shown in the following code:</span></span>  
  
```  
private HashTable cumulativeArray = new HashTable();  
…  
// Initialization function  
public string InitCumulativeMultiply(int index)  
{  
    cumulativeArray[index] = 1.0;  
    return string.Empty;  
}  
```  
  
 <span data-ttu-id="d150f-119">Este ejemplo utiliza una tabla HashTable en lugar de una lista ArrayList,</span><span class="sxs-lookup"><span data-stu-id="d150f-119">This example uses a HashTable instead of an ArrayList.</span></span> <span data-ttu-id="d150f-120">ya que la función de inicialización no se puede llamar con valores de índice por orden.</span><span class="sxs-lookup"><span data-stu-id="d150f-120">This is because the initialization function might not be called with in-order index values.</span></span>  
  
## <a name="implementing-the-three-cumulative-functions"></a><span data-ttu-id="d150f-121">Implementar las tres funciones acumuladas</span><span class="sxs-lookup"><span data-stu-id="d150f-121">Implementing the Three Cumulative Functions</span></span>  
 <span data-ttu-id="d150f-122">Deberá implementar tres funciones para cada functoid acumulado personalizado que desarrolle.</span><span class="sxs-lookup"><span data-stu-id="d150f-122">You will need to implement three functions for each custom cumulative functoid you develop.</span></span> <span data-ttu-id="d150f-123">En la siguiente tabla se describen las funciones y los métodos que debe llamar en el constructor para establecerlos.</span><span class="sxs-lookup"><span data-stu-id="d150f-123">The functions and the methods you must call in the constructor to set them are summarized in the following table.</span></span> <span data-ttu-id="d150f-124">Todas las funciones devuelven valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="d150f-124">All of the functions return string values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d150f-125">Determine el nombre más adecuado para cada función, pero considere que cada función debe tener el número y el tipo de argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="d150f-125">You determine the best name for each function, but each function must have the number and type of arguments specified.</span></span>  
  
|<span data-ttu-id="d150f-126">Propósito de la función</span><span class="sxs-lookup"><span data-stu-id="d150f-126">Function Purpose</span></span>|<span data-ttu-id="d150f-127">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d150f-127">Arguments</span></span>|<span data-ttu-id="d150f-128">Para establecer una referencia</span><span class="sxs-lookup"><span data-stu-id="d150f-128">To set a reference</span></span>|<span data-ttu-id="d150f-129">Para establecer la secuencia de comandos en línea</span><span class="sxs-lookup"><span data-stu-id="d150f-129">To set inline script</span></span>|  
|----------------------|---------------|------------------------|--------------------------|  
|<span data-ttu-id="d150f-130">Inicialización</span><span class="sxs-lookup"><span data-stu-id="d150f-130">Initialization</span></span>|<span data-ttu-id="d150f-131">**índice de int**</span><span class="sxs-lookup"><span data-stu-id="d150f-131">**int index**</span></span>|<span data-ttu-id="d150f-132">**SetExternalFunctionName**</span><span class="sxs-lookup"><span data-stu-id="d150f-132">**SetExternalFunctionName**</span></span>|<span data-ttu-id="d150f-133">**SetScriptBuffer** con `functionNumber` = 0</span><span class="sxs-lookup"><span data-stu-id="d150f-133">**SetScriptBuffer** with `functionNumber` = 0</span></span>|  
|<span data-ttu-id="d150f-134">Cumulation</span><span class="sxs-lookup"><span data-stu-id="d150f-134">Cumulation</span></span>|<span data-ttu-id="d150f-135">**int index, val, ámbito de la cadena de cadena**</span><span class="sxs-lookup"><span data-stu-id="d150f-135">**int index, string val, string scope**</span></span>|<span data-ttu-id="d150f-136">**SetExternalFunctionName2**</span><span class="sxs-lookup"><span data-stu-id="d150f-136">**SetExternalFunctionName2**</span></span>|<span data-ttu-id="d150f-137">**SetScriptBuffer** con `functionNumber` = 1</span><span class="sxs-lookup"><span data-stu-id="d150f-137">**SetScriptBuffer** with `functionNumber` = 1</span></span>|  
|<span data-ttu-id="d150f-138">Obtener</span><span class="sxs-lookup"><span data-stu-id="d150f-138">Get</span></span>|<span data-ttu-id="d150f-139">**índice de int**</span><span class="sxs-lookup"><span data-stu-id="d150f-139">**int index**</span></span>|<span data-ttu-id="d150f-140">**SetExternalFunctionName3**</span><span class="sxs-lookup"><span data-stu-id="d150f-140">**SetExternalFunctionName3**</span></span>|<span data-ttu-id="d150f-141">**SetScriptBuffer** con `functionNumber` = 2</span><span class="sxs-lookup"><span data-stu-id="d150f-141">**SetScriptBuffer** with `functionNumber` = 2</span></span>|  
  
### <a name="initialization"></a><span data-ttu-id="d150f-142">Inicialización</span><span class="sxs-lookup"><span data-stu-id="d150f-142">Initialization</span></span>  
 <span data-ttu-id="d150f-143">La función initialization le permite preparar los mecanismos que usará para realizar la acumulación.</span><span class="sxs-lookup"><span data-stu-id="d150f-143">Initialization enables you to prepare the mechanisms you will use to perform accumulation.</span></span> <span data-ttu-id="d150f-144">Puede inicializar una matriz, restablecer uno o más valores, o cargar otros recursos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d150f-144">You can initialize an array, reset one or more values, or load other resources as needed.</span></span> <span data-ttu-id="d150f-145">No se utiliza el valor devuelto por la cadena.</span><span class="sxs-lookup"><span data-stu-id="d150f-145">The string return value is not used.</span></span>  
  
### <a name="cumulation"></a><span data-ttu-id="d150f-146">Cumulation</span><span class="sxs-lookup"><span data-stu-id="d150f-146">Cumulation</span></span>  
 <span data-ttu-id="d150f-147">Aquí es donde se realiza la operación de acumulación apropiada para el functoid.</span><span class="sxs-lookup"><span data-stu-id="d150f-147">This is where you perform the accumulation operation appropriate for your functoid.</span></span> <span data-ttu-id="d150f-148">BizTalk Server pasa los tres parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="d150f-148">BizTalk Server passes in the following three parameters:</span></span>  
  
- <span data-ttu-id="d150f-149">**Índice.**</span><span class="sxs-lookup"><span data-stu-id="d150f-149">**Index.**</span></span> <span data-ttu-id="d150f-150">un valor de entero que representa una instancia de asignación.</span><span class="sxs-lookup"><span data-stu-id="d150f-150">An integer value representing a map instance.</span></span> <span data-ttu-id="d150f-151">Puede haber en ejecución varias instancias de asignación a la vez.</span><span class="sxs-lookup"><span data-stu-id="d150f-151">There may be multiple map instances running concurrently.</span></span>  
  
- <span data-ttu-id="d150f-152">**Val.**</span><span class="sxs-lookup"><span data-stu-id="d150f-152">**Val.**</span></span> <span data-ttu-id="d150f-153">una cadena que contiene el valor que se debe acumular.</span><span class="sxs-lookup"><span data-stu-id="d150f-153">A string containing the value that should be accumulated.</span></span> <span data-ttu-id="d150f-154">Será un valor numérico salvo si escribe un functoid acumulado de tipo cadena.</span><span class="sxs-lookup"><span data-stu-id="d150f-154">Unless you are writing a string Cumulate functoid it is a numeric value.</span></span>  
  
- <span data-ttu-id="d150f-155">**Ámbito.**</span><span class="sxs-lookup"><span data-stu-id="d150f-155">**Scope.**</span></span> <span data-ttu-id="d150f-156">una cadena que contiene un número que indica qué valor de atributo o elemento se debe acumular.</span><span class="sxs-lookup"><span data-stu-id="d150f-156">A string containing a number indicating which element or attribute value should be accumulated.</span></span> <span data-ttu-id="d150f-157">Los valores reales se determinan mediante una implementación.</span><span class="sxs-lookup"><span data-stu-id="d150f-157">Actual values are determined by an implementation.</span></span>  
  
  <span data-ttu-id="d150f-158">Decida los valores que se van acumular y los que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="d150f-158">You decide which values to accumulate and which values to ignore.</span></span> <span data-ttu-id="d150f-159">Por ejemplo, puede omitir los valores que no estén por debajo de 0 pero que produzcan una excepción cuando el valor no sea numérico.</span><span class="sxs-lookup"><span data-stu-id="d150f-159">For example, you may ignore values that are not below 0 but throw an exception when a value is not numeric.</span></span> <span data-ttu-id="d150f-160">**BaseFunctoid** proporciona dos funciones:**IsDate** y **IsNumeric**, para ayudar con la validación.</span><span class="sxs-lookup"><span data-stu-id="d150f-160">**BaseFunctoid** supplies two functions—**IsDate** and **IsNumeric**—to assist with validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d150f-161">Si usas **IsDate** o **IsNumeric** en un script en línea, asegúrese de establecer **RequiredGlobalHelperFunctions** para que las funciones están disponibles para el script.</span><span class="sxs-lookup"><span data-stu-id="d150f-161">If you use **IsDate** or **IsNumeric** in an inline script, be sure to set **RequiredGlobalHelperFunctions** so that the functions are made available to your script.</span></span>  
  
 <span data-ttu-id="d150f-162">No se utiliza el valor devuelto por la cadena.</span><span class="sxs-lookup"><span data-stu-id="d150f-162">The string return value is not used.</span></span>  
  
### <a name="get"></a><span data-ttu-id="d150f-163">Obtener</span><span class="sxs-lookup"><span data-stu-id="d150f-163">Get</span></span>  
 <span data-ttu-id="d150f-164">Cuando BizTalk Server termina la iteración de todos los valores determinados por la configuración del functoid en la asignación, solicita el valor acumulado.</span><span class="sxs-lookup"><span data-stu-id="d150f-164">When BizTalk Server finishes iterating through all of the values determined by the functoid settings in the map, it requests the accumulated value.</span></span> <span data-ttu-id="d150f-165">La función get tiene un argumento, `Index`, que es un valor entero que representa una instancia de asignación.</span><span class="sxs-lookup"><span data-stu-id="d150f-165">The get function has one argument, `Index`, which is an integer value representing a map instance.</span></span> <span data-ttu-id="d150f-166">El functoid debe usar el valor Index para buscar y devolver el valor acumulado como una cadena.</span><span class="sxs-lookup"><span data-stu-id="d150f-166">Your function should use the index value to find and return the accumulated value as a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d150f-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d150f-167">Example</span></span>  
 <span data-ttu-id="d150f-168">El siguiente ejemplo ilustra cómo crear un functoid personalizado para realizar multiplicaciones acumuladas.</span><span class="sxs-lookup"><span data-stu-id="d150f-168">The following example illustrates how to create a custom functoid for performing cumulative multiplication.</span></span> <span data-ttu-id="d150f-169">Se basa en un archivo de recursos que contiene tres recursos de cadena y un recurso de mapa de bits de 16 x 16 píxeles.</span><span class="sxs-lookup"><span data-stu-id="d150f-169">It relies on a resource file containing three string resources and a 16x16-pixel bitmap resource.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.BaseFunctoids;  
using System.Reflection;  
using System.Text;  
using System.Collections;  
using System.Globalization;  
  
namespace Microsoft.Samples.BizTalk.CustomFunctoid  
{  
    public class CumulativeMultiplyFunctoid : BaseFunctoid  
    {  
        private ArrayList myCumulativeArray = new ArrayList();  
  
        public CumulativeMultiplyFunctoid() : base()  
        {  
            //ID for this functoid  
            ID = 6001;  
  
            // Resource assembly must be ProjectName.ResourceName if building with VS.Net  
            SetupResourceAssembly("Microsoft.Samples.BizTalk.CustomFunctoid.CustomFunctoidResources", Assembly.GetExecutingAssembly());  
  
            // Pass the resource ID names for functoid name, tooltip  
            // description and the 16x16 bitmap for the Map palette  
            SetName("IDS_CUMULATIVEMULTIPLYFUNCTOID_NAME");  
            SetTooltip("IDS_CUMULATIVEMULTIPLYFUNCTOID_TOOLTIP");  
            SetDescription("IDS_CUMULATIVEMULTIPLYFUNCTOID_DESCRIPTION");  
            SetBitmap("IDB_CUMULATIVEMULTIPLYFUNCTOID_BITMAP");  
  
            // Put this string handling function under the Cumulative  
            // Functoid tab in the Visual Studio toolbox for functoids  
            Category = FunctoidCategory.Cumulative;  
  
            // 2 required parameters, no optional parameters  
            SetMinParams(1);  
            SetMaxParams(2);  
  
            // Functoid accepts three inputs  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
            AddInputConnectionType((~ConnectionType.FunctoidCount) & (~ConnectionType.FunctoidIndex) & (~ConnectionType.FunctoidIteration) & (~ConnectionType.FunctoidCumulative) & (~ConnectionType.FunctoidLooping) & (~ConnectionType.Record));  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
  
            // Set the output connection type  
            OutputConnectionType = ConnectionType.AllExceptRecord;  
  
            // Set the Initialize, Cumulative and Get functions  
            SetExternalFunctionName(GetType().Assembly.FullName, "Microsoft.Samples.BizTalk.CustomFunctoid.CumulativeMultiplyFunctoid", "InitCumulativeMultiply");  
            SetExternalFunctionName2("AddToCumulativeMultiply");  
            SetExternalFunctionName3("GetCumulativeMultiply");  
        }  
  
        // Initialization function  
        public string InitCumulativeMultiply(int index)  
        {  
            if (index >= 0)  
            {  
                if (index >= myCumulativeArray.Count)  
                {  
                    myCumulativeArray.Add(1.0);  
                }  
                else  
                {  
                    myCumulativeArray[index] = 1.0;  
                }  
            }  
  
            return "";  
        }  
  
        // Cumulative function  
        public string AddToCumulativeMultiply(int index, string val, string reserved)  
        {  
            if (index < 0 || index >= myCumulativeArray.Count)  
            {  
                return "";  
            }  
  
            if (IsNumeric(val))  
            {  
                double dval = Convert.ToDouble(val, CultureInfo.InvariantCulture);  
                myCumulativeArray[index] = (double)(myCumulativeArray[index]) * dval;  
            }  
            return myCumulativeArray[index].ToString();  
        }  
  
        // Get Function  
        public string GetCumulativeMultiply(int index)  
        {  
            if (index < 0 || index >= myCumulativeArray.Count)  
            {  
                return "";  
            }  
  
            return myCumulativeArray[index].ToString();  
        }  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="d150f-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="d150f-170">See Also</span></span>  
 <span data-ttu-id="d150f-171">[Uso de BaseFunctoid](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="d150f-171">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 <span data-ttu-id="d150f-172">[Desarrollar un Functoid en línea personalizado](../core/developing-a-custom-inline-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="d150f-172">[Developing a Custom Inline Functoid](../core/developing-a-custom-inline-functoid.md) </span></span>  
 [<span data-ttu-id="d150f-173">Functoid personalizado (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="d150f-173">Custom Functoid (BizTalk Server Sample)</span></span>](../core/custom-functoid-biztalk-server-sample.md)