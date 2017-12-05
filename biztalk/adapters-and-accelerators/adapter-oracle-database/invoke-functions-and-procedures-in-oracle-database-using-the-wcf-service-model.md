---
title: Invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, invoke functions and procedures using the WCF service model
- WCF service model, invoking functions and procedures
ms.assetid: 806fc803-3640-42d6-bdf9-53b08f9c7c50
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f1fac59fc77b0cf52abe789db8feb2305043708
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="57266-102">Invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="57266-102">Invoke Functions and Procedures in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="57266-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] superficies de procedimientos, funciones y paquetes como operaciones.</span><span class="sxs-lookup"><span data-stu-id="57266-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces procedures, functions, and packages as operations.</span></span> <span data-ttu-id="57266-104">En el modelo de servicio WCF estas operaciones se representan como métodos en un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="57266-104">In the WCF service model these operations are represented as methods on a WCF client.</span></span> <span data-ttu-id="57266-105">El modelo de servicio WCF y [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="57266-105">The WCF service model and the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span></span>  
  
-   <span data-ttu-id="57266-106">**Admite las funciones**.</span><span class="sxs-lookup"><span data-stu-id="57266-106">**Support functions**.</span></span> <span data-ttu-id="57266-107">El valor devuelto de la función de Oracle aparece como el valor devuelto del método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="57266-107">The RETURN value of the Oracle function is surfaced as the return value of the WCF client method.</span></span> <span data-ttu-id="57266-108">Parámetros de Oracle aparecen como parámetros (con la dirección adecuada según se define a continuación) para el método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="57266-108">Oracle parameters are surfaced as parameters (with the appropriate direction as defined below) to the WCF client method.</span></span>  
  
-   <span data-ttu-id="57266-109">**Compatible con los procedimientos**.</span><span class="sxs-lookup"><span data-stu-id="57266-109">**Support procedures**.</span></span> <span data-ttu-id="57266-110">El primer parámetro del procedimiento de Oracle de salida aparece como el valor devuelto del método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="57266-110">The first OUT parameter of the Oracle procedure is surfaced as the return value of the WCF client method.</span></span> <span data-ttu-id="57266-111">Todos los demás parámetros de Oracle aparecen como parámetros (con la dirección adecuada según se define a continuación) para el método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="57266-111">All other Oracle parameters are surfaced as parameters (with the appropriate direction as defined below) to the WCF client method.</span></span>  
  
-   <span data-ttu-id="57266-112">**Admite los paquetes de Oracle**.</span><span class="sxs-lookup"><span data-stu-id="57266-112">**Support Oracle packages**.</span></span> <span data-ttu-id="57266-113">El nombre de la operación y el espacio de nombres de sus tipos de parámetro se califican con el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="57266-113">The name of the operation and the namespace of its parameter types are qualified by the package name.</span></span>  
  
-   <span data-ttu-id="57266-114">**Compatibilidad con sobrecarga funciones y procedimientos**.</span><span class="sxs-lookup"><span data-stu-id="57266-114">**Support overloaded functions and procedures**.</span></span>  
  
-   <span data-ttu-id="57266-115">**Compatibilidad con IN, OUT e IN parámetros para los tipos de datos de Oracle básicos para los procedimientos y funciones**.</span><span class="sxs-lookup"><span data-stu-id="57266-115">**Support IN, OUT and IN OUT parameters for basic Oracle data types for both procedures and functions**.</span></span> <span data-ttu-id="57266-116">Los parámetros de salida aparecen como **out** aparecen como parámetros en el método de cliente WCF y los parámetros OUT en **ref** parámetros.</span><span class="sxs-lookup"><span data-stu-id="57266-116">OUT parameters are surfaced as **out** parameters on the WCF client method and IN OUT parameters are surfaced as **ref** parameters.</span></span>  
  
-   <span data-ttu-id="57266-117">**IN de soporte técnico, OUT e IN parámetros REF CURSOR procedimientos y funciones, así como valores devueltos de función**.</span><span class="sxs-lookup"><span data-stu-id="57266-117">**Support IN, OUT, and IN OUT REF CURSOR parameters for procedures and functions, as well as function RETURN values**.</span></span> <span data-ttu-id="57266-118">Para obtener más información, consulte [realizar operaciones utilizando los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="57266-118">For more information, see [Performing Operations Using REF CURSORS in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="57266-119">**Admite en, en espera registro a con parámetros para los procedimientos y funciones de tipo, así como valores devueltos de función**.</span><span class="sxs-lookup"><span data-stu-id="57266-119">**Support IN, OUT, and IN OUT RECORD type parameters for procedures and functions, as well as function RETURN values**.</span></span> <span data-ttu-id="57266-120">Para obtener más información, consulte [realizar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="57266-120">For more information, see [Performing Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="57266-121">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="57266-121">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="57266-122">Los ejemplos de este tema se usa el /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT sobrecargar el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="57266-122">The examples in this topic use the /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT overloaded procedure.</span></span> <span data-ttu-id="57266-123">Este procedimiento lee un registro de la tabla de SCOTT/cuenta basada en un identificador de cuenta o un nombre de cuenta.</span><span class="sxs-lookup"><span data-stu-id="57266-123">This procedure reads a record from the SCOTT/ACCOUNT table based on either an account ID or an account name.</span></span> <span data-ttu-id="57266-124">Una secuencia de comandos para generar este procedimiento y la tabla se suministra con los ejemplos del SDK.</span><span class="sxs-lookup"><span data-stu-id="57266-124">A script to generate this procedure and table is supplied with the SDK samples.</span></span> <span data-ttu-id="57266-125">Para obtener más información acerca de los ejemplos SDK, vea [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="57266-125">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="57266-126">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="57266-126">The WCF Client Class</span></span>  
 <span data-ttu-id="57266-127">En la tabla siguiente se muestra el nombre del cliente WCF y el método generado para los procedimientos, las funciones y los paquetes que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies.</span><span class="sxs-lookup"><span data-stu-id="57266-127">The following table shows the name of the WCF client and the method generated for procedures, functions and packages that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces.</span></span> <span data-ttu-id="57266-128">A menos que una función o procedimiento está sobrecargado, se utiliza un solo cliente WCF para invocar todas las funciones en un esquema, todos los procedimientos en un esquema, o todas las funciones y procedimientos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="57266-128">Unless a function or procedure is overloaded, a single WCF client is used to invoke all of the functions in a schema, all of the procedures in a schema, or all of the functions and procedures in a package.</span></span>  
  
|<span data-ttu-id="57266-129">Artefacto de Oracle</span><span class="sxs-lookup"><span data-stu-id="57266-129">Oracle Artifact</span></span>|<span data-ttu-id="57266-130">Nombre de operación de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="57266-130">WCF Client Operation Name</span></span>|<span data-ttu-id="57266-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57266-131">Example</span></span>|  
|---------------------|-------------------------------|-------------|  
|<span data-ttu-id="57266-132">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="57266-132">Procedure</span></span>|<span data-ttu-id="57266-133">[ESQUEMA] ProcedureClient. [PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="57266-133">[SCHEMA]ProcedureClient.[PROC_NAME]</span></span>|<span data-ttu-id="57266-134">SCOTTProcedureClient.MYPROC</span><span class="sxs-lookup"><span data-stu-id="57266-134">SCOTTProcedureClient.MYPROC</span></span>|  
|<span data-ttu-id="57266-135">Función</span><span class="sxs-lookup"><span data-stu-id="57266-135">Function</span></span>|<span data-ttu-id="57266-136">[ESQUEMA] FunctionClient. [FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="57266-136">[SCHEMA]FunctionClient.[FUNC_NAME]</span></span>|<span data-ttu-id="57266-137">SCOTTProcedureClient.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="57266-137">SCOTTProcedureClient.MYFUNC</span></span>|  
|<span data-ttu-id="57266-138">Paquete (procedimiento o función)</span><span class="sxs-lookup"><span data-stu-id="57266-138">Package (procedure or function)</span></span>|<span data-ttu-id="57266-139">[ESQUEMA] Cliente de paquete [nombreDePaquete]. [PROC_NAME o FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="57266-139">[SCHEMA]Package[PACKAGE_NAME]Client.[PROC_NAME or FUNC_NAME]</span></span>|<span data-ttu-id="57266-140">SCOTTPackageMYPACKAGEClient.MYPROC</span><span class="sxs-lookup"><span data-stu-id="57266-140">SCOTTPackageMYPACKAGEClient.MYPROC</span></span>|  
  
 <span data-ttu-id="57266-141">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="57266-141">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="57266-142">[PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo, MYPROC.</span><span class="sxs-lookup"><span data-stu-id="57266-142">[PROC_NAME] = The name of an Oracle procedure; for example, MYPROC.</span></span>  
  
 <span data-ttu-id="57266-143">[FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.</span><span class="sxs-lookup"><span data-stu-id="57266-143">[FUNC_NAME] = The name of an Oracle function; for example, MYFUNC.</span></span>  
  
 <span data-ttu-id="57266-144">[NombreDePaquete] = el nombre de un paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="57266-144">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="57266-145">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] representa el registro de Oracle parámetros de tipo y devolver valores, así como los conjuntos de resultados devueltos por parámetros REF CURSOR como tipos XML complejos que contienen los datos de las filas (o campos) de un registro de Oracle.</span><span class="sxs-lookup"><span data-stu-id="57266-145">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents Oracle RECORD type parameters and return values as well as the result sets returned by REF CURSOR parameters as complex XML types that contain the row data (or fields) of an Oracle record.</span></span> <span data-ttu-id="57266-146">En el modelo de servicio WCF, cada uno de estos tipos XML se representa como una clase. NET; las propiedades de la clase representan los campos del tipo de registro o del conjunto de resultados de REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="57266-146">In the WCF service model, each of these XML types is represented as a .NET class; the properties of the class represent the fields of the RECORD type or REF CURSOR result set.</span></span> <span data-ttu-id="57266-147">Tipos de registros de Oracle siempre se representan como clases .NET fuertemente tipadas.</span><span class="sxs-lookup"><span data-stu-id="57266-147">Oracle RECORD types are always represented as strongly-typed .NET classes.</span></span> <span data-ttu-id="57266-148">Sin embargo, un conjunto de resultados de REF CURSOR, se puede representar como registros fuertemente tipado o débilmente tipada en función de si se declara el REF CURSOR propio como fuertemente tipados o débilmente tipada.</span><span class="sxs-lookup"><span data-stu-id="57266-148">A REF CURSOR result set, however, can be represented as either strongly-typed or weakly-typed records based on whether the REF CURSOR itself is declared as strongly-typed or weakly-typed.</span></span> <span data-ttu-id="57266-149">Las clases que representan REF CURSOR o registro tipo parámetros (o valores devueltos) se generan en un único espacio de nombres basado en el procedimiento, la función o el paquete.</span><span class="sxs-lookup"><span data-stu-id="57266-149">The classes that represent REF CURSOR or RECORD type parameters (or return values) are generated in a unique namespace based on the procedure, function, or package.</span></span> <span data-ttu-id="57266-150">La tabla siguiente muestran estos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="57266-150">The following table shows these namespaces.</span></span>  
  
|<span data-ttu-id="57266-151">Artefacto de Oracle</span><span class="sxs-lookup"><span data-stu-id="57266-151">Oracle Artifact</span></span>|<span data-ttu-id="57266-152">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="57266-152">Namespace</span></span>|<span data-ttu-id="57266-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57266-153">Example</span></span>|  
|---------------------|---------------|-------------|  
|<span data-ttu-id="57266-154">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="57266-154">Procedure</span></span>|<span data-ttu-id="57266-155">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="57266-155">[BASE_NS].</span></span> <span data-ttu-id="57266-156">[ESQUEMA]. Procedimiento. [PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="57266-156">[SCHEMA].Procedure.[PROC_NAME]</span></span>|<span data-ttu-id="57266-157">Microsoft.lobservices.OracleDB._2007._03.Scott. Procedure.MYPROC</span><span class="sxs-lookup"><span data-stu-id="57266-157">microsoft.lobservices.oracledb._2007._03.SCOTT.Procedure.MYPROC</span></span>|  
|<span data-ttu-id="57266-158">Función</span><span class="sxs-lookup"><span data-stu-id="57266-158">Function</span></span>|<span data-ttu-id="57266-159">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="57266-159">[BASE_NS].</span></span> <span data-ttu-id="57266-160">[ESQUEMA]. Función. [FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="57266-160">[SCHEMA].Function.[FUNC_NAME]</span></span>|<span data-ttu-id="57266-161">Microsoft.lobservices.OracleDB._2007._03.Scott. Function.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="57266-161">microsoft.lobservices.oracledb._2007._03.SCOTT.Function.MYFUNC</span></span>|  
|<span data-ttu-id="57266-162">Paquete (procedimiento)</span><span class="sxs-lookup"><span data-stu-id="57266-162">Package (Procedure)</span></span>|<span data-ttu-id="57266-163">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="57266-163">[BASE_NS].</span></span> <span data-ttu-id="57266-164">[ESQUEMA]. Paquete. [NOMBREDEPAQUETE]. [PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="57266-164">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME]</span></span>|<span data-ttu-id="57266-165">Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYPROC</span><span class="sxs-lookup"><span data-stu-id="57266-165">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC</span></span>|  
|<span data-ttu-id="57266-166">Paquete (función)</span><span class="sxs-lookup"><span data-stu-id="57266-166">Package (Function)</span></span>|<span data-ttu-id="57266-167">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="57266-167">[BASE_NS].</span></span> <span data-ttu-id="57266-168">[ESQUEMA]. Paquete. [NOMBREDEPAQUETE]. [FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="57266-168">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME]</span></span>|<span data-ttu-id="57266-169">Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="57266-169">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC</span></span>|  
|<span data-ttu-id="57266-170">Conjunto de registros genérico (débilmente tipada)</span><span class="sxs-lookup"><span data-stu-id="57266-170">Generic Record Set (weakly-typed)</span></span>|<span data-ttu-id="57266-171">[BASE_NS]</span><span class="sxs-lookup"><span data-stu-id="57266-171">[BASE_NS]</span></span>|<span data-ttu-id="57266-172">Microsoft.lobservices.OracleDB._2007._03</span><span class="sxs-lookup"><span data-stu-id="57266-172">microsoft.lobservices.oracledb._2007._03</span></span>|  
  
 <span data-ttu-id="57266-173">[BASE_NS] = el espacio de nombres de adaptador base; Microsoft.lobservices.OracleDB._2007._03.</span><span class="sxs-lookup"><span data-stu-id="57266-173">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span></span>  
  
 <span data-ttu-id="57266-174">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="57266-174">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="57266-175">[PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo, MYPROC.</span><span class="sxs-lookup"><span data-stu-id="57266-175">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="57266-176">[FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.</span><span class="sxs-lookup"><span data-stu-id="57266-176">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="57266-177">[NombreDePaquete] = el nombre de un paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="57266-177">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="57266-178">Para obtener información sobre cómo se utilizan estos espacios de nombres para los parámetros de registro, consulte [realizar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="57266-178">For information about how these namespaces are used for RECORD parameters, see [Performing Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span> <span data-ttu-id="57266-179">Para obtener información sobre cómo se utilizan estos espacios de nombres para los parámetros REF CURSOR, vea [realizar operaciones utilizando los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="57266-179">For information about how these namespaces are used for REF CURSOR parameters, see [Performing Operations Using REF CURSORS in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="57266-180">En general, los parámetros de Oracle y los valores devueltos se asignan como se indica a continuación en el método de cliente WCF:</span><span class="sxs-lookup"><span data-stu-id="57266-180">In general, the Oracle parameters and return values are mapped as follows in the WCF client method:</span></span>  
  
-   <span data-ttu-id="57266-181">Parámetros IN de Oracle se asignan a parámetros de (entrada). NET.</span><span class="sxs-lookup"><span data-stu-id="57266-181">Oracle IN parameters are mapped to .NET (input) parameters.</span></span>  
  
-   <span data-ttu-id="57266-182">Los parámetros OUT de Oracle se asignan a .NET **out** parámetros.</span><span class="sxs-lookup"><span data-stu-id="57266-182">Oracle OUT parameters are mapped to .NET **out** parameters.</span></span>  
  
-   <span data-ttu-id="57266-183">Oracle en los parámetros se asignan a .NET **ref** parámetros.</span><span class="sxs-lookup"><span data-stu-id="57266-183">Oracle IN OUT parameters are mapped to .NET **ref** parameters.</span></span>  
  
-   <span data-ttu-id="57266-184">Se asignan los valores devueltos de función para el valor devuelto del método.</span><span class="sxs-lookup"><span data-stu-id="57266-184">Function RETURN values are mapped to the method return value.</span></span>  
  
 <span data-ttu-id="57266-185">Sin embargo, existen dos excepciones importantes:</span><span class="sxs-lookup"><span data-stu-id="57266-185">However, two important exceptions exist:</span></span>  
  
-   <span data-ttu-id="57266-186">Parámetros en espera REF CURSOR de Oracle se dividen en una cadena de entrada y salida (**out**) grabar conjunto.</span><span class="sxs-lookup"><span data-stu-id="57266-186">Oracle IN OUT REF CURSOR parameters are split into an input string and an output (**out**) record set.</span></span> <span data-ttu-id="57266-187">Esto es porque el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] representa parámetros IN REF CUSROR como cadenas y parámetros de salida de REF CURSOR como tipos complejos (conjuntos de registros), estos no se pueden combinar en un único parámetro.</span><span class="sxs-lookup"><span data-stu-id="57266-187">This is because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents IN REF CUSROR parameters as strings and OUT REF CURSOR parameters as complex types (record sets), these cannot be combined into a single parameter.</span></span>  
  
-   <span data-ttu-id="57266-188">El primer parámetro en un procedimiento de Oracle de salida se asigna al valor devuelto del método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="57266-188">The first OUT parameter in an Oracle procedure is mapped to the return value of the WCF client method.</span></span> <span data-ttu-id="57266-189">Este es el comportamiento estándar de WCF.</span><span class="sxs-lookup"><span data-stu-id="57266-189">This is standard WCF behavior.</span></span>  
  
 <span data-ttu-id="57266-190">En el ejemplo siguiente se muestra parte de un procedimiento simple de Oracle (cargado en el esquema SCOTT) y la firma del método de cliente WCF que se genera para invocarlo.</span><span class="sxs-lookup"><span data-stu-id="57266-190">The following example shows part of a simple Oracle procedure (loaded in the SCOTT schema) and the signature of the WCF client method that is generated to invoke it.</span></span> <span data-ttu-id="57266-191">El procedimiento de Oracle tiene tres parámetros, tres parámetros IN OUT y tres parámetros OUT Sin embargo, el método de cliente WCF no asigna un parámetro para el primer parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="57266-191">The Oracle procedure has three IN parameters, three IN OUT parameters, and three OUT parameters; however, the WCF client method does not map a parameter for the first OUT parameter.</span></span> <span data-ttu-id="57266-192">En su lugar se asigna para el valor devuelto del método.</span><span class="sxs-lookup"><span data-stu-id="57266-192">Instead it is mapped to the method return value.</span></span>  
  
```  
CREATE or REPLACE PROCEDURE Sample_Procedure   
    (  
     INNUMBER      IN         NUMBER,  
     INVARCHAR     IN         VARCHAR2,  
     INDATE        IN         DATE,  
     INOUTNUMBER   IN OUT     NUMBER,  
     INOUTVARCHAR  IN OUT     VARCHAR,  
     INOUTDATE     IN OUT     DATE,  
     OUTNUMBER     OUT        NUMBER,  
     OUTVARCHAR    OUT        VARCHAR2,  
     OUTDATE       OUT        DATE  
    ) AS   
    BEGIN  
  
        ...  
  
    END;  
    /  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTProcedureClient : System.ServiceModel.ClientBase<SCOTTProcedure>, SCOTTProcedure {  
  
    public System.Nullable<decimal> SAMPLE_PROCEDURE  
       (  
        System.Nullable<decimal> INNUMBER,   
        string INVARCHAR,   
        System.Nullable\<System.DateTime\> INDATE,   
        ref System.Nullable<decimal> INOUTNUMBER,   
        ref string INOUTVARCHAR,   
        ref System.Nullable\<System.DateTime\> INOUTDATE,   
        out string OUTVARCHAR,   
        out System.Nullable\<System.DateTime\> OUTDATE  
        );  
}  
```  
  
### <a name="support-for-overloaded-procedures-functions-and-packages"></a><span data-ttu-id="57266-193">Compatibilidad con procedimientos sobrecargados, funciones y paquetes</span><span class="sxs-lookup"><span data-stu-id="57266-193">Support for Overloaded Procedures, Functions and Packages</span></span>  
 <span data-ttu-id="57266-194">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite sobrecarga procedimientos, funciones y paquetes anexando una cadena única para el identificador de nodo y el espacio de nombres que se pone de manifiesto para cada artefacto sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="57266-194">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports overloaded procedures, functions, and packages by appending a unique string to the node ID and the namespace that it surfaces for each overloaded artifact.</span></span> <span data-ttu-id="57266-195">Esta cadena es "overload1" para la primera sobrecarga, "overload2" para la siguiente sobrecarga y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="57266-195">This string is "overload1" for the first overload, "overload2" for the next overload, and so on.</span></span>  
  
 <span data-ttu-id="57266-196">En el modelo de servicio WCF cada función o procedimiento sobrecargado se representa mediante un único cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="57266-196">In the WCF service model each overloaded procedure or function is represented by a unique WCF client.</span></span> <span data-ttu-id="57266-197">Esto es diferente del caso no sobrecargar en que todos los de las funciones en un esquema, todos los procedimientos en un esquema, o todos los procedimientos y funciones en un paquete se invocan el mismo cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="57266-197">This is different from the non-overloaded case in which all of the functions in a SCHEMA, all of the procedures in a SCHEMA, or all of the procedures and functions in a PACKAGE are invoked by the same WCF client.</span></span> <span data-ttu-id="57266-198">En la tabla siguiente muestra al cliente de WCF nombre y el método generada para procedimientos sobrecargados, funciones y paquetes.</span><span class="sxs-lookup"><span data-stu-id="57266-198">The following table shows the WCF client name and method generated for overloaded procedures, functions, and packages.</span></span>  
  
|<span data-ttu-id="57266-199">Artefacto de Oracle</span><span class="sxs-lookup"><span data-stu-id="57266-199">Oracle Artifact</span></span>|<span data-ttu-id="57266-200">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="57266-200">WCF Client Name</span></span>|<span data-ttu-id="57266-201">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57266-201">Example</span></span>|  
|---------------------|---------------------|-------------|  
|<span data-ttu-id="57266-202">Paquete sobrecargado (procedimiento)</span><span class="sxs-lookup"><span data-stu-id="57266-202">Overloaded Package (Procedure)</span></span>|<span data-ttu-id="57266-203">[ESQUEMA] Empaquetar [nombreDePaquete] [PROC_NAME]] [OVERLOAD_ID] cliente. [PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="57266-203">[SCHEMA]Package[PACKAGE_NAME][PROC_NAME] ][OVERLOAD_ID]Client.[PROC_NAME]</span></span>|<span data-ttu-id="57266-204">SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC</span><span class="sxs-lookup"><span data-stu-id="57266-204">SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC</span></span>|  
|<span data-ttu-id="57266-205">Paquete sobrecargado (función)</span><span class="sxs-lookup"><span data-stu-id="57266-205">Overloaded Package (Function)</span></span>|<span data-ttu-id="57266-206">[ESQUEMA] Empaquetar [nombreDePaquete] [FUNC_NAME]] [OVERLOAD_ID] cliente. [FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="57266-206">[SCHEMA]Package[PACKAGE_NAME][FUNC_NAME] ][OVERLOAD_ID]Client.[FUNC_NAME]</span></span>|<span data-ttu-id="57266-207">SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="57266-207">SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC</span></span>|  
  
 <span data-ttu-id="57266-208">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="57266-208">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="57266-209">[PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo, MYPROC.</span><span class="sxs-lookup"><span data-stu-id="57266-209">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="57266-210">[FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.</span><span class="sxs-lookup"><span data-stu-id="57266-210">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="57266-211">[NombreDePaquete] = el nombre de un paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="57266-211">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="57266-212">[OVERLOAD_ID] = cadena única que identifica el artefacto sobrecargado; "overload1", "overload2" y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="57266-212">[OVERLOAD_ID] = The unique string that identifies the overloaded artifact; "overload1", "overload2", and so on.</span></span>  
  
 <span data-ttu-id="57266-213">En la tabla siguiente se muestra el espacio de nombres que se genera para procedimientos sobrecargados, funciones y paquetes.</span><span class="sxs-lookup"><span data-stu-id="57266-213">The following table shows the namespace generated for overloaded procedures, functions, and packages.</span></span>  
  
|<span data-ttu-id="57266-214">Artefacto de Oracle</span><span class="sxs-lookup"><span data-stu-id="57266-214">Oracle Artifact</span></span>|<span data-ttu-id="57266-215">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="57266-215">Namespace</span></span>|<span data-ttu-id="57266-216">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57266-216">Example</span></span>|  
|---------------------|---------------|-------------|  
|<span data-ttu-id="57266-217">Paquete (procedimiento)</span><span class="sxs-lookup"><span data-stu-id="57266-217">Package (Procedure)</span></span>|<span data-ttu-id="57266-218">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="57266-218">[BASE_NS].</span></span> <span data-ttu-id="57266-219">[ESQUEMA]. Paquete. [NOMBREDEPAQUETE]. [PROC_NAME] [OVERLOAD_ID]</span><span class="sxs-lookup"><span data-stu-id="57266-219">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME] [OVERLOAD_ID]</span></span>|<span data-ttu-id="57266-220">Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYPROC.overload1</span><span class="sxs-lookup"><span data-stu-id="57266-220">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC.overload1</span></span>|  
|<span data-ttu-id="57266-221">Paquete (función)</span><span class="sxs-lookup"><span data-stu-id="57266-221">Package (Function)</span></span>|<span data-ttu-id="57266-222">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="57266-222">[BASE_NS].</span></span> <span data-ttu-id="57266-223">[ESQUEMA]. Paquete. [NOMBREDEPAQUETE]. [FUNC_NAME]. [OVERLOAD_ID]</span><span class="sxs-lookup"><span data-stu-id="57266-223">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME].[OVERLOAD_ID]</span></span>|<span data-ttu-id="57266-224">Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYFUNC.overload1</span><span class="sxs-lookup"><span data-stu-id="57266-224">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC.overload1</span></span>|  
|<span data-ttu-id="57266-225">Conjunto de registros genérico (débilmente tipada)</span><span class="sxs-lookup"><span data-stu-id="57266-225">Generic Record Set (weakly-typed)</span></span>|<span data-ttu-id="57266-226">[BASE_NS]</span><span class="sxs-lookup"><span data-stu-id="57266-226">[BASE_NS]</span></span>|<span data-ttu-id="57266-227">Microsoft.lobservices.OracleDB._2007._03</span><span class="sxs-lookup"><span data-stu-id="57266-227">microsoft.lobservices.oracledb._2007._03</span></span>|  
  
 <span data-ttu-id="57266-228">[BASE_NS] = el espacio de nombres de adaptador base; Microsoft.lobservices.OracleDB._2007._03.</span><span class="sxs-lookup"><span data-stu-id="57266-228">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span></span>  
  
 <span data-ttu-id="57266-229">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="57266-229">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="57266-230">[PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo, MYPROC.</span><span class="sxs-lookup"><span data-stu-id="57266-230">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="57266-231">[FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.</span><span class="sxs-lookup"><span data-stu-id="57266-231">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="57266-232">[NombreDePaquete] = el nombre de un paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="57266-232">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="57266-233">[OVERLOAD_ID] = cadena única que identifica el artefacto sobrecargado; "overload1", "overload2" y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="57266-233">[OVERLOAD_ID] = The unique string that identifies the overloaded artifact; "overload1", "overload2", and so on.</span></span> <span data-ttu-id="57266-234">El valor numérico en la cadena es el identificador de la sobrecarga del artefacto mantenida por la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="57266-234">The numeric value in the string is the overload ID for the artifact maintained by the Oracle database.</span></span>  
  
 <span data-ttu-id="57266-235">En el ejemplo siguiente se muestra los clientes de WCF y las firmas de método generadas para el procedimiento GET_ACCOUNT sobrecargado en el paquete ACCOUNT_PKG.</span><span class="sxs-lookup"><span data-stu-id="57266-235">The following example shows the WCF clients and the method signatures generated for the overloaded GET_ACCOUNT procedure in the ACCOUNT_PKG package.</span></span> <span data-ttu-id="57266-236">(Las declaraciones de Oracle se incluyen). Este ejemplo muestra cómo se genera un único cliente WCF para cada sobrecarga y cómo el método generado para cada cliente devuelve un conjunto de registros de un espacio de nombres único.</span><span class="sxs-lookup"><span data-stu-id="57266-236">(The Oracle declarations are included.) This example shows how a unique WCF client is generated for each overload and how the method generated for each client returns a record set in a unique namespace.</span></span>  
  
```  
/* Procedure that takes account ID and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aid IN account.acctid%TYPE, acct OUT account%ROWTYPE) ;  
  
/* Procedure that takes account name and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aname IN account.name%TYPE, acct OUT account%ROWTYPE) ;  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1.ACCTRECORD GET_ACCOUNT(System.Nullable<decimal> AID);  
}  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2.ACCTRECORD GET_ACCOUNT(string ANAME);  
}  
```  
  
## <a name="invoking-functions-and-procedures"></a><span data-ttu-id="57266-237">Invocar funciones y procedimientos</span><span class="sxs-lookup"><span data-stu-id="57266-237">Invoking Functions and Procedures</span></span>  
 <span data-ttu-id="57266-238">Para invocar una función o un procedimiento con un cliente WCF, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="57266-238">To invoke a function or a procedure by using a WCF client, perform the following steps.</span></span>  
  
1.  <span data-ttu-id="57266-239">Generar una clase de cliente WCF para la función de destino, el procedimiento o el paquete.</span><span class="sxs-lookup"><span data-stu-id="57266-239">Generate a WCF client class for the target function, procedure, or package.</span></span> <span data-ttu-id="57266-240">Esta clase debe contener métodos para las operaciones que va a invocar en el artefacto de destino.</span><span class="sxs-lookup"><span data-stu-id="57266-240">This class should contain methods for the operations that you will invoke on the target artifact.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="57266-241">En el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], sobrecargado funciones y procedimientos que aparecen en la **categorías y operaciones disponibles** cuadro como [nombre].1, [nombre].2, [nombre].3 y así sucesivamente, donde [NAME] es el nombre del artefacto sobrecargado y el valor numérico es el identificador de sobrecarga en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="57266-241">In the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], overloaded functions and procedures appear in the **Available categories and operations** box as [NAME].1, [NAME].2, [NAME].3, and so on, where [NAME] is the name of the overloaded artifact and the numeric value is the overload ID on the Oracle database.</span></span>  
  
2.  <span data-ttu-id="57266-242">Cree una instancia de la clase de cliente WCF y llamar a sus métodos para invocar la función o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="57266-242">Create an instance of the WCF client class and call its methods to invoke the function or procedure.</span></span>  
  
 <span data-ttu-id="57266-243">Para obtener más información acerca de cómo crear una clase de cliente WCF e invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [información general sobre el modelo de servicio de WCF con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="57266-243">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF Service Model with the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="57266-244">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se ejecuta cada operación dentro de una transacción en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="57266-244">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes each operation inside of a transaction on the Oracle database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="57266-245">Las clases que representan el REF CURSOR y parámetros de tipo de registro o valores devuelven de funciones o procedimientos (y paquetes) se declaran en un espacio de nombres único para cada función o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="57266-245">The classes that represent REF CURSOR and RECORD type parameters or return values in functions or procedures (and packages) are declared in a unique namespace for each function or procedure.</span></span> <span data-ttu-id="57266-246">Por ejemplo, esto significa que se declarará un tipo de paquete REF CURSOR que se utiliza como un valor devuelto en dos funciones diferentes en un espacio de nombres único para cada método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="57266-246">This means, for example, that a PACKAGE REF CURSOR type that is used as a return value in two different functions will be declared in a unique namespace for each WCF client method.</span></span> <span data-ttu-id="57266-247">O bien debe declarar variables independientes para almacenar estos diferentes valores de retorno o conversión correctamente la variable cuando se invoca uno de los métodos de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="57266-247">You must either declare separate variables to hold these different return values or appropriately cast the variable when you invoke one of the WCF client methods.</span></span>  
  
 <span data-ttu-id="57266-248">En el ejemplo siguiente se muestra cómo llamar al procedimiento /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT sobrecargado para obtener registros de cuenta de la tabla /SCOTT/ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="57266-248">The following example demonstrates calling the overloaded /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT procedure to get account records from the /SCOTT/ACCOUNT table.</span></span> <span data-ttu-id="57266-249">Primero se crea un nuevo registro llamando al procedimiento /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="57266-249">First a new record is created by calling the /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT procedure.</span></span> <span data-ttu-id="57266-250">A continuación, se lee el registro de la nueva copia dos veces mediante una llamada a diferentes sobrecargas de GET_ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="57266-250">Then the new record is read back twice by calling different overloads of GET_ACCOUNT.</span></span> <span data-ttu-id="57266-251">Este ejemplo usa tres clientes WCF, uno para el procedimiento CREATE_ACCOUNT y cada una de las sobrecargas GET_ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="57266-251">This example uses three WCF clients, one for the CREATE_ACCOUNT procedure and one each for the GET_ACCOUNT overloads.</span></span> <span data-ttu-id="57266-252">Alias se usan para distinguir entre los espacios de nombres utilizados para el valor devuelto de GET_ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="57266-252">Aliases are used to distinguish between namespaces used for the return value of GET_ACCOUNT.</span></span> <span data-ttu-id="57266-253">Un ejemplo completo está disponible en los ejemplos del SDK.</span><span class="sxs-lookup"><span data-stu-id="57266-253">A full sample is available in the SDK samples.</span></span> <span data-ttu-id="57266-254">Para obtener más información acerca de los ejemplos SDK, vea [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="57266-254">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF Adapter LOB SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF Adapter LOB SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// Alias client namespaces to shorten declarations of "shared" types   
using CREATE_ACCOUNTns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT;  
using GET_ACCOUNT_BY_IDns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1;  
using GET_ACCOUNT_BY_NAMEns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2;  
  
// This sample demonstrates calling overloaded packaged procedures on Oracle  
// First a new account is created by calling CREATE_ACCOUNT which takes two record parameters  
// Then the information for the new account is returned by calling an overloaded procedure GET_ACCOUNT  
// The first overload returns the account information by account ID  
// The second overload returns the account information by account name  
// Notice that different clients (and namespaces) are created for overloaded procedures and functions  
namespace OracleOverloadsSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            decimal acctId;  
            string newAccountName = "Paula Bento";  
  
            Console.WriteLine("Creating clients");  
            // Create Client for CREATE_ACCOUNT Function  
            SCOTTPackageACCOUNT_PKGClient createAccountClient =   
                new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG");  
            // NOTE: user name and password are case-sensitive  
            createAccountClient.ClientCredentials.UserName.UserName = "SCOTT";  
            createAccountClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 1 -- takes ACCOUNT ID parameter  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client getAccountByIdClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1");  
            // NOTE: user name and password are case-sensitive  
            getAccountByIdClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByIdClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 2 -- takes ACCOUNT NAME parameter  
            // NOTE: this client can be created from configuration; detail provided here  
            // for demonstration  
            OracleDBBinding overload2Binding = new OracleDBBinding();  
            EndpointAddress overload2EndpointAddress = new EndpointAddress("oracleDB://ADAPTER");  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client getAccountByNameClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client(overload2Binding, overload2EndpointAddress);  
            // NOTE: user name and password are case-sensitive  
            getAccountByNameClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByNameClient.ClientCredentials.UserName.Password = "TIGER";  
  
            try  
            {  
                Console.WriteLine("Opening clients -- please wait");  
                // Open clients  
                createAccountClient.Open();  
                getAccountByIdClient.Open();  
                getAccountByNameClient.Open();  
  
                Console.WriteLine("Creating new account");  
                // Create an account record  
                // NOTE: ACCTRECORD is defined in all three namespaces so specify the definition  
                // that corresponds to the client.  
                CREATE_ACCOUNTns.ACCTRECORD acctRec = new CREATE_ACCOUNTns.ACCTRECORD();  
  
                // Set any value for ACCTID -- new account ID is returned by CREATE_ACCOUNT  
                acctRec.ACCTID = 0;  
                acctRec.NAME = newAccountName;  
                acctRec.BALANCE = 10537;  
  
                // Create address record  
                CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD addrRec = new CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD();  
                addrRec.STREET = "456 Valley Rd";  
                addrRec.CITY = "New York";  
                addrRec.STATE = "NY";  
  
                // Create account  
                acctId = (decimal)createAccountClient.CREATE_ACCOUNT(acctRec, addrRec);  
                Console.WriteLine("New Account Created: AccountId = {0}, Name = {1}, Balance = {2:C}",  
                   acctId, acctRec.NAME, acctRec.BALANCE);  
  
                /* Get new account by Id */  
                GET_ACCOUNT_BY_IDns.ACCTRECORD acctById = getAccountByIdClient.GET_ACCOUNT(acctId);  
                Console.WriteLine("Account Returned by Id: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctById.ACCTID, acctById.NAME, acctById.BALANCE);  
  
                /* Get new account by Name */  
                GET_ACCOUNT_BY_NAMEns.ACCTRECORD acctByName = getAccountByNameClient.GET_ACCOUNT(newAccountName);  
                Console.WriteLine("Account Returned by Name: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctByName.ACCTID, acctByName.NAME, acctByName.BALANCE);  
  
                Console.WriteLine("Hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw ex;  
            }  
            finally  
            {  
                // Close all the clients  
                createAccountClient.Close();  
                getAccountByIdClient.Close();  
                getAccountByNameClient.Close();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="57266-255">Vea también</span><span class="sxs-lookup"><span data-stu-id="57266-255">See Also</span></span>  
 [<span data-ttu-id="57266-256">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="57266-256">Develop Oracle Database Applications by Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)