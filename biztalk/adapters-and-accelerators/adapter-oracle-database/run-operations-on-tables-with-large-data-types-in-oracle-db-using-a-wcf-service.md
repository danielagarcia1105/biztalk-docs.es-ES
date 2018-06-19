---
title: Completar las operaciones en tablas con tipos de datos de gran tamaño en la base de datos de Oracle mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations on tables and views
- how to, invoke the ReadLOB and UpdateLOB operations
ms.assetid: 5d0e84d3-7ffa-47c7-aaf2-a1007f7a71a2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ae5a616e71e27a4d6fa8cd27473665f7bc96b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215612"
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="b0475-102">Completar las operaciones en tablas con tipos de datos de gran tamaño en la base de datos de Oracle mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="b0475-102">Complete operations on tables with large data types in Oracle Database using the WCF service model</span></span>
<span data-ttu-id="b0475-103">Esta sección contiene información sobre cómo invocar las operaciones ReadLOB y UpdateLOB desde el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="b0475-103">This section contains information about how to invoke the ReadLOB and UpdateLOB operations from the WCF service model.</span></span> <span data-ttu-id="b0475-104">Las operaciones de ReadLOB y UpdateLOB se exhibe para tablas y vistas que contienen columnas LOB; que es que las columnas que se utilizan para almacenar datos de objetos grandes (LOB) de Oracle.</span><span class="sxs-lookup"><span data-stu-id="b0475-104">The ReadLOB and UpdateLOB operations are surfaced for tables and views that contain LOB columns; that is columns that are used to store Oracle large object (LOB) data.</span></span> <span data-ttu-id="b0475-105">Para obtener información general de los tipos de datos LOB de Oracle admitidos la [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] y de las operaciones ReadLOB y UpdateLOB, consulte [operaciones en tablas y vistas que contienen LOB base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="b0475-105">For an overview of the Oracle LOB data types supported by the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] and of the ReadLOB and UpdateLOB operations, see [Operations on Tables and Views That Contain LOB Data in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b0475-106">Columnas de datos LOB pueden contener grandes cantidades de datos: hasta 4 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="b0475-106">LOB data columns can contain large amounts of data—up to 4 gigabytes (GB).</span></span> <span data-ttu-id="b0475-107">Una limitación importante del uso de un cliente de WCF para operar en las columnas LOB es que el modelo de servicio WCF solo admite datos de transmisión por secuencias en la operación de ReadLOB, no en la operación de UpdateLOB.</span><span class="sxs-lookup"><span data-stu-id="b0475-107">A significant limitation of using a WCF client to operate on LOB columns is that the WCF service model only supports data streaming on the ReadLOB operation, not on the UpdateLOB operation.</span></span> <span data-ttu-id="b0475-108">Esto es porque WCF requiere que para la transmisión por secuencias para trabajar desde el modelo de servicio, el parámetro se transmita debe ser el único parámetro en su dirección.</span><span class="sxs-lookup"><span data-stu-id="b0475-108">This is because WCF requires that for streaming to work from service model, the parameter to be streamed must be the only parameter in its direction.</span></span> <span data-ttu-id="b0475-109">La operación de UpdateLOB tiene dos otros parámetros IN (un nombre y la fila de filtro de columna) además de los datos LOB; por esta razón, transmisión por secuencias no se admite en ella en el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="b0475-109">The UpdateLOB operation has two other IN parameters (a column name and row filter) in addition to the LOB data; for this reason, streaming is not supported on it in the WCF service model.</span></span> <span data-ttu-id="b0475-110">Por lo tanto, si va a actualizar una columna LOB con una gran cantidad de datos, puede usar el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="b0475-110">Therefore, if you are updating a LOB column with a large amount of data, you might want to use the WCF channel model.</span></span> <span data-ttu-id="b0475-111">Para obtener más información acerca de cómo usar el modelo de canal WCF para transmitir datos LOB mediante la operación de UpdateLOB, consulte [Streaming Oracle tipos de datos LOB utilizando el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="b0475-111">For more information on how to use the WCF channel model to stream LOB data using the UpdateLOB operation, see [Streaming Oracle LOB Data Types by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="b0475-112">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="b0475-112">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="b0475-113">Los ejemplos en este tema usan la tabla /SCOTT/CUSTOMER.</span><span class="sxs-lookup"><span data-stu-id="b0475-113">The examples in this topic use the /SCOTT/CUSTOMER table.</span></span> <span data-ttu-id="b0475-114">Esta tabla contiene una columna BLOB denominada PHOTO. Una secuencia de comandos para generar esta tabla se suministra con los ejemplos del SDK.</span><span class="sxs-lookup"><span data-stu-id="b0475-114">This table contains a BLOB column named PHOTO.A script to generate this table is supplied with the SDK samples.</span></span> <span data-ttu-id="b0475-115">Para obtener más información acerca de los ejemplos SDK, vea [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="b0475-115">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="b0475-116">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="b0475-116">The WCF Client Class</span></span>  
 <span data-ttu-id="b0475-117">El ejemplo siguiente muestra las firmas de método para una clase de cliente WCF generado para las operaciones de ReadLOB y UpdateLOB en la tabla /SCOTT/CUSTOMER.</span><span class="sxs-lookup"><span data-stu-id="b0475-117">The following example shows the method signatures for a WCF client class generated for the ReadLOB and UpdateLOB operations on the /SCOTT/CUSTOMER table.</span></span>  
  
```  
public partial class SCOTTTableCUSTOMERClient : System.ServiceModel.ClientBase<SCOTTTableCUSTOMER>,   
                                                SCOTTTableCUSTOMER   
{  
    public System.IO.Stream ReadLOB(string LOB_COLUMN, string FILTER);   
  
    public void UpdateLOB(string LOB_COLUMN, string FILTER, byte[] Stream);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="b0475-118">Tenga en cuenta que **ReadLOB** devuelve un flujo de datos, pero que **UpdateLOB** no funciona en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="b0475-118">Note that **ReadLOB** returns a data stream, but that **UpdateLOB** does not operate on a stream.</span></span>  
  
## <a name="invoking-the-readlob-and-updatelob-operations"></a><span data-ttu-id="b0475-119">Invocar las operaciones de UpdateLOB y ReadLOB</span><span class="sxs-lookup"><span data-stu-id="b0475-119">Invoking the ReadLOB and UpdateLOB Operations</span></span>  
 <span data-ttu-id="b0475-120">Tanto el **ReadLOB** y **UpdateLOB** métodos solo pueden funcionar en una sola columna LOB en una fila única de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b0475-120">Both the **ReadLOB** and **UpdateLOB** methods can operate only on a single LOB column in a single database row.</span></span> <span data-ttu-id="b0475-121">Establecer los parámetros siguientes para identificar la fila/columna de destino.</span><span class="sxs-lookup"><span data-stu-id="b0475-121">You set the following parameters to identify the target column/row.</span></span>  
  
|<span data-ttu-id="b0475-122">Parámetro</span><span class="sxs-lookup"><span data-stu-id="b0475-122">Parameter</span></span>|<span data-ttu-id="b0475-123">Definición</span><span class="sxs-lookup"><span data-stu-id="b0475-123">Definition</span></span>|  
|---------------|----------------|  
|<span data-ttu-id="b0475-124">LOB_COLUMN</span><span class="sxs-lookup"><span data-stu-id="b0475-124">LOB_COLUMN</span></span>|<span data-ttu-id="b0475-125">El nombre de la columna de destino dentro de la fila identificada por el parámetro FILTER; Por ejemplo, "PHOTO".</span><span class="sxs-lookup"><span data-stu-id="b0475-125">The name of the target column within the row identified by the FILTER parameter; for example, "PHOTO".</span></span>|  
|<span data-ttu-id="b0475-126">FILTER</span><span class="sxs-lookup"><span data-stu-id="b0475-126">FILTER</span></span>|<span data-ttu-id="b0475-127">El contenido de una instrucción SQL SELECT cláusula WHERE que especifica la fila de destino; Por ejemplo, "nombre = 'Kim Ralls'".</span><span class="sxs-lookup"><span data-stu-id="b0475-127">The contents of a SQL SELECT statement WHERE clause that specifies the target row; for example, "NAME='Kim Ralls'".</span></span> <span data-ttu-id="b0475-128">El filtro debe especificar una y solo una fila.</span><span class="sxs-lookup"><span data-stu-id="b0475-128">The filter must specify one and only one row.</span></span> <span data-ttu-id="b0475-129">Si el filtro coincide con más de una fila:</span><span class="sxs-lookup"><span data-stu-id="b0475-129">If the filter matches more than one row:</span></span><br /><br /> <span data-ttu-id="b0475-130">-   **ReadLOB** devuelve datos LOB para la primera fila coincidente.</span><span class="sxs-lookup"><span data-stu-id="b0475-130">-   **ReadLOB** returns LOB data for the first matching row.</span></span><br /><span data-ttu-id="b0475-131">-   **UpdateLOB** produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="b0475-131">-   **UpdateLOB** throws an exception.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b0475-132">La secuencia devuelta por **ReadLOB** no admite **Seek**.</span><span class="sxs-lookup"><span data-stu-id="b0475-132">The stream returned by **ReadLOB** does not support **Seek**.</span></span> <span data-ttu-id="b0475-133">Esto significa que las propiedades como **longitud** no se admiten, ya sea.</span><span class="sxs-lookup"><span data-stu-id="b0475-133">This means that properties such as **Length** are not supported, either.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b0475-134">El **UpdateLOB** operación debe realizarse dentro de un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="b0475-134">The **UpdateLOB** operation must be performed within a transaction scope.</span></span> <span data-ttu-id="b0475-135">Además, el **UseAmbientTransaction** enlaza la propiedad debe establecerse en **true** antes de realizar la **UpdateLOB** operación.</span><span class="sxs-lookup"><span data-stu-id="b0475-135">Also, the **UseAmbientTransaction** binding property must be set to **true** before performing the **UpdateLOB** operation.</span></span>  
  
 <span data-ttu-id="b0475-136">El código siguiente muestra cómo utilizar a un cliente de WCF para actualizar la columna PHOTO de BLOB en la tabla /SCOTT/CUSTOMER desde un archivo y leer los datos de columna nueva a un archivo.</span><span class="sxs-lookup"><span data-stu-id="b0475-136">The following code shows how to use a WCF client to update the BLOB PHOTO column in the /SCOTT/CUSTOMER table from a file and read the new column data back to a file.</span></span> <span data-ttu-id="b0475-137">Puede encontrar un ejemplo completo en los ejemplos del SDK.</span><span class="sxs-lookup"><span data-stu-id="b0475-137">You can find a full sample in the SDK samples.</span></span> <span data-ttu-id="b0475-138">Para obtener más información acerca de los ejemplos SDK, vea [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="b0475-138">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Transaction;  
  
// Include for file streaming  
using System.IO;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for the WCF channel model  
using System.ServiceModel.Channels;  
  
// Include this namespace for the WCF LOB Adapter SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using CustomerTablens = microsoft.lobservices.oracledb._2007._03;  
  
namespace OracleLobOpsSnippetSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.UseAmbientTransaction = true; //set this to true for UpdateLOB operation  
  
                EndpointAddress endpointAddress = new EndpointAddress("oracleDB://ADAPTER");  
  
                using (SCOTTTableCUSTOMERClient customerTableClient =  
                    new SCOTTTableCUSTOMERClient(binding, endpointAddress))  
                {  
                    customerTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
                    customerTableClient.ClientCredentials.UserName.Password = "TIGER";  
  
                    // Open the client to read the LOB data back  
                    customerTableClient.Open();  
  
                    // Add a photo to the customer record    
                    using (FileStream fs = new FileStream("SamplePhoto.jpg", FileMode.Open))  
                    {  
                        Console.WriteLine("Updating photo");  
                        int count = 0;  
                        byte[] photo = new byte[fs.Length];  
                        while ((count += fs.Read(photo, count, (int) (((fs.Length-count)>4096)? 4096:fs.Length-count))) \< fs.Length) ;  
  
                        // UpdateLOB operation must be performed within a transaction scope  
                        using(TransactionScope tx = new TransactionScope())  
                        {  
                           customerTableClient.UpdateLOB("PHOTO", "NAME='Kim Ralls'", photo);  
                           Console.WriteLine("Photo updated");  
                           tx.Complete();  
                        }  
                    }  
  
                    // Read the data back and store it to another file  
                    using (FileStream fs = new FileStream("PhotoCopy.jpg", FileMode.Create))  
                    {  
                        Console.WriteLine("Reading photo data");  
                        Stream photoStream = customerTableClient.ReadLOB("PHOTO", "NAME='Kim Ralls'");  
                        Console.WriteLine("Photo data read -- writing to PhotoCopy.jpg");  
  
                        int count;  
                        int length = 0;  
                        byte[] buffer = new byte[4096];  
                        while ((count = photoStream.Read(buffer, 0, 4096)) > 0)  
                        {  
                            fs.Write(buffer, 0, count);  
                            length+=count;  
                        }  
                        Console.WriteLine("{0} bytes written to PhotoCopy.jpg", length);  
                    }  
  
                }  
  
                Console.WriteLine("Photo updated and read back -- Hit <RETURN> to end");  
                Console.ReadLine();  
  
            }  
            catch (Exception ex)  
            {  
                // handle exception  
                Console.WriteLine("Exception caught: " + ex.Message);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0475-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0475-139">See Also</span></span>  
 [<span data-ttu-id="b0475-140">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="b0475-140">Develop Oracle Database Applications Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)