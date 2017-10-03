---
title: Clase SiebelCommand en el adaptador de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SiebelCommand
- Data Provider for Siebel, SiebelCommand
- SiebelCommand, supported methods and properties
ms.assetid: 7cba0e47-634b-4878-b480-80fbcbbf5c90
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d268e9a1d5954d703d392070a53c84bd9cee0d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="siebelcommand-class-in-the-siebel-adapter"></a><span data-ttu-id="dcae3-102">Clase SiebelCommand en el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="dcae3-102">SiebelCommand class in the Siebel adapter</span></span>
<span data-ttu-id="dcae3-103">Después de establecer una conexión con el sistema Siebel, el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] analiza las cadenas de comandos de Siebel y parámetros de los comandos proporcionados por el cliente ADO.NET y asigna el comando en un mensaje de solicitud WCF.</span><span class="sxs-lookup"><span data-stu-id="dcae3-103">After establishing a connection with the Siebel system, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] parses the Siebel command strings and command parameters provided by the ADO.NET client and maps the command into a WCF request message.</span></span> <span data-ttu-id="dcae3-104">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] , a continuación, envía la solicitud a la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y obtiene la respuesta XML y el contenido del cuerpo del adaptador.</span><span class="sxs-lookup"><span data-stu-id="dcae3-104">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] then sends the request to the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and obtains the response XML and the body contents from the adapter.</span></span> <span data-ttu-id="dcae3-105">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] , a continuación, utiliza el `XMLDataReader` para recuperar los datos relacionales desde el cuerpo XML.</span><span class="sxs-lookup"><span data-stu-id="dcae3-105">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] then uses the `XMLDataReader` to retrieve the relational data from the XML body.</span></span>  
  
 <span data-ttu-id="dcae3-106">Mediante una instancia de `Microsoft.Data.SiebelClient.SiebelClientFactory`, un programa cliente puede obtener una instancia de la `System.Data.Common.DbCommand` clase para construir un comando de Siebel.</span><span class="sxs-lookup"><span data-stu-id="dcae3-106">Using an instance of `Microsoft.Data.SiebelClient.SiebelClientFactory`, a client program can obtain an instance of the `System.Data.Common.DbCommand` class to construct a Siebel command.</span></span>  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbCommand command = factory.CreateCommand();  
```  
  
 <span data-ttu-id="dcae3-107">También se puede usar el siguiente método para crear un comando:</span><span class="sxs-lookup"><span data-stu-id="dcae3-107">Alternatively, the following approach can be used to create a command:</span></span>  
  
```  
//Here connection is an instance of SiebelConnection  
SiebelCommand cmd = (SiebelCommand) connection.CreateCommand();  
cmd.CommandText = "SELECT [Name] as MyName, [City], [Country]  from Account.Account WHERE Name LIKE '3Com*' OPTION 'ViewMode 1'";  
```  
  
 <span data-ttu-id="dcae3-108">El `SiebelCommand` clase hereda de `DbCommand`.</span><span class="sxs-lookup"><span data-stu-id="dcae3-108">The `SiebelCommand` class inherits from `DbCommand`.</span></span>  <span data-ttu-id="dcae3-109">Se encuentra en el espacio de nombres `Microsoft.Data.SiebelClient`.</span><span class="sxs-lookup"><span data-stu-id="dcae3-109">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="dcae3-110">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="dcae3-110">Supported Properties</span></span>  
 <span data-ttu-id="dcae3-111">El **SiebelCommand** clase admite las siguientes `DbCommand` *protegido* propiedades:</span><span class="sxs-lookup"><span data-stu-id="dcae3-111">The **SiebelCommand** class supports the following `DbCommand`*protected* properties:</span></span>  
  
|<span data-ttu-id="dcae3-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="dcae3-112">Name</span></span>|<span data-ttu-id="dcae3-113">Get/Set.</span><span class="sxs-lookup"><span data-stu-id="dcae3-113">Get/Set</span></span>|<span data-ttu-id="dcae3-114">Description</span><span class="sxs-lookup"><span data-stu-id="dcae3-114">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="dcae3-115">**DbConnection**</span><span class="sxs-lookup"><span data-stu-id="dcae3-115">**DbConnection**</span></span>|<span data-ttu-id="dcae3-116">Get y Set</span><span class="sxs-lookup"><span data-stu-id="dcae3-116">Get and Set</span></span>|<span data-ttu-id="dcae3-117">Este archivo debe contener subyacente `DbConnection` instancia a partir del cual `DbCommand` se obtiene la instancia.</span><span class="sxs-lookup"><span data-stu-id="dcae3-117">This should contain the underlying `DbConnection` instance from which this `DbCommand` instance is obtained.</span></span>|  
|<span data-ttu-id="dcae3-118">**DbParameterCollection**</span><span class="sxs-lookup"><span data-stu-id="dcae3-118">**DbParameterCollection**</span></span>|<span data-ttu-id="dcae3-119">Obtener</span><span class="sxs-lookup"><span data-stu-id="dcae3-119">Get</span></span>|<span data-ttu-id="dcae3-120">Obtiene la colección de `DbParameter` objetos.</span><span class="sxs-lookup"><span data-stu-id="dcae3-120">Gets the collection of `DbParameter` objects.</span></span>|  
  
 <span data-ttu-id="dcae3-121">`SiebelCommand`también admite las siguientes `DbCommand` *público* propiedades:</span><span class="sxs-lookup"><span data-stu-id="dcae3-121">`SiebelCommand` also supports the following `DbCommand`*public* properties:</span></span>  
  
|<span data-ttu-id="dcae3-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="dcae3-122">Name</span></span>|<span data-ttu-id="dcae3-123">Get/Set.</span><span class="sxs-lookup"><span data-stu-id="dcae3-123">Get/Set</span></span>|<span data-ttu-id="dcae3-124">Description</span><span class="sxs-lookup"><span data-stu-id="dcae3-124">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="dcae3-125">**CommandText**</span><span class="sxs-lookup"><span data-stu-id="dcae3-125">**CommandText**</span></span>|<span data-ttu-id="dcae3-126">Get y Set</span><span class="sxs-lookup"><span data-stu-id="dcae3-126">Get and Set</span></span>|<span data-ttu-id="dcae3-127">Esto contiene la instrucción SQL que desea ejecutar el cliente ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="dcae3-127">This contain the SQL statement that the ADO.NET client wishes to execute.</span></span>|  
|<span data-ttu-id="dcae3-128">**CommandType**</span><span class="sxs-lookup"><span data-stu-id="dcae3-128">**CommandType**</span></span>|<span data-ttu-id="dcae3-129">Get y Set</span><span class="sxs-lookup"><span data-stu-id="dcae3-129">Get and Set</span></span>|<span data-ttu-id="dcae3-130">Sólo `CommandType.Text` se admite.</span><span class="sxs-lookup"><span data-stu-id="dcae3-130">Only `CommandType.Text` is supported.</span></span>|  
|<span data-ttu-id="dcae3-131">**Conexión**</span><span class="sxs-lookup"><span data-stu-id="dcae3-131">**Connection**</span></span>|<span data-ttu-id="dcae3-132">Get y Set</span><span class="sxs-lookup"><span data-stu-id="dcae3-132">Get and Set</span></span>|<span data-ttu-id="dcae3-133">Esto utiliza el `DbConnection` miembro.</span><span class="sxs-lookup"><span data-stu-id="dcae3-133">This uses the `DbConnection` member.</span></span>|  
|<span data-ttu-id="dcae3-134">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="dcae3-134">**Parameters**</span></span>|<span data-ttu-id="dcae3-135">Obtener</span><span class="sxs-lookup"><span data-stu-id="dcae3-135">Get</span></span>|<span data-ttu-id="dcae3-136">Esto utiliza el `DbParameterCollection` miembro.</span><span class="sxs-lookup"><span data-stu-id="dcae3-136">This uses the `DbParameterCollection` member.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="dcae3-137">El `SiebelCommand` clase omite el `CommandTimeout`, `DesignTimeVisible`, y `DbTransaction` propiedades.</span><span class="sxs-lookup"><span data-stu-id="dcae3-137">The `SiebelCommand` class ignores the `CommandTimeout`, `DesignTimeVisible`, and `DbTransaction` properties.</span></span>  
  
## <a name="supported-methods"></a><span data-ttu-id="dcae3-138">Métodos admitidos</span><span class="sxs-lookup"><span data-stu-id="dcae3-138">Supported Methods</span></span>  
 <span data-ttu-id="dcae3-139">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] admite las siguientes `DbCommand` *protegido* métodos:</span><span class="sxs-lookup"><span data-stu-id="dcae3-139">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports the following `DbCommand`*protected* methods:</span></span>  
  
|<span data-ttu-id="dcae3-140">Nombre</span><span class="sxs-lookup"><span data-stu-id="dcae3-140">Name</span></span>|<span data-ttu-id="dcae3-141">Description</span><span class="sxs-lookup"><span data-stu-id="dcae3-141">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="dcae3-142">**CreateDbParameter**</span><span class="sxs-lookup"><span data-stu-id="dcae3-142">**CreateDbParameter**</span></span>|<span data-ttu-id="dcae3-143">Crea un nuevo `DbParameter` instancia.</span><span class="sxs-lookup"><span data-stu-id="dcae3-143">Creates a new `DbParameter` instance.</span></span>|  
|<span data-ttu-id="dcae3-144">**ExecuteDbDataReader**</span><span class="sxs-lookup"><span data-stu-id="dcae3-144">**ExecuteDbDataReader**</span></span>|<span data-ttu-id="dcae3-145">Esto ejecuta los comandos SELECT y EXEC y devuelve un `DbDataReader`.</span><span class="sxs-lookup"><span data-stu-id="dcae3-145">This executes the SELECT and EXEC commands and returns a `DbDataReader`.</span></span>|  
  
 <span data-ttu-id="dcae3-146">`SiebelCommand`también admite las siguientes `DbCommand` *público* métodos:</span><span class="sxs-lookup"><span data-stu-id="dcae3-146">`SiebelCommand` also supports the following `DbCommand`*public* methods:</span></span>  
  
|<span data-ttu-id="dcae3-147">Nombre</span><span class="sxs-lookup"><span data-stu-id="dcae3-147">Name</span></span>|<span data-ttu-id="dcae3-148">Description</span><span class="sxs-lookup"><span data-stu-id="dcae3-148">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="dcae3-149">**CreateParameter**</span><span class="sxs-lookup"><span data-stu-id="dcae3-149">**CreateParameter**</span></span>|<span data-ttu-id="dcae3-150">Crea un nuevo `DbParameter` a través de la instancia`CreateDbParameter().`</span><span class="sxs-lookup"><span data-stu-id="dcae3-150">Creates a new `DbParameter` instance through `CreateDbParameter().`</span></span>|  
|<span data-ttu-id="dcae3-151">**ExecuteReader**</span><span class="sxs-lookup"><span data-stu-id="dcae3-151">**ExecuteReader**</span></span>|<span data-ttu-id="dcae3-152">Ejecuta `CommandText` contra la `Connection` y devuelve `DbDataReader` a través de `ExecuteDbDataReader()`.</span><span class="sxs-lookup"><span data-stu-id="dcae3-152">Executes `CommandText` against the `Connection` and returns `DbDataReader` through `ExecuteDbDataReader()`.</span></span>|  
|<span data-ttu-id="dcae3-153">**Preparar**</span><span class="sxs-lookup"><span data-stu-id="dcae3-153">**Prepare**</span></span>|<span data-ttu-id="dcae3-154">Este código analiza la `CommandText` y compila el árbol de análisis de comando SQL.</span><span class="sxs-lookup"><span data-stu-id="dcae3-154">This parses the `CommandText` and builds the SQL command parse tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dcae3-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcae3-155">See Also</span></span>  
 [<span data-ttu-id="dcae3-156">Extender Interfaces de ADO.NET con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="dcae3-156">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)