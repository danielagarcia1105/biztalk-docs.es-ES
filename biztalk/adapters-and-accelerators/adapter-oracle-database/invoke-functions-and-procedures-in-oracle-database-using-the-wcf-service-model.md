---
title: Invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, invoke functions and procedures using the WCF service model
- WCF service model, invoking functions and procedures
ms.assetid: 806fc803-3640-42d6-bdf9-53b08f9c7c50
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1423d5945fe1c82ccc64027a28efa3c1777ca5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013157"
---
# <a name="invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="f9876-102">Invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="f9876-102">Invoke Functions and Procedures in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="f9876-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] superficies de procedimientos, funciones y paquetes como operaciones.</span><span class="sxs-lookup"><span data-stu-id="f9876-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces procedures, functions, and packages as operations.</span></span> <span data-ttu-id="f9876-104">En el modelo de servicio WCF estas operaciones se representan como métodos en un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="f9876-104">In the WCF service model these operations are represented as methods on a WCF client.</span></span> <span data-ttu-id="f9876-105">El modelo de servicio WCF y el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f9876-105">The WCF service model and the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span></span>  
  
-   <span data-ttu-id="f9876-106">**Compatibilidad con las funciones**.</span><span class="sxs-lookup"><span data-stu-id="f9876-106">**Support functions**.</span></span> <span data-ttu-id="f9876-107">El valor devuelto de la función de Oracle aparece como el valor devuelto del método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="f9876-107">The RETURN value of the Oracle function is surfaced as the return value of the WCF client method.</span></span> <span data-ttu-id="f9876-108">Parámetros de Oracle se exponen como parámetros (con la dirección adecuada según se define a continuación) para el método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="f9876-108">Oracle parameters are surfaced as parameters (with the appropriate direction as defined below) to the WCF client method.</span></span>  
  
-   <span data-ttu-id="f9876-109">**Admite procedimientos**.</span><span class="sxs-lookup"><span data-stu-id="f9876-109">**Support procedures**.</span></span> <span data-ttu-id="f9876-110">El primer parámetro del procedimiento Oracle OUT aparece como el valor devuelto del método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="f9876-110">The first OUT parameter of the Oracle procedure is surfaced as the return value of the WCF client method.</span></span> <span data-ttu-id="f9876-111">Todos los demás parámetros de Oracle se exponen como parámetros (con la dirección adecuada según se define a continuación) para el método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="f9876-111">All other Oracle parameters are surfaced as parameters (with the appropriate direction as defined below) to the WCF client method.</span></span>  
  
-   <span data-ttu-id="f9876-112">**Compatibilidad con paquetes Oracle**.</span><span class="sxs-lookup"><span data-stu-id="f9876-112">**Support Oracle packages**.</span></span> <span data-ttu-id="f9876-113">El nombre de la operación y el espacio de nombres de sus tipos de parámetro se califican con el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="f9876-113">The name of the operation and the namespace of its parameter types are qualified by the package name.</span></span>  
  
-   <span data-ttu-id="f9876-114">**Compatibilidad con sobrecarga funciones y procedimientos**.</span><span class="sxs-lookup"><span data-stu-id="f9876-114">**Support overloaded functions and procedures**.</span></span>  
  
-   <span data-ttu-id="f9876-115">**Soporte técnico IN, OUT y en los parámetros para los tipos de datos básicos de Oracle para procedimientos y funciones de salida**.</span><span class="sxs-lookup"><span data-stu-id="f9876-115">**Support IN, OUT and IN OUT parameters for basic Oracle data types for both procedures and functions**.</span></span> <span data-ttu-id="f9876-116">Los parámetros OUT se exponen como **out** los parámetros del método de cliente WCF y los parámetros OUT IN aparecen como **ref** parámetros.</span><span class="sxs-lookup"><span data-stu-id="f9876-116">OUT parameters are surfaced as **out** parameters on the WCF client method and IN OUT parameters are surfaced as **ref** parameters.</span></span>  
  
-   <span data-ttu-id="f9876-117">**EN soporte técnico, de salida y en parámetros REF CURSOR para los procedimientos y funciones, así como valores devueltos de función de salida**.</span><span class="sxs-lookup"><span data-stu-id="f9876-117">**Support IN, OUT, and IN OUT REF CURSOR parameters for procedures and functions, as well as function RETURN values**.</span></span> <span data-ttu-id="f9876-118">Para obtener más información, consulte [realizar operaciones utilizando los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="f9876-118">For more information, see [Performing Operations Using REF CURSORS in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="f9876-119">**Compatibilidad con en, OUT y IN OUT registro escriba los parámetros de procedimientos y funciones, así como valores devueltos de función**.</span><span class="sxs-lookup"><span data-stu-id="f9876-119">**Support IN, OUT, and IN OUT RECORD type parameters for procedures and functions, as well as function RETURN values**.</span></span> <span data-ttu-id="f9876-120">Para obtener más información, consulte [realizar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="f9876-120">For more information, see [Performing Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="f9876-121">Acerca de los ejemplos usados en este tema.</span><span class="sxs-lookup"><span data-stu-id="f9876-121">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="f9876-122">Los ejemplos de este tema usan el /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT sobrecargado procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f9876-122">The examples in this topic use the /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT overloaded procedure.</span></span> <span data-ttu-id="f9876-123">Este procedimiento lee un registro de la tabla de SCOTT/cuenta basada en un identificador de cuenta o un nombre de cuenta.</span><span class="sxs-lookup"><span data-stu-id="f9876-123">This procedure reads a record from the SCOTT/ACCOUNT table based on either an account ID or an account name.</span></span> <span data-ttu-id="f9876-124">Una secuencia de comandos para generar este procedimiento y la tabla se suministra con los ejemplos del SDK.</span><span class="sxs-lookup"><span data-stu-id="f9876-124">A script to generate this procedure and table is supplied with the SDK samples.</span></span> <span data-ttu-id="f9876-125">Para obtener más información acerca de los ejemplos SDK, consulte [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="f9876-125">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="f9876-126">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="f9876-126">The WCF Client Class</span></span>  
 <span data-ttu-id="f9876-127">En la tabla siguiente se muestra el nombre del cliente WCF y el método generado para los procedimientos, funciones y paquetes que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies.</span><span class="sxs-lookup"><span data-stu-id="f9876-127">The following table shows the name of the WCF client and the method generated for procedures, functions and packages that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces.</span></span> <span data-ttu-id="f9876-128">A menos que se sobrecarga una función o procedimiento, se utiliza un único cliente WCF para invocar todas las funciones en un esquema, todos los procedimientos en un esquema, o todas las funciones y procedimientos de un paquete.</span><span class="sxs-lookup"><span data-stu-id="f9876-128">Unless a function or procedure is overloaded, a single WCF client is used to invoke all of the functions in a schema, all of the procedures in a schema, or all of the functions and procedures in a package.</span></span>  
  
|<span data-ttu-id="f9876-129">Artefacto de Oracle</span><span class="sxs-lookup"><span data-stu-id="f9876-129">Oracle Artifact</span></span>|<span data-ttu-id="f9876-130">Nombre de operación de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="f9876-130">WCF Client Operation Name</span></span>|<span data-ttu-id="f9876-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9876-131">Example</span></span>|  
|---------------------|-------------------------------|-------------|  
|<span data-ttu-id="f9876-132">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="f9876-132">Procedure</span></span>|<span data-ttu-id="f9876-133">[ESQUEMA] ProcedureClient. [PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="f9876-133">[SCHEMA]ProcedureClient.[PROC_NAME]</span></span>|<span data-ttu-id="f9876-134">SCOTTProcedureClient.MYPROC</span><span class="sxs-lookup"><span data-stu-id="f9876-134">SCOTTProcedureClient.MYPROC</span></span>|  
|<span data-ttu-id="f9876-135">Función</span><span class="sxs-lookup"><span data-stu-id="f9876-135">Function</span></span>|<span data-ttu-id="f9876-136">[ESQUEMA] FunctionClient. [FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="f9876-136">[SCHEMA]FunctionClient.[FUNC_NAME]</span></span>|<span data-ttu-id="f9876-137">SCOTTProcedureClient.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="f9876-137">SCOTTProcedureClient.MYFUNC</span></span>|  
|<span data-ttu-id="f9876-138">Paquete (procedimiento o función)</span><span class="sxs-lookup"><span data-stu-id="f9876-138">Package (procedure or function)</span></span>|<span data-ttu-id="f9876-139">[ESQUEMA] [Nombre_del_paquete] del paquete cliente. [PROC_NAME o FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="f9876-139">[SCHEMA]Package[PACKAGE_NAME]Client.[PROC_NAME or FUNC_NAME]</span></span>|<span data-ttu-id="f9876-140">SCOTTPackageMYPACKAGEClient.MYPROC</span><span class="sxs-lookup"><span data-stu-id="f9876-140">SCOTTPackageMYPACKAGEClient.MYPROC</span></span>|  
  
 <span data-ttu-id="f9876-141">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="f9876-141">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="f9876-142">[PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo, MYPROC.</span><span class="sxs-lookup"><span data-stu-id="f9876-142">[PROC_NAME] = The name of an Oracle procedure; for example, MYPROC.</span></span>  
  
 <span data-ttu-id="f9876-143">[FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.</span><span class="sxs-lookup"><span data-stu-id="f9876-143">[FUNC_NAME] = The name of an Oracle function; for example, MYFUNC.</span></span>  
  
 <span data-ttu-id="f9876-144">[Nombre_del_paquete] = el nombre de un paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="f9876-144">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="f9876-145">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle registro representa parámetros de tipo y devolver valores, así como los conjuntos de resultados devueltos por parámetros REF CURSOR como tipos complejos de XML que contienen los datos de fila (o campos) de un registro de Oracle.</span><span class="sxs-lookup"><span data-stu-id="f9876-145">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents Oracle RECORD type parameters and return values as well as the result sets returned by REF CURSOR parameters as complex XML types that contain the row data (or fields) of an Oracle record.</span></span> <span data-ttu-id="f9876-146">En el modelo de servicio WCF, cada uno de estos tipos XML se representa como una clase. NET; las propiedades de la clase representan los campos del tipo de registro o conjunto de resultados de REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="f9876-146">In the WCF service model, each of these XML types is represented as a .NET class; the properties of the class represent the fields of the RECORD type or REF CURSOR result set.</span></span> <span data-ttu-id="f9876-147">Tipos de registros de Oracle siempre se representan como clases .NET fuertemente tipadas.</span><span class="sxs-lookup"><span data-stu-id="f9876-147">Oracle RECORD types are always represented as strongly-typed .NET classes.</span></span> <span data-ttu-id="f9876-148">Sin embargo, un conjunto de resultados de REF CURSOR puede representarse como registros fuertemente tipada o débilmente tipada en función de si se declara el REF CURSOR propio fuertemente tipada como o débilmente tipada.</span><span class="sxs-lookup"><span data-stu-id="f9876-148">A REF CURSOR result set, however, can be represented as either strongly-typed or weakly-typed records based on whether the REF CURSOR itself is declared as strongly-typed or weakly-typed.</span></span> <span data-ttu-id="f9876-149">Las clases que representan REF CURSOR o registro tipo parámetros (o valores devueltos) se generan en un único espacio de nombres según el procedimiento, función o paquete.</span><span class="sxs-lookup"><span data-stu-id="f9876-149">The classes that represent REF CURSOR or RECORD type parameters (or return values) are generated in a unique namespace based on the procedure, function, or package.</span></span> <span data-ttu-id="f9876-150">En la tabla siguiente se muestra estos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="f9876-150">The following table shows these namespaces.</span></span>  
  
|<span data-ttu-id="f9876-151">Artefacto de Oracle</span><span class="sxs-lookup"><span data-stu-id="f9876-151">Oracle Artifact</span></span>|<span data-ttu-id="f9876-152">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f9876-152">Namespace</span></span>|<span data-ttu-id="f9876-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9876-153">Example</span></span>|  
|---------------------|---------------|-------------|  
|<span data-ttu-id="f9876-154">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="f9876-154">Procedure</span></span>|<span data-ttu-id="f9876-155">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="f9876-155">[BASE_NS].</span></span> <span data-ttu-id="f9876-156">[ESQUEMA]. Procedimiento. [PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="f9876-156">[SCHEMA].Procedure.[PROC_NAME]</span></span>|<span data-ttu-id="f9876-157">Microsoft.lobservices.OracleDB._2007._03.Scott. Procedure.MYPROC</span><span class="sxs-lookup"><span data-stu-id="f9876-157">microsoft.lobservices.oracledb._2007._03.SCOTT.Procedure.MYPROC</span></span>|  
|<span data-ttu-id="f9876-158">Función</span><span class="sxs-lookup"><span data-stu-id="f9876-158">Function</span></span>|<span data-ttu-id="f9876-159">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="f9876-159">[BASE_NS].</span></span> <span data-ttu-id="f9876-160">[ESQUEMA]. Función. [FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="f9876-160">[SCHEMA].Function.[FUNC_NAME]</span></span>|<span data-ttu-id="f9876-161">Microsoft.lobservices.OracleDB._2007._03.Scott. Function.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="f9876-161">microsoft.lobservices.oracledb._2007._03.SCOTT.Function.MYFUNC</span></span>|  
|<span data-ttu-id="f9876-162">Paquete (procedimiento)</span><span class="sxs-lookup"><span data-stu-id="f9876-162">Package (Procedure)</span></span>|<span data-ttu-id="f9876-163">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="f9876-163">[BASE_NS].</span></span> <span data-ttu-id="f9876-164">[ESQUEMA]. Paquete. [NOMBRE_DEL_PAQUETE]. [PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="f9876-164">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME]</span></span>|<span data-ttu-id="f9876-165">Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYPROC</span><span class="sxs-lookup"><span data-stu-id="f9876-165">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC</span></span>|  
|<span data-ttu-id="f9876-166">Paquete (función)</span><span class="sxs-lookup"><span data-stu-id="f9876-166">Package (Function)</span></span>|<span data-ttu-id="f9876-167">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="f9876-167">[BASE_NS].</span></span> <span data-ttu-id="f9876-168">[ESQUEMA]. Paquete. [NOMBRE_DEL_PAQUETE]. [FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="f9876-168">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME]</span></span>|<span data-ttu-id="f9876-169">Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="f9876-169">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC</span></span>|  
|<span data-ttu-id="f9876-170">Genéricos (débilmente tipada) del conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="f9876-170">Generic Record Set (weakly-typed)</span></span>|<span data-ttu-id="f9876-171">[BASE_NS]</span><span class="sxs-lookup"><span data-stu-id="f9876-171">[BASE_NS]</span></span>|<span data-ttu-id="f9876-172">Microsoft.lobservices.OracleDB._2007._03</span><span class="sxs-lookup"><span data-stu-id="f9876-172">microsoft.lobservices.oracledb._2007._03</span></span>|  
  
 <span data-ttu-id="f9876-173">[BASE_NS] = el espacio de nombres de adaptador base; Microsoft.lobservices.OracleDB._2007._03.</span><span class="sxs-lookup"><span data-stu-id="f9876-173">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span></span>  
  
 <span data-ttu-id="f9876-174">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="f9876-174">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="f9876-175">[PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo: MYPROC.</span><span class="sxs-lookup"><span data-stu-id="f9876-175">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="f9876-176">[FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.</span><span class="sxs-lookup"><span data-stu-id="f9876-176">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="f9876-177">[Nombre_del_paquete] = el nombre de un paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="f9876-177">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="f9876-178">Para obtener información sobre cómo se usan estos espacios de nombres para los parámetros de registro, vea [realizar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="f9876-178">For information about how these namespaces are used for RECORD parameters, see [Performing Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span> <span data-ttu-id="f9876-179">Para obtener información sobre cómo se usan estos espacios de nombres para los parámetros REF CURSOR, vea [realizar operaciones utilizando los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="f9876-179">For information about how these namespaces are used for REF CURSOR parameters, see [Performing Operations Using REF CURSORS in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="f9876-180">En general, los parámetros de Oracle y los valores devueltos se asignan como se indica a continuación en el método de cliente WCF:</span><span class="sxs-lookup"><span data-stu-id="f9876-180">In general, the Oracle parameters and return values are mapped as follows in the WCF client method:</span></span>  
  
- <span data-ttu-id="f9876-181">Parámetros IN de Oracle se asignan a parámetros de (entrada). NET.</span><span class="sxs-lookup"><span data-stu-id="f9876-181">Oracle IN parameters are mapped to .NET (input) parameters.</span></span>  
  
- <span data-ttu-id="f9876-182">Los parámetros OUT de Oracle se asignan a .NET **out** parámetros.</span><span class="sxs-lookup"><span data-stu-id="f9876-182">Oracle OUT parameters are mapped to .NET **out** parameters.</span></span>  
  
- <span data-ttu-id="f9876-183">Oracle en los parámetros se asignan a .NET **ref** parámetros.</span><span class="sxs-lookup"><span data-stu-id="f9876-183">Oracle IN OUT parameters are mapped to .NET **ref** parameters.</span></span>  
  
- <span data-ttu-id="f9876-184">Función que se asignan los valores devueltos para el valor devuelto del método.</span><span class="sxs-lookup"><span data-stu-id="f9876-184">Function RETURN values are mapped to the method return value.</span></span>  
  
  <span data-ttu-id="f9876-185">Sin embargo, existen dos excepciones importantes:</span><span class="sxs-lookup"><span data-stu-id="f9876-185">However, two important exceptions exist:</span></span>  
  
- <span data-ttu-id="f9876-186">Los parámetros IN OUT REF CURSOR de Oracle se dividen en una cadena de entrada y salida (**out**) conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="f9876-186">Oracle IN OUT REF CURSOR parameters are split into an input string and an output (**out**) record set.</span></span> <span data-ttu-id="f9876-187">Esto es porque el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] representa los parámetros IN REF CUSROR como cadenas y los parámetros de salida de REF CURSOR como tipos complejos (conjuntos de registros), estos no se pueden combinar en un solo parámetro.</span><span class="sxs-lookup"><span data-stu-id="f9876-187">This is because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents IN REF CUSROR parameters as strings and OUT REF CURSOR parameters as complex types (record sets), these cannot be combined into a single parameter.</span></span>  
  
- <span data-ttu-id="f9876-188">El parámetro en un procedimiento de Oracle, primero se asigna al valor devuelto del método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="f9876-188">The first OUT parameter in an Oracle procedure is mapped to the return value of the WCF client method.</span></span> <span data-ttu-id="f9876-189">Es el comportamiento WCF estándar.</span><span class="sxs-lookup"><span data-stu-id="f9876-189">This is standard WCF behavior.</span></span>  
  
  <span data-ttu-id="f9876-190">El ejemplo siguiente muestra parte de un procedimiento simple de Oracle (cargado en el esquema SCOTT) y la firma del método de cliente WCF que se genera para invocarlo.</span><span class="sxs-lookup"><span data-stu-id="f9876-190">The following example shows part of a simple Oracle procedure (loaded in the SCOTT schema) and the signature of the WCF client method that is generated to invoke it.</span></span> <span data-ttu-id="f9876-191">El procedimiento de Oracle tiene tres parámetros, tres parámetros IN OUT y tres parámetros OUT Sin embargo, el método de cliente WCF no asigna un parámetro para el primer parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="f9876-191">The Oracle procedure has three IN parameters, three IN OUT parameters, and three OUT parameters; however, the WCF client method does not map a parameter for the first OUT parameter.</span></span> <span data-ttu-id="f9876-192">En su lugar se asigna al valor devuelto de método.</span><span class="sxs-lookup"><span data-stu-id="f9876-192">Instead it is mapped to the method return value.</span></span>  
  
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
  
### <a name="support-for-overloaded-procedures-functions-and-packages"></a><span data-ttu-id="f9876-193">Compatibilidad con procedimientos sobrecargados, funciones y paquetes</span><span class="sxs-lookup"><span data-stu-id="f9876-193">Support for Overloaded Procedures, Functions and Packages</span></span>  
 <span data-ttu-id="f9876-194">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite sobrecarga procedimientos, funciones y paquetes anexando una cadena única para el identificador de nodo y el espacio de nombres que pone de manifiesto para cada artefacto sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="f9876-194">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports overloaded procedures, functions, and packages by appending a unique string to the node ID and the namespace that it surfaces for each overloaded artifact.</span></span> <span data-ttu-id="f9876-195">Esta cadena es "overload1" para la primera sobrecarga, "overload2" para la sobrecarga siguiente y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="f9876-195">This string is "overload1" for the first overload, "overload2" for the next overload, and so on.</span></span>  
  
 <span data-ttu-id="f9876-196">En el modelo de servicio WCF cada función o un procedimiento sobrecargado se representa mediante un único cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="f9876-196">In the WCF service model each overloaded procedure or function is represented by a unique WCF client.</span></span> <span data-ttu-id="f9876-197">Esto es diferente en el caso de no sobrecargar en el que todos las funciones de un esquema, todos los procedimientos en un esquema, o todos los procedimientos y funciones en un paquete se invocan el mismo cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="f9876-197">This is different from the non-overloaded case in which all of the functions in a SCHEMA, all of the procedures in a SCHEMA, or all of the procedures and functions in a PACKAGE are invoked by the same WCF client.</span></span> <span data-ttu-id="f9876-198">En la tabla siguiente se muestra al cliente de WCF nombre y el método generada para procedimientos sobrecargados, funciones y paquetes.</span><span class="sxs-lookup"><span data-stu-id="f9876-198">The following table shows the WCF client name and method generated for overloaded procedures, functions, and packages.</span></span>  
  
|<span data-ttu-id="f9876-199">Artefacto de Oracle</span><span class="sxs-lookup"><span data-stu-id="f9876-199">Oracle Artifact</span></span>|<span data-ttu-id="f9876-200">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="f9876-200">WCF Client Name</span></span>|<span data-ttu-id="f9876-201">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9876-201">Example</span></span>|  
|---------------------|---------------------|-------------|  
|<span data-ttu-id="f9876-202">Paquete sobrecargado (procedimiento)</span><span class="sxs-lookup"><span data-stu-id="f9876-202">Overloaded Package (Procedure)</span></span>|<span data-ttu-id="f9876-203">[ESQUEMA] Paquetes [nombre_del_paquete] [PROC_NAME]] [OVERLOAD_ID] cliente. [PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="f9876-203">[SCHEMA]Package[PACKAGE_NAME][PROC_NAME] ][OVERLOAD_ID]Client.[PROC_NAME]</span></span>|<span data-ttu-id="f9876-204">SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC</span><span class="sxs-lookup"><span data-stu-id="f9876-204">SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC</span></span>|  
|<span data-ttu-id="f9876-205">Paquete sobrecargado (función)</span><span class="sxs-lookup"><span data-stu-id="f9876-205">Overloaded Package (Function)</span></span>|<span data-ttu-id="f9876-206">[ESQUEMA] Paquetes [nombre_del_paquete] [FUNC_NAME]] [OVERLOAD_ID] cliente. [FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="f9876-206">[SCHEMA]Package[PACKAGE_NAME][FUNC_NAME] ][OVERLOAD_ID]Client.[FUNC_NAME]</span></span>|<span data-ttu-id="f9876-207">SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="f9876-207">SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC</span></span>|  
  
 <span data-ttu-id="f9876-208">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="f9876-208">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="f9876-209">[PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo: MYPROC.</span><span class="sxs-lookup"><span data-stu-id="f9876-209">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="f9876-210">[FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.</span><span class="sxs-lookup"><span data-stu-id="f9876-210">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="f9876-211">[Nombre_del_paquete] = el nombre de un paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="f9876-211">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="f9876-212">[OVERLOAD_ID] = la cadena única que identifica el artefacto sobrecargado; "overload1", "overload2" y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="f9876-212">[OVERLOAD_ID] = The unique string that identifies the overloaded artifact; "overload1", "overload2", and so on.</span></span>  
  
 <span data-ttu-id="f9876-213">En la tabla siguiente se muestra el espacio de nombres que se genera para procedimientos sobrecargados, funciones y paquetes.</span><span class="sxs-lookup"><span data-stu-id="f9876-213">The following table shows the namespace generated for overloaded procedures, functions, and packages.</span></span>  
  
|<span data-ttu-id="f9876-214">Artefacto de Oracle</span><span class="sxs-lookup"><span data-stu-id="f9876-214">Oracle Artifact</span></span>|<span data-ttu-id="f9876-215">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f9876-215">Namespace</span></span>|<span data-ttu-id="f9876-216">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9876-216">Example</span></span>|  
|---------------------|---------------|-------------|  
|<span data-ttu-id="f9876-217">Paquete (procedimiento)</span><span class="sxs-lookup"><span data-stu-id="f9876-217">Package (Procedure)</span></span>|<span data-ttu-id="f9876-218">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="f9876-218">[BASE_NS].</span></span> <span data-ttu-id="f9876-219">[ESQUEMA]. Paquete. [NOMBRE_DEL_PAQUETE]. [PROC_NAME] [OVERLOAD_ID]</span><span class="sxs-lookup"><span data-stu-id="f9876-219">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME] [OVERLOAD_ID]</span></span>|<span data-ttu-id="f9876-220">Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYPROC.overload1</span><span class="sxs-lookup"><span data-stu-id="f9876-220">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC.overload1</span></span>|  
|<span data-ttu-id="f9876-221">Paquete (función)</span><span class="sxs-lookup"><span data-stu-id="f9876-221">Package (Function)</span></span>|<span data-ttu-id="f9876-222">[BASE_NS].</span><span class="sxs-lookup"><span data-stu-id="f9876-222">[BASE_NS].</span></span> <span data-ttu-id="f9876-223">[ESQUEMA]. Paquete. [NOMBRE_DEL_PAQUETE]. [FUNC_NAME]. [OVERLOAD_ID]</span><span class="sxs-lookup"><span data-stu-id="f9876-223">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME].[OVERLOAD_ID]</span></span>|<span data-ttu-id="f9876-224">Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYFUNC.overload1</span><span class="sxs-lookup"><span data-stu-id="f9876-224">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC.overload1</span></span>|  
|<span data-ttu-id="f9876-225">Genéricos (débilmente tipada) del conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="f9876-225">Generic Record Set (weakly-typed)</span></span>|<span data-ttu-id="f9876-226">[BASE_NS]</span><span class="sxs-lookup"><span data-stu-id="f9876-226">[BASE_NS]</span></span>|<span data-ttu-id="f9876-227">Microsoft.lobservices.OracleDB._2007._03</span><span class="sxs-lookup"><span data-stu-id="f9876-227">microsoft.lobservices.oracledb._2007._03</span></span>|  
  
 <span data-ttu-id="f9876-228">[BASE_NS] = el espacio de nombres de adaptador base; Microsoft.lobservices.OracleDB._2007._03.</span><span class="sxs-lookup"><span data-stu-id="f9876-228">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span></span>  
  
 <span data-ttu-id="f9876-229">[Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.</span><span class="sxs-lookup"><span data-stu-id="f9876-229">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="f9876-230">[PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo: MYPROC.</span><span class="sxs-lookup"><span data-stu-id="f9876-230">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="f9876-231">[FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.</span><span class="sxs-lookup"><span data-stu-id="f9876-231">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="f9876-232">[Nombre_del_paquete] = el nombre de un paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="f9876-232">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="f9876-233">[OVERLOAD_ID] = la cadena única que identifica el artefacto sobrecargado; "overload1", "overload2" y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="f9876-233">[OVERLOAD_ID] = The unique string that identifies the overloaded artifact; "overload1", "overload2", and so on.</span></span> <span data-ttu-id="f9876-234">El valor numérico en la cadena es el identificador de la sobrecarga del artefacto mantenida por la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="f9876-234">The numeric value in the string is the overload ID for the artifact maintained by the Oracle database.</span></span>  
  
 <span data-ttu-id="f9876-235">El ejemplo siguiente muestra los clientes WCF y las firmas de método generadas para el procedimiento GET_ACCOUNT sobrecargado en el paquete ACCOUNT_PKG.</span><span class="sxs-lookup"><span data-stu-id="f9876-235">The following example shows the WCF clients and the method signatures generated for the overloaded GET_ACCOUNT procedure in the ACCOUNT_PKG package.</span></span> <span data-ttu-id="f9876-236">(Las declaraciones de Oracle se incluyen). En este ejemplo se muestra cómo se genera un único cliente WCF para cada sobrecarga y cómo el método generado para cada cliente devuelve un conjunto de registros en un espacio de nombres único.</span><span class="sxs-lookup"><span data-stu-id="f9876-236">(The Oracle declarations are included.) This example shows how a unique WCF client is generated for each overload and how the method generated for each client returns a record set in a unique namespace.</span></span>  
  
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
  
## <a name="invoking-functions-and-procedures"></a><span data-ttu-id="f9876-237">Invocar funciones y procedimientos</span><span class="sxs-lookup"><span data-stu-id="f9876-237">Invoking Functions and Procedures</span></span>  
 <span data-ttu-id="f9876-238">Para invocar una función o un procedimiento con un cliente WCF, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f9876-238">To invoke a function or a procedure by using a WCF client, perform the following steps.</span></span>  
  
1. <span data-ttu-id="f9876-239">Generar una clase de cliente WCF para la función de destino, el procedimiento o el paquete.</span><span class="sxs-lookup"><span data-stu-id="f9876-239">Generate a WCF client class for the target function, procedure, or package.</span></span> <span data-ttu-id="f9876-240">Esta clase debe contener métodos para las operaciones que va a invocar en el artefacto de destino.</span><span class="sxs-lookup"><span data-stu-id="f9876-240">This class should contain methods for the operations that you will invoke on the target artifact.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f9876-241">En el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]sobrecargado funciones y procedimientos que aparecen en la **operaciones y categorías disponibles** cuadro como [nombre].1, [nombre].2, [nombre].3 y así sucesivamente, donde [NAME] es el nombre del artefacto sobrecargado y el valor numérico es el identificador de sobrecarga en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="f9876-241">In the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], overloaded functions and procedures appear in the **Available categories and operations** box as [NAME].1, [NAME].2, [NAME].3, and so on, where [NAME] is the name of the overloaded artifact and the numeric value is the overload ID on the Oracle database.</span></span>  
  
2. <span data-ttu-id="f9876-242">Cree una instancia de la clase de cliente WCF y llamar a sus métodos para invocar la función o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f9876-242">Create an instance of the WCF client class and call its methods to invoke the function or procedure.</span></span>  
  
   <span data-ttu-id="f9876-243">Para obtener más información acerca de cómo crear una clase de cliente WCF e invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [general del modelo de servicio WCF con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f9876-243">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF Service Model with the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
   <span data-ttu-id="f9876-244">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ejecuta cada operación dentro de una transacción en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="f9876-244">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes each operation inside of a transaction on the Oracle database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f9876-245">Las clases que representan el REF CURSOR y parámetros de tipo de registro o valores devuelven de funciones o procedimientos (y paquetes) se declaran en un espacio de nombres único para cada función o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f9876-245">The classes that represent REF CURSOR and RECORD type parameters or return values in functions or procedures (and packages) are declared in a unique namespace for each function or procedure.</span></span> <span data-ttu-id="f9876-246">Por ejemplo, esto significa que se declarará un tipo de paquete REF CURSOR que se utiliza como valor devuelto en dos funciones diferentes en un espacio de nombres único para cada método de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="f9876-246">This means, for example, that a PACKAGE REF CURSOR type that is used as a return value in two different functions will be declared in a unique namespace for each WCF client method.</span></span> <span data-ttu-id="f9876-247">O bien debe declarar variables independientes para almacenar estos diferentes valores de retorno o conversión correctamente la variable cuando se invoca uno de los métodos de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="f9876-247">You must either declare separate variables to hold these different return values or appropriately cast the variable when you invoke one of the WCF client methods.</span></span>  
  
 <span data-ttu-id="f9876-248">El ejemplo siguiente muestra una llamada al procedimiento /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT sobrecargado para obtener registros de cuenta de la tabla /SCOTT/ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="f9876-248">The following example demonstrates calling the overloaded /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT procedure to get account records from the /SCOTT/ACCOUNT table.</span></span> <span data-ttu-id="f9876-249">Primero se crea un nuevo registro llamando al procedimiento /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="f9876-249">First a new record is created by calling the /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT procedure.</span></span> <span data-ttu-id="f9876-250">A continuación, se lee el nuevo registro back dos veces al llamar a las distintas sobrecargas de GET_ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="f9876-250">Then the new record is read back twice by calling different overloads of GET_ACCOUNT.</span></span> <span data-ttu-id="f9876-251">Este ejemplo utiliza tres clientes WCF, uno para el procedimiento CREATE_ACCOUNT y uno para las sobrecargas GET_ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="f9876-251">This example uses three WCF clients, one for the CREATE_ACCOUNT procedure and one each for the GET_ACCOUNT overloads.</span></span> <span data-ttu-id="f9876-252">Los alias se usan para distinguir entre los espacios de nombres utilizados para el valor devuelto de GET_ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="f9876-252">Aliases are used to distinguish between namespaces used for the return value of GET_ACCOUNT.</span></span> <span data-ttu-id="f9876-253">Un ejemplo completo está disponible en los ejemplos del SDK.</span><span class="sxs-lookup"><span data-stu-id="f9876-253">A full sample is available in the SDK samples.</span></span> <span data-ttu-id="f9876-254">Para obtener más información acerca de los ejemplos SDK, consulte [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="f9876-254">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f9876-255">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9876-255">See Also</span></span>  
 [<span data-ttu-id="f9876-256">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="f9876-256">Develop Oracle Database Applications by Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)