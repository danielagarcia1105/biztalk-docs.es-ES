---
title: "Completar las operaciones en tablas con tipos de datos de gran tamaño en la base de datos de Oracle mediante el modelo de servicio WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations on tables and views
- how to, invoke the ReadLOB and UpdateLOB operations
ms.assetid: 5d0e84d3-7ffa-47c7-aaf2-a1007f7a71a2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ae5a616e71e27a4d6fa8cd27473665f7bc96b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-database-using-the-wcf-service-model"></a>Completar las operaciones en tablas con tipos de datos de gran tamaño en la base de datos de Oracle mediante el modelo de servicio WCF
Esta sección contiene información sobre cómo invocar las operaciones ReadLOB y UpdateLOB desde el modelo de servicio WCF. Las operaciones de ReadLOB y UpdateLOB se exhibe para tablas y vistas que contienen columnas LOB; que es que las columnas que se utilizan para almacenar datos de objetos grandes (LOB) de Oracle. Para obtener información general de los tipos de datos LOB de Oracle admitidos la [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] y de las operaciones ReadLOB y UpdateLOB, consulte [operaciones en tablas y vistas que contienen LOB base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md).  
  
> [!IMPORTANT]
>  Columnas de datos LOB pueden contener grandes cantidades de datos: hasta 4 gigabytes (GB). Una limitación importante del uso de un cliente de WCF para operar en las columnas LOB es que el modelo de servicio WCF solo admite datos de transmisión por secuencias en la operación de ReadLOB, no en la operación de UpdateLOB. Esto es porque WCF requiere que para la transmisión por secuencias para trabajar desde el modelo de servicio, el parámetro se transmita debe ser el único parámetro en su dirección. La operación de UpdateLOB tiene dos otros parámetros IN (un nombre y la fila de filtro de columna) además de los datos LOB; por esta razón, transmisión por secuencias no se admite en ella en el modelo de servicio WCF. Por lo tanto, si va a actualizar una columna LOB con una gran cantidad de datos, puede usar el modelo de canal WCF. Para obtener más información acerca de cómo usar el modelo de canal WCF para transmitir datos LOB mediante la operación de UpdateLOB, consulte [Streaming Oracle tipos de datos LOB utilizando el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 Los ejemplos en este tema usan la tabla /SCOTT/CUSTOMER. Esta tabla contiene una columna BLOB denominada PHOTO. Una secuencia de comandos para generar esta tabla se suministra con los ejemplos del SDK. Para obtener más información acerca de los ejemplos SDK, vea [ejemplos del SDK](../../core/samples-in-the-sdk.md).  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El ejemplo siguiente muestra las firmas de método para una clase de cliente WCF generado para las operaciones de ReadLOB y UpdateLOB en la tabla /SCOTT/CUSTOMER.  
  
```  
public partial class SCOTTTableCUSTOMERClient : System.ServiceModel.ClientBase<SCOTTTableCUSTOMER>,   
                                                SCOTTTableCUSTOMER   
{  
    public System.IO.Stream ReadLOB(string LOB_COLUMN, string FILTER);   
  
    public void UpdateLOB(string LOB_COLUMN, string FILTER, byte[] Stream);  
}  
```  
  
> [!NOTE]
>  Tenga en cuenta que **ReadLOB** devuelve un flujo de datos, pero que **UpdateLOB** no funciona en una secuencia.  
  
## <a name="invoking-the-readlob-and-updatelob-operations"></a>Invocar las operaciones de UpdateLOB y ReadLOB  
 Tanto el **ReadLOB** y **UpdateLOB** métodos solo pueden funcionar en una sola columna LOB en una fila única de la base de datos. Establecer los parámetros siguientes para identificar la fila/columna de destino.  
  
|Parámetro|Definición|  
|---------------|----------------|  
|LOB_COLUMN|El nombre de la columna de destino dentro de la fila identificada por el parámetro FILTER; Por ejemplo, "PHOTO".|  
|FILTER|El contenido de una instrucción SQL SELECT cláusula WHERE que especifica la fila de destino; Por ejemplo, "nombre = 'Kim Ralls'". El filtro debe especificar una y solo una fila. Si el filtro coincide con más de una fila:<br /><br /> -   **ReadLOB** devuelve datos LOB para la primera fila coincidente.<br />-   **UpdateLOB** produce una excepción.|  
  
> [!NOTE]
>  La secuencia devuelta por **ReadLOB** no admite **Seek**. Esto significa que las propiedades como **longitud** no se admiten, ya sea.  
  
> [!CAUTION]
>  El **UpdateLOB** operación debe realizarse dentro de un ámbito de transacción. Además, el **UseAmbientTransaction** enlaza la propiedad debe establecerse en **true** antes de realizar la **UpdateLOB** operación.  
  
 El código siguiente muestra cómo utilizar a un cliente de WCF para actualizar la columna PHOTO de BLOB en la tabla /SCOTT/CUSTOMER desde un archivo y leer los datos de columna nueva a un archivo. Puede encontrar un ejemplo completo en los ejemplos del SDK. Para obtener más información acerca de los ejemplos SDK, vea [ejemplos del SDK](../../core/samples-in-the-sdk.md).  
  
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
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)