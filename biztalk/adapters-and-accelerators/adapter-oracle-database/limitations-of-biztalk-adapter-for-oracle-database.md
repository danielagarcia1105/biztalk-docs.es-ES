---
title: Limitaciones del adaptador de BizTalk para Oracle Database | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, limitations of
ms.assetid: eab4ddea-f986-43c2-82bb-b9fe37961a5b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8138449cf3af067c9a76848f203c7e1809f6adbc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986613"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="75089-102">Limitaciones del adaptador de BizTalk para Oracle Database</span><span class="sxs-lookup"><span data-stu-id="75089-102">Limitations of BizTalk Adapter for Oracle Database</span></span>
## <a name="general"></a><span data-ttu-id="75089-103">General</span><span class="sxs-lookup"><span data-stu-id="75089-103">General</span></span>  
 <span data-ttu-id="75089-104">Lo siguiente es limitaciones para conocidas el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="75089-104">The following are known limitations for the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span></span>  
  
- <span data-ttu-id="75089-105">Salvo algunas excepciones, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con la versión anterior de los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="75089-105">Barring some exceptions, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is compatible with the previous release of the adapters.</span></span> <span data-ttu-id="75089-106">Para obtener una lista de los cambios que ha sucedido desde la última versión, consulte [características clave en el adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="75089-106">For a list of changes that has happened since the last release, see [Key Features in BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md).</span></span>  
  
- <span data-ttu-id="75089-107">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tipos de XML.</span><span class="sxs-lookup"><span data-stu-id="75089-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support XML Types.</span></span>  
  
- <span data-ttu-id="75089-108">La operación SQLEXECUTE no devuelve los valores de salida o en los parámetros OUT procedimientos, funciones o los paquetes.</span><span class="sxs-lookup"><span data-stu-id="75089-108">The SQLEXECUTE operation does not return values for OUT or IN OUT parameters to procedures, functions, or packages.</span></span> <span data-ttu-id="75089-109">Por este motivo, debe invocar procedimientos, funciones y paquetes mediante el uso de las operaciones dedicadas que los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone para que estos artefactos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="75089-109">For this reason, you must invoke procedures, functions, and packages by using the dedicated operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes for these Oracle artifacts.</span></span>  
  
- <span data-ttu-id="75089-110">Al recuperar datos de la base de datos de Oracle mediante el proxy de programación, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] deserializar los mensajes XML que tengan más de 65536 nodos.</span><span class="sxs-lookup"><span data-stu-id="75089-110">When retrieving data from the Oracle database using proxy programming, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not deserialize XML messages that have more than 65536 nodes.</span></span> <span data-ttu-id="75089-111">Asegúrese de que el mensaje de respuesta tiene nodos menor o igual a 65536.</span><span class="sxs-lookup"><span data-stu-id="75089-111">Make sure the response message has nodes less than or equal to 65536.</span></span> <span data-ttu-id="75089-112">Puede evitar esta limitación si modifica el archivo app.config para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="75089-112">You can work around this limitation by modifying the app.config file for your application.</span></span> <span data-ttu-id="75089-113">Para obtener instrucciones, consulte [solucionar problemas de funcionamiento con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="75089-113">For instructions, see [Troubleshoot operational issues with the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md).</span></span>  
  
- <span data-ttu-id="75089-114">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] cadenas de entrada toma y construye los comandos SQL que se ejecutan mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="75089-114">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] takes input strings and constructs SQL commands that are then executed by the adapter.</span></span> <span data-ttu-id="75089-115">Sin embargo, la cadena de entrada podría contener otros comandos SQL que también se ejecutan y pueden provocar errores en el contrato de operación.</span><span class="sxs-lookup"><span data-stu-id="75089-115">However, the input string might contain other SQL commands that also get executed and might break the operation contract.</span></span>  
  
   <span data-ttu-id="75089-116">Considere un escenario donde el adaptador proporciona un REF CURSOR de entrada a un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="75089-116">Consider a scenario where the adapter provides an input REF CURSOR to a stored procedure.</span></span> <span data-ttu-id="75089-117">En este escenario, el cliente del adaptador debe proporcionar un comando que, cuando se ejecuta, obtiene el REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="75089-117">In such a scenario, the adapter client must provide a command that, when executed, obtains the REF CURSOR.</span></span> <span data-ttu-id="75089-118">A continuación, el adaptador pasa el REF CURSOR en el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="75089-118">The adapter then passes on the REF CURSOR to the stored procedure.</span></span> <span data-ttu-id="75089-119">Sin embargo, si el comando para obtener el REF CURSOR realiza algunas modificaciones adicionales en la base de datos, el contrato de operación para ejecutar el procedimiento almacenado se interrumpe.</span><span class="sxs-lookup"><span data-stu-id="75089-119">However, if the command for obtaining the REF CURSOR performs some additional modifications to the database, the operation contract for executing the stored procedure is broken.</span></span>  
  
- <span data-ttu-id="75089-120">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite hasta dos niveles de anidamiento de UDT.</span><span class="sxs-lookup"><span data-stu-id="75089-120">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports UDT nesting only up to two levels.</span></span>  
  
- <span data-ttu-id="75089-121">Al usar los adaptadores con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], si las credenciales en el WCF-custom puerto son incorrectos, no se procesan los mensajes de solicitud de envío.</span><span class="sxs-lookup"><span data-stu-id="75089-121">When using the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="75089-122">Después de especificar las credenciales correctas, el mensaje se envía a la base de datos de Oracle y se recibe una respuesta.</span><span class="sxs-lookup"><span data-stu-id="75089-122">After you specify the correct credentials, the message is sent to the Oracle database and a response is received.</span></span> <span data-ttu-id="75089-123">Sin embargo, el mensaje de respuesta no está disponible para el puerto de salida.</span><span class="sxs-lookup"><span data-stu-id="75089-123">However, the response message is not available to the out port.</span></span> <span data-ttu-id="75089-124">En estos escenarios, debe reiniciar la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="75089-124">In such scenarios, you may need to restart the host instance.</span></span>  
  
- <span data-ttu-id="75089-125">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite el tipo de datos BFILE dentro de los tipos complejos (como registro tipo tabla tipo, UDT y VARRAY).</span><span class="sxs-lookup"><span data-stu-id="75089-125">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support the BFILE data type inside complex types (such as RECORD type, TABLE type, UDT, and VARRAY).</span></span>  
  
- <span data-ttu-id="75089-126">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tipos definidos por el usuario (UDT) que tienen referencias circulares.</span><span class="sxs-lookup"><span data-stu-id="75089-126">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support User-Defined Types (UDTs) that have circular references.</span></span>  
  
- <span data-ttu-id="75089-127">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no los registros de soporte técnico que contienen campos de tipo de tablas de PL/SQL del tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="75089-127">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support records that contain fields of type PL/SQL tables of RECORD type.</span></span>  
  
- <span data-ttu-id="75089-128">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no permiten a los clientes establecer el valor del primer elemento en un VARRAY en NULL.</span><span class="sxs-lookup"><span data-stu-id="75089-128">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not enable clients to set the value of the first element in a VARRAY to NULL.</span></span>  
  
- <span data-ttu-id="75089-129">Excepto para las tablas de PL/SQL, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite los UDT se definen dentro de un paquete.</span><span class="sxs-lookup"><span data-stu-id="75089-129">Except for PL/SQL tables, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that are defined inside a package.</span></span>  
  
## <a name="limitations-due-to-odpnet"></a><span data-ttu-id="75089-130">Limitaciones debido a ODP.NET</span><span class="sxs-lookup"><span data-stu-id="75089-130">Limitations due to ODP.NET</span></span>  
 <span data-ttu-id="75089-131">Lo siguiente es limitaciones para conocidas el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] debido a la limitación de ODP.NET:</span><span class="sxs-lookup"><span data-stu-id="75089-131">The following are known limitations for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] due to the limitation of ODP.NET:</span></span>  
  
- <span data-ttu-id="75089-132">Para los tipos de datos de Oracle que toman los valores decimales, ODP.NET no produce una excepción si el valor de entrada contiene caracteres alfabéticos.</span><span class="sxs-lookup"><span data-stu-id="75089-132">For Oracle data types that take decimal values, ODP.NET does not throw an exception if the input value contains alphabetic characters.</span></span> <span data-ttu-id="75089-133">Dado que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa ODP.NET para interactuar con la base de datos de Oracle, el adaptador demasiado no producir una excepción al pasar los caracteres alfabéticos.</span><span class="sxs-lookup"><span data-stu-id="75089-133">Because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses ODP.NET to interface with the Oracle database, the adapter too does not throw an exception when passing alphabetic characters.</span></span> <span data-ttu-id="75089-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="75089-134">For example:</span></span>  
  
  -   <span data-ttu-id="75089-135">Pasar un valor "54r" para una operación de inserción no produce una excepción; en su lugar, se inserta el valor "54".</span><span class="sxs-lookup"><span data-stu-id="75089-135">Passing a value “54r” for an insert operation does not throw an exception; the value “54” is inserted instead.</span></span>  
  
  -   <span data-ttu-id="75089-136">Pasar un valor "r54" para una operación de inserción no produce una excepción; en su lugar, se inserta el valor "0".</span><span class="sxs-lookup"><span data-stu-id="75089-136">Passing a value “r54” for an insert operation does not throw an exception; the value “0” is inserted instead.</span></span>  
  
- <span data-ttu-id="75089-137">Debido a una limitación de ODP.NET la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite el uso de procedimientos sobrecargados con cursores REF cursor de fuertemente tipadas y débilmente tipada.</span><span class="sxs-lookup"><span data-stu-id="75089-137">Because of an ODP.NET limitation, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support the use of overloaded procedures using strongly-typed and weakly-typed REF CURSORS.</span></span> <span data-ttu-id="75089-138">Internamente, el adaptador trata los CURSORES REF fuertemente tipadas y débilmente tipada como simplemente cursores REF cursor.</span><span class="sxs-lookup"><span data-stu-id="75089-138">Internally, the adapter treats both the strongly-typed and weakly-typed REF CURSORS as just REF CURSORS.</span></span>  
  
- <span data-ttu-id="75089-139">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tablas de PL/SQL que no están indizadas por un campo numérico.</span><span class="sxs-lookup"><span data-stu-id="75089-139">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support PL/SQL tables that are not indexed by a numeric field.</span></span>  
  
- <span data-ttu-id="75089-140">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite matrices asociativas que no contienen ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="75089-140">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support associative arrays that do not contain any element.</span></span>  
  
- <span data-ttu-id="75089-141">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite los UDT que contienen el tipo de datos de marca de tiempo con atributos de zona horaria local (TimeStampLTZ).</span><span class="sxs-lookup"><span data-stu-id="75089-141">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that contain the TimeStamp data type with local time zone attributes (TimeStampLTZ).</span></span>  
  
- <span data-ttu-id="75089-142">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite los UDT que contienen un "."</span><span class="sxs-lookup"><span data-stu-id="75089-142">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that contain a “.”</span></span> <span data-ttu-id="75089-143">(punto) en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="75089-143">(period) in their names.</span></span>  
  
- <span data-ttu-id="75089-144">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite los UDT que contienen los tipos de datos BLOB, CLOB y NCLOB como un parámetro IN OUT.</span><span class="sxs-lookup"><span data-stu-id="75089-144">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that contain BLOB, CLOB, and NCLOB data types as an IN OUT parameter.</span></span>  
  
- <span data-ttu-id="75089-145">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite Varray de Varray de los siguientes tipos simples: BFILE, IntervalDS, IntervalYM, TimeStampLTZ y TimeStampTZ.</span><span class="sxs-lookup"><span data-stu-id="75089-145">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support Varray of Varray of the following simple types: BFILE, IntervalDS, IntervalYM, TimeStampLTZ, and TimeStampTZ.</span></span>  
  
- <span data-ttu-id="75089-146">Debido a la limitación de matrices asociativas, tablas de PL/SQL de registros que contienen cualquiera de los siguientes tipos de datos o tablas de PL/SQL no se admiten en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="75089-146">Due to the limitation of associative arrays, PL/SQL tables or PL/SQL tables of records that contain any of the following data types are not supported in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span></span>  
  
  -   <span data-ttu-id="75089-147">BFILE</span><span class="sxs-lookup"><span data-stu-id="75089-147">BFILE</span></span>  
  
  -   <span data-ttu-id="75089-148">BLOB</span><span class="sxs-lookup"><span data-stu-id="75089-148">BLOB</span></span>  
  
  -   <span data-ttu-id="75089-149">CLOB</span><span class="sxs-lookup"><span data-stu-id="75089-149">CLOB</span></span>  
  
  -   <span data-ttu-id="75089-150">IntervalDS</span><span class="sxs-lookup"><span data-stu-id="75089-150">IntervalDS</span></span>  
  
  -   <span data-ttu-id="75089-151">IntervalYM</span><span class="sxs-lookup"><span data-stu-id="75089-151">IntervalYM</span></span>  
  
  -   <span data-ttu-id="75089-152">Long</span><span class="sxs-lookup"><span data-stu-id="75089-152">Long</span></span>  
  
  -   <span data-ttu-id="75089-153">NCLOB</span><span class="sxs-lookup"><span data-stu-id="75089-153">NCLOB</span></span>  
  
  -   <span data-ttu-id="75089-154">RowID</span><span class="sxs-lookup"><span data-stu-id="75089-154">RowID</span></span>  
  
  -   <span data-ttu-id="75089-155">TimeStamp</span><span class="sxs-lookup"><span data-stu-id="75089-155">TimeStamp</span></span>  
  
  -   <span data-ttu-id="75089-156">TimeStampLTZ</span><span class="sxs-lookup"><span data-stu-id="75089-156">TimeStampLTZ</span></span>  
  
  -   <span data-ttu-id="75089-157">TimeStampTZ</span><span class="sxs-lookup"><span data-stu-id="75089-157">TimeStampTZ</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75089-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="75089-158">See Also</span></span>  
 [<span data-ttu-id="75089-159">Definición del adaptador de BizTalk para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="75089-159">Understand the BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)