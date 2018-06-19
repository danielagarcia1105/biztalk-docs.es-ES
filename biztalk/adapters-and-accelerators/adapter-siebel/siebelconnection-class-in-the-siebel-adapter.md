---
title: Clase SiebelConnection en el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, SiebelConnection
- SiebelConnection, supported properties and methods
- SiebelConnection
ms.assetid: 661d9876-4c14-4748-b05f-cc4fd1c4ebcf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fc99c2e3f019f2ddf88647b0faeb7e41644fd0e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222340"
---
# <a name="siebelconnection-class-in-the-siebel-adapter"></a><span data-ttu-id="094d3-102">Clase SiebelConnection en el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="094d3-102">SiebelConnection class in the Siebel adapter</span></span>
<span data-ttu-id="094d3-103">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] tiene acceso a subyacente [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] `Binding`, `ConnectionFactory`, y `Channel` para conectarse al sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="094d3-103">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] accesses the underlying [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]`Binding`, the `ConnectionFactory`, and `Channel` to connect to the Siebel system.</span></span> <span data-ttu-id="094d3-104">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] implementa el `DbConnection` características de la clase para admitir los anteriores.</span><span class="sxs-lookup"><span data-stu-id="094d3-104">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] implements the `DbConnection` class to support the preceding features.</span></span>  
  
 <span data-ttu-id="094d3-105">Mediante una instancia de `Microsoft.Data.SiebelClient.SiebelClientFactory`, un programa cliente puede obtener una instancia de la `System.Data.Common.DbConnection` clase para conectarse al sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="094d3-105">Using an instance of `Microsoft.Data.SiebelClient.SiebelClientFactory`, a client program can obtain an instance of the `System.Data.Common.DbConnection` class to connect to the Siebel system.</span></span>  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbConnection connection = factory.CreateConnection();  
```  
  
 <span data-ttu-id="094d3-106">También se puede usar el siguiente método para crear una conexión:</span><span class="sxs-lookup"><span data-stu-id="094d3-106">Alternatively, the following approach can be used to create a connection:</span></span>  
  
```  
  
SiebelConnection connection = new SiebelConnection();  
connection.ConnectionString = connectionString;  
```  
  
 <span data-ttu-id="094d3-107">El `SiebelConnection` clase hereda de `DbConnection`.</span><span class="sxs-lookup"><span data-stu-id="094d3-107">The `SiebelConnection` class inherits from `DbConnection`.</span></span> <span data-ttu-id="094d3-108">Se encuentra en el espacio de nombres `Microsoft.Data.SiebelClient`.</span><span class="sxs-lookup"><span data-stu-id="094d3-108">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="094d3-109">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="094d3-109">Supported Properties</span></span>  
 <span data-ttu-id="094d3-110">El `SiebelConnection` clase admite las siguientes `DbConnection` propiedades.</span><span class="sxs-lookup"><span data-stu-id="094d3-110">The `SiebelConnection` class supports the following `DbConnection` properties.</span></span>  
  
|<span data-ttu-id="094d3-111">Nombre</span><span class="sxs-lookup"><span data-stu-id="094d3-111">Name</span></span>|<span data-ttu-id="094d3-112">Get/Set.</span><span class="sxs-lookup"><span data-stu-id="094d3-112">Get/Set</span></span>|<span data-ttu-id="094d3-113">Description</span><span class="sxs-lookup"><span data-stu-id="094d3-113">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="094d3-114">**ConnectionString**</span><span class="sxs-lookup"><span data-stu-id="094d3-114">**ConnectionString**</span></span>|<span data-ttu-id="094d3-115">Get y Set</span><span class="sxs-lookup"><span data-stu-id="094d3-115">Get and Set</span></span>|<span data-ttu-id="094d3-116">Obtiene o establece la cadena que se usa para abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="094d3-116">Gets or sets the string used to open the connection.</span></span>|  
|<span data-ttu-id="094d3-117">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="094d3-117">**Database**</span></span>|<span data-ttu-id="094d3-118">Obtener</span><span class="sxs-lookup"><span data-stu-id="094d3-118">Get</span></span>|<span data-ttu-id="094d3-119">Obtiene el nombre de la base de datos actual una vez que se abre una conexión o el nombre de base de datos especificado en la cadena de conexión antes de abrirse la conexión.</span><span class="sxs-lookup"><span data-stu-id="094d3-119">Gets the name of the current database after a connection is opened, or the database name specified in the connection string before the connection is opened.</span></span> <span data-ttu-id="094d3-120">Debe ser el nombre del repositorio de Siebel.</span><span class="sxs-lookup"><span data-stu-id="094d3-120">This should be the Siebel repository name.</span></span>|  
|<span data-ttu-id="094d3-121">**DataSource**</span><span class="sxs-lookup"><span data-stu-id="094d3-121">**DataSource**</span></span>|<span data-ttu-id="094d3-122">Obtener</span><span class="sxs-lookup"><span data-stu-id="094d3-122">Get</span></span>|<span data-ttu-id="094d3-123">Obtiene el nombre de la puerta de enlace de Siebel para esta conexión.</span><span class="sxs-lookup"><span data-stu-id="094d3-123">Gets the name of the Siebel gateway for this connection.</span></span>|  
|<span data-ttu-id="094d3-124">**ServerVersion**</span><span class="sxs-lookup"><span data-stu-id="094d3-124">**ServerVersion**</span></span>|<span data-ttu-id="094d3-125">Obtener</span><span class="sxs-lookup"><span data-stu-id="094d3-125">Get</span></span>|<span data-ttu-id="094d3-126">En la versión actual de [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], esta propiedad devuelve un valor codificado de forma rígida, que no representa la versión real del servidor Siebel.</span><span class="sxs-lookup"><span data-stu-id="094d3-126">In the current version of [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], this property returns a hard-coded value, which does not represent the actual version of the Siebel server.</span></span>|  
|<span data-ttu-id="094d3-127">**State**</span><span class="sxs-lookup"><span data-stu-id="094d3-127">**State**</span></span>|<span data-ttu-id="094d3-128">Obtener</span><span class="sxs-lookup"><span data-stu-id="094d3-128">Get</span></span>|<span data-ttu-id="094d3-129">Obtiene una cadena que describe el estado de la conexión.</span><span class="sxs-lookup"><span data-stu-id="094d3-129">Gets a string that describes the state of the connection.</span></span> <span data-ttu-id="094d3-130">Este archivo puede contener tres valores posibles: abierto, ROTO o cerrado.</span><span class="sxs-lookup"><span data-stu-id="094d3-130">This can contain three possible values: OPEN, BROKEN, or CLOSED.</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="094d3-131">Métodos admitidos</span><span class="sxs-lookup"><span data-stu-id="094d3-131">Supported Methods</span></span>  
 <span data-ttu-id="094d3-132">El `SiebelConnection` clase admite las siguientes `DbConnection` métodos.</span><span class="sxs-lookup"><span data-stu-id="094d3-132">The `SiebelConnection` class supports the following `DbConnection` methods.</span></span>  
  
|<span data-ttu-id="094d3-133">Nombre</span><span class="sxs-lookup"><span data-stu-id="094d3-133">Name</span></span>|<span data-ttu-id="094d3-134">Description</span><span class="sxs-lookup"><span data-stu-id="094d3-134">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="094d3-135">**CreateDbCommand**</span><span class="sxs-lookup"><span data-stu-id="094d3-135">**CreateDbCommand**</span></span>|<span data-ttu-id="094d3-136">Este método protegido proporciona una nueva instancia de DbCommand.</span><span class="sxs-lookup"><span data-stu-id="094d3-136">This protected method provides a new DbCommand instance.</span></span>|  
|<span data-ttu-id="094d3-137">**ChangeDatabase**</span><span class="sxs-lookup"><span data-stu-id="094d3-137">**ChangeDatabase**</span></span>|<span data-ttu-id="094d3-138">Este método público no se admite e iniciará una excepción si se llama.</span><span class="sxs-lookup"><span data-stu-id="094d3-138">This public method is not supported, and will throw an exception if called.</span></span>|  
|<span data-ttu-id="094d3-139">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="094d3-139">**Open**</span></span>|<span data-ttu-id="094d3-140">Abre una conexión con el sistema Siebel mediante la creación de un canal WCF.</span><span class="sxs-lookup"><span data-stu-id="094d3-140">Opens a connection with the Siebel system by creating a WCF channel.</span></span>|  
|<span data-ttu-id="094d3-141">**Cerrar**</span><span class="sxs-lookup"><span data-stu-id="094d3-141">**Close**</span></span>|<span data-ttu-id="094d3-142">Cierra una conexión con el sistema Siebel, el cierre de un canal WCF.</span><span class="sxs-lookup"><span data-stu-id="094d3-142">Closes a connection with the Siebel system by closing a WCF channel.</span></span>|  
|<span data-ttu-id="094d3-143">**CreateCommand**</span><span class="sxs-lookup"><span data-stu-id="094d3-143">**CreateCommand**</span></span>|<span data-ttu-id="094d3-144">Crea un objeto de comando.</span><span class="sxs-lookup"><span data-stu-id="094d3-144">Creates a command object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="094d3-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="094d3-145">See Also</span></span>  
 [<span data-ttu-id="094d3-146">Extender Interfaces de ADO.NET con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="094d3-146">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)