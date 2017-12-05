---
title: Functoids de base de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77bc9390-cdb5-42ff-8b28-6265c51c79fc
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63a719299ef6678b9fd38a936d84ba9b1f57a85b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="database-functoids"></a><span data-ttu-id="6fb73-102">Functoids de base de datos</span><span class="sxs-lookup"><span data-stu-id="6fb73-102">Database Functoids</span></span>
<span data-ttu-id="6fb73-103">**Base de datos** functoids extraer datos de una base de datos para su uso en un mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="6fb73-103">**Database** functoids extract data from a database for use in an output instance message.</span></span> 

## <a name="overview"></a><span data-ttu-id="6fb73-104">Información general</span><span class="sxs-lookup"><span data-stu-id="6fb73-104">Overview</span></span>
<span data-ttu-id="6fb73-105">La siguiente es una lista de los **base de datos** functoids y cómo utilizarlas:</span><span class="sxs-lookup"><span data-stu-id="6fb73-105">The following is a list of the **Database** functoids and how you can use them:</span></span>  
  
-   <span data-ttu-id="6fb73-106">**Búsqueda de la base de datos.**</span><span class="sxs-lookup"><span data-stu-id="6fb73-106">**Database Lookup.**</span></span> <span data-ttu-id="6fb73-107">Use la **base de datos de búsqueda** functoid para extraer información de una base de datos y almacenarla como un conjunto de registros de Microsoft ActiveX datos objetos .NET (ADO.NET).</span><span class="sxs-lookup"><span data-stu-id="6fb73-107">Use the **Database Lookup** functoid to extract information from a database and store it as a Microsoft ActiveX Data Objects .NET (ADO.NET) recordset.</span></span> <span data-ttu-id="6fb73-108">Este functoid requiere cuatro parámetros de entrada en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="6fb73-108">This functoid requires four input parameters in the following order:</span></span>  
  
    -   <span data-ttu-id="6fb73-109">Un valor de búsqueda</span><span class="sxs-lookup"><span data-stu-id="6fb73-109">A lookup value</span></span>  
  
    -   <span data-ttu-id="6fb73-110">Una cadena de conexión de base de datos</span><span class="sxs-lookup"><span data-stu-id="6fb73-110">A database connection string</span></span>  
  
    -   <span data-ttu-id="6fb73-111">Un nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="6fb73-111">A table name</span></span>  
  
    -   <span data-ttu-id="6fb73-112">Un nombre de columna para el valor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6fb73-112">A column name for the lookup value.</span></span>  
  
-   <span data-ttu-id="6fb73-113">**Devolución de error.**</span><span class="sxs-lookup"><span data-stu-id="6fb73-113">**Error Return.**</span></span> <span data-ttu-id="6fb73-114">Use la **devolución de Error** functoid para capturar la información de error, como errores de conexión de base de datos, que se producen durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6fb73-114">Use the **Error Return** functoid to capture error information, such as database connection failures, that occur during run time.</span></span> <span data-ttu-id="6fb73-115">Este functoid requiere un parámetro de entrada: un vínculo desde el **base de datos de búsqueda** functoid.</span><span class="sxs-lookup"><span data-stu-id="6fb73-115">This functoid requires one input parameter: a link from the **Database Lookup** functoid.</span></span>  
  
-   <span data-ttu-id="6fb73-116">**Formatear mensaje.**</span><span class="sxs-lookup"><span data-stu-id="6fb73-116">**Format Message.**</span></span> <span data-ttu-id="6fb73-117">Devuelve una cadena formateada y localizada utilizando sustitución de argumentos y, potencialmente, referencias cruzadas a valores e Id.</span><span class="sxs-lookup"><span data-stu-id="6fb73-117">Returns a formatted and localized string using argument substitution and, potentially, ID and value cross-referencing.</span></span>  
  
-   <span data-ttu-id="6fb73-118">**Obtener el identificador de aplicación.**</span><span class="sxs-lookup"><span data-stu-id="6fb73-118">**Get Application ID.**</span></span> <span data-ttu-id="6fb73-119">Recupera un identificador de un objeto de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fb73-119">Retrieves an identifier for an application object.</span></span>  
  
-   <span data-ttu-id="6fb73-120">**Obtener valor de aplicación.**</span><span class="sxs-lookup"><span data-stu-id="6fb73-120">**Get Application Value.**</span></span> <span data-ttu-id="6fb73-121">Recupera un valor de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fb73-121">Retrieves an application value.</span></span>  
  
-   <span data-ttu-id="6fb73-122">**Obtener Id. común.**</span><span class="sxs-lookup"><span data-stu-id="6fb73-122">**Get Common ID.**</span></span> <span data-ttu-id="6fb73-123">Recupera un identificador de un objeto común.</span><span class="sxs-lookup"><span data-stu-id="6fb73-123">Retrieves an identifier for a common object.</span></span>  
  
-   <span data-ttu-id="6fb73-124">**Obtener valor común.**</span><span class="sxs-lookup"><span data-stu-id="6fb73-124">**Get Common Value.**</span></span> <span data-ttu-id="6fb73-125">Recupera un valor común.</span><span class="sxs-lookup"><span data-stu-id="6fb73-125">Retrieves a common value.</span></span>  
  
-   <span data-ttu-id="6fb73-126">**Quitar Id. de aplicación.**</span><span class="sxs-lookup"><span data-stu-id="6fb73-126">**Remove Application ID.**</span></span> <span data-ttu-id="6fb73-127">Quita un valor de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fb73-127">Removes an application value.</span></span>  
  
-   <span data-ttu-id="6fb73-128">**Establecer Id. común.**</span><span class="sxs-lookup"><span data-stu-id="6fb73-128">**Set Common ID.**</span></span> <span data-ttu-id="6fb73-129">Establece y devuelve un identificador para un objeto común.</span><span class="sxs-lookup"><span data-stu-id="6fb73-129">Sets and returns an identifier for a common object.</span></span>  
  
-   <span data-ttu-id="6fb73-130">**Extractor de valor.**</span><span class="sxs-lookup"><span data-stu-id="6fb73-130">**Value Extractor.**</span></span> <span data-ttu-id="6fb73-131">Use la **Extractor de valor** functoid para extraer datos de la columna especificada en un conjunto de registros devuelto por la **base de datos de búsqueda** functoid.</span><span class="sxs-lookup"><span data-stu-id="6fb73-131">Use the **Value Extractor** functoid to extract data from the specified column in a recordset returned by the **Database Lookup** functoid.</span></span> <span data-ttu-id="6fb73-132">El functoid requiere dos parámetros de entrada: un vínculo a la **base de datos de búsqueda** functoid y un nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="6fb73-132">This functoid requires two input parameters: a link to the **Database Lookup** functoid and a column name.</span></span>  
  
 <span data-ttu-id="6fb73-133">Siete de los **base de datos** functoids: **formatear mensaje, obtener Id. de aplicación**, **obtener valor de aplicación**, **obtener Id. común**, **Obtener valor común**, **quitar Id. de aplicación**, y **establecer Id. común**: son **referencias cruzadas** functoids.</span><span class="sxs-lookup"><span data-stu-id="6fb73-133">Seven of the **Database** functoids— **Format Message, Get Application ID**, **Get Application Value**, **Get Common ID**, **Get Common Value**, **Remove Application ID**, and **Set Common ID**—are **CrossReferencing** functoids.</span></span> <span data-ttu-id="6fb73-134">Estos functoids trasladan los Id. y valores de un mensaje de entrada a los Id. y valores que se necesitan en el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="6fb73-134">These functoids translate IDs and values from an input message into the IDs and values needed in the output message.</span></span> <span data-ttu-id="6fb73-135">Para obtener más información, consulte **referencia de Functoids de base de datos** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="6fb73-135">For more information, see **Database Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="example"></a><span data-ttu-id="6fb73-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6fb73-136">Example</span></span>  
 <span data-ttu-id="6fb73-137">En el ejemplo siguiente se usa algunos de los **base de datos** functoids.</span><span class="sxs-lookup"><span data-stu-id="6fb73-137">The following example uses some of the **Database** functoids.</span></span> <span data-ttu-id="6fb73-138">Imagine un gran fabricante de comercios al por menor, con tiendas distribuidas por una extensa área geográfica.</span><span class="sxs-lookup"><span data-stu-id="6fb73-138">Consider a large retail manufacturer with stores spread over a large geographical area.</span></span> <span data-ttu-id="6fb73-139">Para realizar un seguimiento de los almacenes, oficina central asigna a cada almacén de un código único denominado un **StoreID**.</span><span class="sxs-lookup"><span data-stu-id="6fb73-139">To keep track of the stores, headquarters assigns each store a unique code called a **StoreID**.</span></span> <span data-ttu-id="6fb73-140">Además, la oficina central asocia la siguiente información a cada **StoreID**:</span><span class="sxs-lookup"><span data-stu-id="6fb73-140">Additionally, headquarters associates the following information with each **StoreID**:</span></span>  
  
-   <span data-ttu-id="6fb73-141">StoreName</span><span class="sxs-lookup"><span data-stu-id="6fb73-141">StoreName</span></span>  
  
-   <span data-ttu-id="6fb73-142">StoreAddress</span><span class="sxs-lookup"><span data-stu-id="6fb73-142">StoreAddress</span></span>  
  
-   <span data-ttu-id="6fb73-143">City</span><span class="sxs-lookup"><span data-stu-id="6fb73-143">City</span></span>  
  
-   <span data-ttu-id="6fb73-144">PostalCode</span><span class="sxs-lookup"><span data-stu-id="6fb73-144">PostalCode</span></span>  
  
-   <span data-ttu-id="6fb73-145">StorePhoneNumber</span><span class="sxs-lookup"><span data-stu-id="6fb73-145">StorePhoneNumber</span></span>  
  
-   <span data-ttu-id="6fb73-146">StoreManager</span><span class="sxs-lookup"><span data-stu-id="6fb73-146">StoreManager</span></span>  
  
 <span data-ttu-id="6fb73-147">Esta información se almacena en una base de datos y se distribuye a los socios comerciales periódicamente.</span><span class="sxs-lookup"><span data-stu-id="6fb73-147">This information is stored in a database and is distributed to trading partners on a regular basis.</span></span> <span data-ttu-id="6fb73-148">Para el fabricante, todas las compras las realiza la oficina central, no las tiendas.</span><span class="sxs-lookup"><span data-stu-id="6fb73-148">For the manufacturer, all purchasing is done by headquarters, not the stores.</span></span> <span data-ttu-id="6fb73-149">Cuando la oficina central envía un pedido a los socios comerciales, es habitual que varias tiendas reciban mercancía encargada mediante el pedido único.</span><span class="sxs-lookup"><span data-stu-id="6fb73-149">When headquarters sends a purchase order to the trading partners, it is common for multiple stores to receive merchandise ordered through the single purchase order.</span></span> <span data-ttu-id="6fb73-150">En lugar de enviar información de nombre y la dirección de cada tienda que tiene que recibir mercancía, oficina central envía simplemente el **StoreID**.</span><span class="sxs-lookup"><span data-stu-id="6fb73-150">Instead of sending name and address information for each store that is to receive merchandise, headquarters simply sends the **StoreID**.</span></span> <span data-ttu-id="6fb73-151">Para insertar la información de nombre y la dirección en la notificación previa de envío, el socio comercial utiliza el **base de datos** functoids para insertar automáticamente esta información en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="6fb73-151">To insert the name and address information into the advanced ship notice, the trading partner uses the **Database** functoids to automatically insert this information into the output instance message.</span></span> <span data-ttu-id="6fb73-152">En la siguiente ilustración se muestra cómo puede implementar un socio comercial la sustitución del StoreID en una asignación.</span><span class="sxs-lookup"><span data-stu-id="6fb73-152">The following figure shows how a trading partner can implement the replacement of the StoreID in a map.</span></span>  
  
 <span data-ttu-id="6fb73-153">![Mapa que muestra los functoids de base de datos diferente. ] (../core/media/origdbfunctoids.gif "origdbfunctoids")</span><span class="sxs-lookup"><span data-stu-id="6fb73-153">![Map showing  different database functoids.](../core/media/origdbfunctoids.gif "origdbfunctoids")</span></span>  
  
 <span data-ttu-id="6fb73-154">En la ilustración, el esquema de origen representa un pedido entrante; el esquema de destino representa una notificación previa de envío.</span><span class="sxs-lookup"><span data-stu-id="6fb73-154">In the figure, the source schema represents an incoming purchase order; the destination schema represents an advanced ship notice.</span></span> <span data-ttu-id="6fb73-155">El **base de datos de búsqueda** functoid busca el registro adecuado de la tabla de base de datos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6fb73-155">The **Database Lookup** functoid finds the appropriate record from the appropriate database table.</span></span> <span data-ttu-id="6fb73-156">El **Extractor de valor** functoids extraen la columna apropiada del registro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6fb73-156">The **Value Extractor** functoids extract the appropriate column from the lookup record.</span></span> <span data-ttu-id="6fb73-157">El **devolución de Error** functoid genera una cadena que contiene información de error si hay errores (como errores de conexión) en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6fb73-157">The **Error Return** functoid outputs a string containing error information if there are errors (such as connection failures) at run time.</span></span>  
  
 <span data-ttu-id="6fb73-158">En el ejemplo anterior, el primer parámetro de entrada se toma de la **StoreID** campo de entrada pedido de compra y el restante tres parámetros de entrada son constantes configuradas en el **configurar \< Functoid\> Functoid** cuadro de diálogo para la **base de datos de búsqueda** functoid.</span><span class="sxs-lookup"><span data-stu-id="6fb73-158">In the previous example, the first input parameter is taken from the **StoreID** field of the incoming purchase order, and the remaining three input parameters are constants configured in the **Configure \<Functoid\> Functoid** dialog box for the **Database Lookup** functoid.</span></span> <span data-ttu-id="6fb73-159">Es posible crear vínculos desde el esquema de origen para suministrar valores a los cuatro parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="6fb73-159">It is possible to create links from the source schema to supply values for all four input parameters.</span></span>  
  
> [!NOTE]
>  * <span data-ttu-id="6fb73-160">No se puede usar algunos tipos de datos de Microsoft SQL Server, como **texto**, **ntext**, y **imagen**, como valores de búsqueda para la **búsqueda de la base de datos** functoid.</span><span class="sxs-lookup"><span data-stu-id="6fb73-160">You cannot use some Microsoft SQL Server data types, such as **text**, **ntext**, and **image**, as lookup values for the **Database Lookup** functoid.</span></span> <span data-ttu-id="6fb73-161">El functoid requiere tipos de datos que puedan representarse como una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="6fb73-161">The functoid requires data types that can be represented as a text string.</span></span>  
>
>  * <span data-ttu-id="6fb73-162">Si hay más de un registro que coincida con los parámetros de entrada de la **búsqueda de la base de datos** functoid, la **Extractor de valor** functoid extrae los datos solo desde el primer registro.</span><span class="sxs-lookup"><span data-stu-id="6fb73-162">If there is more than one record matching the input parameters of the **Database Lookup** functoid, the **Value Extractor** functoid extracts data only from the first record.</span></span>  
>
>  * <span data-ttu-id="6fb73-163">Utilice autenticación de NT en las cadenas de conexión para proteger las contraseñas mediante cifrado.</span><span class="sxs-lookup"><span data-stu-id="6fb73-163">Use NT authentication in connection strings to protect passwords with encryption.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="6fb73-164">Functoids disponibles</span><span class="sxs-lookup"><span data-stu-id="6fb73-164">Available functoids</span></span>  
 <span data-ttu-id="6fb73-165">El **base de datos** functoids son:</span><span class="sxs-lookup"><span data-stu-id="6fb73-165">The **Database** functoids are:</span></span> 

* <span data-ttu-id="6fb73-166">Búsqueda en base de datos</span><span class="sxs-lookup"><span data-stu-id="6fb73-166">Database Lookup</span></span>
* <span data-ttu-id="6fb73-167">Devolución de error</span><span class="sxs-lookup"><span data-stu-id="6fb73-167">Error Return</span></span>
* <span data-ttu-id="6fb73-168">Formatear mensaje</span><span class="sxs-lookup"><span data-stu-id="6fb73-168">Format Message</span></span>
* <span data-ttu-id="6fb73-169">Obtener Id. de aplicación</span><span class="sxs-lookup"><span data-stu-id="6fb73-169">Get Application ID</span></span>
* <span data-ttu-id="6fb73-170">Obtener valor de aplicación</span><span class="sxs-lookup"><span data-stu-id="6fb73-170">Get Application Value</span></span>
* <span data-ttu-id="6fb73-171">Obtener Id. común</span><span class="sxs-lookup"><span data-stu-id="6fb73-171">Get Common ID</span></span>
* <span data-ttu-id="6fb73-172">Obtener valor común</span><span class="sxs-lookup"><span data-stu-id="6fb73-172">Get Common Value</span></span>
* <span data-ttu-id="6fb73-173">Quitar Id. de aplicación</span><span class="sxs-lookup"><span data-stu-id="6fb73-173">Remove Application ID</span></span>
* <span data-ttu-id="6fb73-174">Establecer Id. común</span><span class="sxs-lookup"><span data-stu-id="6fb73-174">Set Common ID</span></span>
* <span data-ttu-id="6fb73-175">Extractor de valor</span><span class="sxs-lookup"><span data-stu-id="6fb73-175">Value Extractor</span></span>

<span data-ttu-id="6fb73-176">Para obtener más detalles sobre estas funciones, vea la **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="6fb73-176">For more details on these functiods, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="6fb73-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fb73-177">See Also</span></span>  
-  [<span data-ttu-id="6fb73-178">Cómo agregar Functoids básicos a un mapa</span><span class="sxs-lookup"><span data-stu-id="6fb73-178">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
-  <span data-ttu-id="6fb73-179">**Referencia a Functoids de base de datos**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6fb73-179">**Database Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>