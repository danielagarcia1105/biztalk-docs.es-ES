---
title: Los esquemas de mensajes para los cursores REF cursor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF CURSORS, message schemas for
- IN REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: b62e7a9f-278c-41b3-90f0-2f621a34327b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e41359bd9fa7a54a68de49bfe115ca7c563dfdb3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979021"
---
# <a name="message-schemas-for-ref-cursors"></a><span data-ttu-id="8b25f-102">Esquemas de mensaje para cursores REF cursor</span><span class="sxs-lookup"><span data-stu-id="8b25f-102">Message Schemas for REF CURSORS</span></span>
<span data-ttu-id="8b25f-103">Un REF CURSOR es un tipo de datos de Oracle PL/SQL que representa un puntero a un conjunto de resultados en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8b25f-103">A REF CURSOR is an Oracle PL/SQL data type that represents a pointer to a result set in the Oracle database.</span></span> <span data-ttu-id="8b25f-104">Tipos REF CURSOR habilitar la entrada y salida de transmisión por secuencias de datos y son ideales para transferir grandes cantidades de datos hacia y desde un bloque de código PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="8b25f-104">REF CURSOR types enable input and output streaming of data and are ideal for transferring large amounts of data to and from a PL/SQL code block.</span></span> [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="8b25f-105"> proporciona compatibilidad para pasar parámetros REF CURSOR fuertemente tipadas y débilmente tipada a funciones y los procedimientos de PL/SQL ALEJAR y los parámetros OUT en.</span><span class="sxs-lookup"><span data-stu-id="8b25f-105"> provides support for passing strongly-typed and weakly-typed REF CURSOR parameters to PL/SQL procedures and functions as IN, OUT and IN OUT parameters.</span></span>  
  
 <span data-ttu-id="8b25f-106">En la base de datos de Oracle, puede ser un tipo REF CURSOR fuertemente tipada o débilmente tipada:</span><span class="sxs-lookup"><span data-stu-id="8b25f-106">In the Oracle database, a REF CURSOR type can be either strongly-typed or weakly-typed:</span></span>  
  
- <span data-ttu-id="8b25f-107">Fuertemente tipado REF CURSOR se declara con una cláusula de valor DEVUELTA como `TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`.</span><span class="sxs-lookup"><span data-stu-id="8b25f-107">A strongly-typed REF CURSOR is declared with a RETURN clause as in `TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`.</span></span> <span data-ttu-id="8b25f-108">Una variable de REF CURSOR fuertemente tipado solo puede representar un conjunto de resultados que contiene datos que coincide con el tipo con el que se declara su tipo REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8b25f-108">A strongly-typed REF CURSOR variable can only represent a result set that contains data that matches the type with which its REF CURSOR type is declared.</span></span> <span data-ttu-id="8b25f-109">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] devuelve un conjunto de REF CURSOR fuertemente tipados fuertemente tipada de resultados.</span><span class="sxs-lookup"><span data-stu-id="8b25f-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] returns a strongly-typed result set for a strongly-typed REF CURSOR.</span></span>  
  
- <span data-ttu-id="8b25f-110">Débilmente tipada REF CURSOR se declara sin una cláusula de valor DEVUELTA como `TYPE WeakCurType IS REF CURSOR;`.</span><span class="sxs-lookup"><span data-stu-id="8b25f-110">A weakly-typed REF CURSOR is declared without a RETURN clause as in `TYPE WeakCurType IS REF CURSOR;`.</span></span> <span data-ttu-id="8b25f-111">Oracle ofrece también un tipo especial de REF CURSOR llamado SYS_REFCURSOR que puede usarse para declarar variables débilmente tipada de REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8b25f-111">Oracle also provides a special REF CURSOR type called SYS_REFCURSOR that can be used to declare weakly-typed REF CURSOR variables.</span></span> <span data-ttu-id="8b25f-112">Las variables débilmente tipada de REF CURSOR pueden representar un conjunto de resultados que contiene cualquier tipo de datos de fila.</span><span class="sxs-lookup"><span data-stu-id="8b25f-112">Weakly-typed REF CURSOR variables can represent a result set that contains any kind of row data.</span></span> <span data-ttu-id="8b25f-113">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] devuelve un conjunto de resultados débilmente tipada de registros genéricos para débilmente tipada REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8b25f-113">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] returns a weakly-typed result set of generic records for a weakly-typed REF CURSOR.</span></span>  
  
## <a name="in-ref-cursor-parameters"></a><span data-ttu-id="8b25f-114">EN parámetros REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="8b25f-114">IN REF CURSOR Parameters</span></span>  
 <span data-ttu-id="8b25f-115">No hay ninguna API ODP.NET para crear un REF CURSOR en el servidor de Oracle, por lo que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no puede proporcionar la capacidad de un programa cliente crear y mantener las variables de REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8b25f-115">There is no ODP.NET API to create a REF CURSOR on the Oracle server, so the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] cannot provide the capability for a client program to create and maintain REF CURSOR variables.</span></span>  
  
 <span data-ttu-id="8b25f-116">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] , sin embargo, permitir que un cliente pasar parámetros REF CURSOR de IN a funciones o procedimientos almacenados mediante la especificación de un bloque de código PL/SQL que devuelve un REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8b25f-116">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does, however, enable a client to pass IN REF CURSOR parameters to functions or stored procedures by specifying a block of PL/SQL code that returns a REF CURSOR.</span></span> <span data-ttu-id="8b25f-117">El adaptador utiliza este código para crear y abrir una variable de REF CURSOR en el servidor de Oracle. a continuación, llama a la función o el uso de esta variable como parámetro en el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="8b25f-117">The adapter uses this code to create and OPEN a REF CURSOR variable on the Oracle server; it then calls the function or stored procedure using this variable as the IN parameter.</span></span>  
  
 <span data-ttu-id="8b25f-118">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] representa parámetros IN REF CURSOR como cadenas que contienen el bloque de código PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="8b25f-118">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents IN REF CURSOR parameters as strings that contain the PL/SQL code block.</span></span> <span data-ttu-id="8b25f-119">Dentro de este bloque, se especifica la ubicación del CURSOR REF con un signo de interrogación (?).</span><span class="sxs-lookup"><span data-stu-id="8b25f-119">Within this block, the location of the REF CURSOR is specified with a question mark (?).</span></span> <span data-ttu-id="8b25f-120">El bloque de código PL/SQL puede contener una instrucción OPEN FOR que contiene una consulta SQL; o puede contener una llamada de función o procedimiento en la que se devuelven un REF CURSOR abierto en un parámetro OUT.</span><span class="sxs-lookup"><span data-stu-id="8b25f-120">The PL/SQL code block can contain an OPEN-FOR statement that contains a SQL query; or it can contain a function or procedure call in which an opened REF CURSOR is returned in an OUT parameter.</span></span>  
  
 <span data-ttu-id="8b25f-121">El siguiente muestra cómo especificar una en REF CURSOR mediante una llamada a un procedimiento almacenado o función para abrir el REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8b25f-121">The following shows how to specify an IN REF CURSOR by calling a stored procedure or function to open the REF CURSOR.</span></span>  
  
```  
<[IN_REF_CURSOR_PARAM_NAME]>begin [SP_NAME]([SP_PARAMS...], ?, [SP_PARAMS...]); end;</[IN_REF_CURSOR_PARAM_NAME]>  
  
Example:  
<EMP_RC>begin GETEMP(1, ?); end; </EMP_RC>  
```  
  
 <span data-ttu-id="8b25f-122">El siguiente muestra cómo especificar un IN REF CURSOR utilizando una consulta SELECT para abrir el REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8b25f-122">The following shows how to specify an IN REF CURSOR by using a SELECT query to open the REF CURSOR.</span></span>  
  
```  
<IN_REF_CURSOR_PARAM_NAME>begin open ? for select [FIELD_NAMES] from [TABLE_NAME]; end;</IN_REF_CURSOR_PARAM_NAME>  
  
Example:  
<EMP_RC>begin open ? for select * from EMP; end;</EMP_RC>  
```  
  
## <a name="out-ref-cursor-parameters"></a><span data-ttu-id="8b25f-123">LOS parámetros REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="8b25f-123">OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="8b25f-124">SALIDA de REF CURSOR parámetros se devuelven como conjuntos de resultados fuertemente tipada o débilmente tipada.</span><span class="sxs-lookup"><span data-stu-id="8b25f-124">OUT REF CURSOR parameters are returned as either strongly-typed or weakly-typed result sets.</span></span> <span data-ttu-id="8b25f-125">El tipo de conjunto de resultados devuelto depende de si el parámetro REF CURSOR se declara como fuertemente tipados o débilmente tipada REF CURSOR en la definición de función o procedimiento almacenada en el servidor de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8b25f-125">The type of the result set returned depends on whether the REF CURSOR parameter is declared as a strongly-typed or weakly-typed REF CURSOR in the stored procedure or function definition on the Oracle server.</span></span> <span data-ttu-id="8b25f-126">Se devuelve un conjunto de resultados fuertemente tipado para parámetros REF CURSOR fuertemente tipados y se devuelve un conjunto de resultados débilmente tipada para débilmente tipada parámetros REF CURSOR (por ejemplo, los parámetros se declaran con un tipo SYS_REFCURSOR).</span><span class="sxs-lookup"><span data-stu-id="8b25f-126">A strongly-typed result set is returned for strongly-typed REF CURSOR parameters and a weakly-typed result set is returned for weakly-typed REF CURSOR parameters (for example, parameters declared with a SYS_REFCURSOR type).</span></span>  
  
 <span data-ttu-id="8b25f-127">A continuación muestra el código XML para un parámetro de salida de REF CURSOR fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="8b25f-127">The following shows the XML for a strongly-typed OUT REF CURSOR parameter.</span></span>  
  
```  
<[PARAM_NAME]>  
 <[PARAM_NAME]RECORD>  
  <[COL1_NAME]>value1</[COL1_NAME]>  
  <[COL2_NAME]>value2</[COL2_NAME]>  
  ...  
 </[PARAM_NAME]RECORD>  
</[PARAM_NAME]>  
  
[PARAM_NAME] = OUT REF CURSOR parameter name; for example, EMP_REFCURSOR  
[COL_NAME] = Name of a column in the REF CURSOR type; for example, Name.  
```  
  
 <span data-ttu-id="8b25f-128">A continuación muestra el código XML para un parámetro de salida de REF CURSOR débilmente tipada.</span><span class="sxs-lookup"><span data-stu-id="8b25f-128">The following shows the XML for a weakly-typed OUT REF CURSOR parameter.</span></span>  
  
```  
<[PARAM_NAME]>  
 <GenRecordRow xmlns="oracledb">  
  <GenRecordColumn>  
   <ColumnName>COL_NAME</ColumnName>  
   <ColumnValue>COL_VALUE</ColumnValue>  
   <ColumnType>COL_TYPE</ColumnType>  
  </GenRecordColumn>  
  …  
 </GenRecordRow>  
 …  
</[PARAM_NAME]>  
  
[COL_NAME] = Name of column; for example, Name  
[COL_VALUE] = Column value; for example, Scott  
[COL_TYPE] = Column data type; for example, System.String  
```  
  
## <a name="in-out-ref-cursor-parameters"></a><span data-ttu-id="8b25f-129">EN los parámetros REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="8b25f-129">IN OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="8b25f-130">Dado que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] modela parámetros IN REF CURSOR como cadenas y los parámetros de salida de REF CURSOR como tipos complejos, que no admite un tipo único para un parámetro OUT en REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8b25f-130">Because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] models IN REF CURSOR parameters as strings and OUT REF CURSOR parameters as complex types, it cannot support a single type for an IN OUT REF CURSOR parameter.</span></span> <span data-ttu-id="8b25f-131">Por este motivo, trata los parámetros OUT en REF CURSOR como dos parámetros distintos: un parámetro IN en el mensaje de solicitud y un parámetro OUT en el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="8b25f-131">For this reason, it treats IN OUT REF CURSOR parameters as two different parameters: an IN parameter in the request message and an OUT parameter in the response message.</span></span>  
  
 <span data-ttu-id="8b25f-132">Para evitar un conflicto de nombres en la programación del modelo de servicio, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] anexa la cadena "_IN" para el parámetro IN en el mensaje de solicitud, por lo que para un parámetro dado denominado [PARAM_NAME], se crean dos parámetros:</span><span class="sxs-lookup"><span data-stu-id="8b25f-132">To avoid a name conflict in service model programming, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] appends the string "_IN" to the IN parameter in the request message so that for a given parameter named [PARAM_NAME], two parameters are created:</span></span>  
  
-   <span data-ttu-id="8b25f-133">_IN [PARAM_NAME] es un parámetro IN REF CURSOR en el procedimiento almacenado o un mensaje de solicitud de función.</span><span class="sxs-lookup"><span data-stu-id="8b25f-133">[PARAM_NAME]_IN is an IN REF CURSOR parameter in the stored procedure or function request message.</span></span> <span data-ttu-id="8b25f-134">Contiene una instrucción de PL/SQL (una consulta select o una llamada de función o procedimiento almacenada) que devuelve un REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8b25f-134">It contains a PL/SQL statement (either a select query or a stored procedure or function call) that returns a REF CURSOR.</span></span>  
  
-   <span data-ttu-id="8b25f-135">[PARAM_NAME] es un parámetro de salida de REF CURSOR en el procedimiento almacenado o un mensaje de respuesta de la función.</span><span class="sxs-lookup"><span data-stu-id="8b25f-135">[PARAM_NAME] is an OUT REF CURSOR parameter in the stored procedure or function response message.</span></span> <span data-ttu-id="8b25f-136">Contiene la salida REF CURSOR como un conjunto de resultados fuertemente tipada o débilmente tipada.</span><span class="sxs-lookup"><span data-stu-id="8b25f-136">It contains the OUT REF CURSOR as a strongly-typed or weakly-typed result set.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b25f-137">El adaptador no admite un procedimiento o función que contiene un parámetro IN denominado _IN [PARAM_NAME] y un parámetro OUT en REF CURSOR denominado [PARAM_NAME].</span><span class="sxs-lookup"><span data-stu-id="8b25f-137">The adapter cannot support a procedure or function that contains an IN parameter named [PARAM_NAME]_IN and an IN OUT REF CURSOR parameter named [PARAM_NAME].</span></span> <span data-ttu-id="8b25f-138">Esto es porque el adaptador espera un parámetro llamado _IN [PARAM_NAME] para representar la entrada para el parámetro REF CURSOR y no se puede especificar ambos parámetros en el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="8b25f-138">This is because the adapter expects a parameter named [PARAM_NAME]_IN to represent the input to the REF CURSOR parameter, and you cannot specify both parameters in the request message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b25f-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b25f-139">See Also</span></span>  
 [<span data-ttu-id="8b25f-140">Mensajes y esquemas de mensaje para el adaptador de BizTalk para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="8b25f-140">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)