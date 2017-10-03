---
title: Obtener metadatos con WS-Metadata Exchange en la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange, retrieving metadata
- metadata, retrieving using WS-Metadata Exchange
ms.assetid: 6ff34438-7260-489d-a5f0-6e53f8fe43be
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be3f829d41b77dc7897d7b3f4300d82e7a3c100
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-using-ws-metadata-exchange-in-oracle-database"></a>Obtener metadatos con WS-Metadata Exchange en la base de datos de Oracle
Como un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado, el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un extremo de WS-Metadata Exchange (MEX) que puede usar para recuperar metadatos para operaciones específicas de la [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].  
  
 WCF proporciona una infraestructura enriquecida para exportar, publicar, recuperar e importar metadatos de un servicio. Los servicios WCF, al igual que el adaptador, usan metadatos para describir cómo interactuar con los puntos de conexión de servicio para que las herramientas, como svcutil.exe, puedan generar automáticamente código de cliente para utilizar el servicio. WCF representa los metadatos para un servicio como una instancia de la **MetadataSet** tipo, que está estrechamente ligado al formato de serialización de metadatos definido en WS-Metadata Exchange (MEX). Puede crear un **MetadataSet** para las operaciones de destino en el adaptador mediante el uso de un **MetadataExchangeClient**.  
  
 WCF admite para el intercambio de metadatos es un tema amplio y fuera del ámbito de esta documentación. Para obtener más información sobre la compatibilidad con metadatos en WCF, vea [metadatos](https://msdn.microsoft.com/library/ms731823.aspx). Para obtener una descripción especialmente apropiada de la arquitectura, clases y espacios de nombres que WCF expone metadatos, vea [Introducción a la arquitectura metadatos](https://msdn.microsoft.com/library/ms730243.aspx). Deberá familiarizarse con el contenido relacionado con la recuperación de metadatos de un servicio WCF en estos temas WCF antes de continuar.  
  
 Los temas siguientes contienen información sobre cómo usar un **MetadataExchangeClient** para recuperar los metadatos de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a>Usar un MetadataExchangeClient para recuperar metadatos  
 Para usar un **MetadataExchangeClient** debe especificar un URI de conexión y un enlace (**OracleDBBinding**). El URI de conexión identifica las operaciones para el que van a recuperar los metadatos.  
  
 Las secciones siguientes contienen información acerca de cómo especificar las propiedades de enlace importante, el URI de conexión y cómo usar un **MetadataExchangeClient** para recuperar metadatos desde el adaptador.  
  
### <a name="the-connection-uri"></a>El URI de conexión  
 Para usar el **MetadataExchangeClient** debe proporcionar una URI que especifica un extremo MEX y la o las operaciones para el que van a recuperar los metadatos de la conexión de Oracle. Especificar una operación de punto de conexión y de destino MEX en el URI de conexión de la siguiente manera:  
  
-   Debe incluir el parámetro "wsdl" en la cadena de consulta. Si es el primer parámetro de la cadena de consulta, se especifica justo después del signo de interrogación (?). Si no es el primer parámetro, debe ir precedida por una y comercial (&).  
  
-   Debe seguir el parámetro "wsdl" por uno o más parámetros de "op". Cada parámetro de "op" está precedido por una y comercial (&) y especifica la acción de mensaje (Id. de nodo) de una operación de destino.  
  
 Por ejemplo, el siguiente URI de conexión tiene como destino las operaciones de inserción y eliminación para el SCOTT. Tabla EMP. Se resaltan los parámetros "wsdl" y "op".  
  
```  
"oracledb://ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
```  
  
> [!NOTE]
>  Si desea modificar el espacio de nombres generado para la operación de POLLINGSTMT debe especificar un parámetro de PollingId en la cadena de consulta.  
  
 Cómo pasar este URI de conexión para el **MetadataExchangeClient** depende de cuál de los métodos sobrecargados que utilice para crear el cliente y recuperar metadatos desde el adaptador.  
  
 Para obtener más información sobre el URI de conexión de Oracle, vea [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  
  
### <a name="binding-properties"></a>Propiedades de enlace  
 Cuando se crea el **MetadataExchangeClient**, debe especificar un **OracleDBBinding**.  
  
 Hay varias propiedades de enlace que afectan al modo en que el adaptador genera los metadatos. Estas propiedades son:  
  
-   **EnableSafeTyping**  
  
-   **UseSchemaInNamespace**  
  
-   **PollingStatement**  
  
> [!IMPORTANT]
>  Si desea recuperar los metadatos de la operación de POLLINGSTMT debe establecer el **PollingStatement** propiedad de enlace.  
  
 Debe asegurarse de que estas propiedades de enlace se establecen en los valores necesarios para la aplicación antes de invocar el **GetMetadata** método en el **MetadataExchangeClient**. Para obtener más información sobre la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] propiedades de enlace, consulte [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un **MetadataExchangeClient** para crear una descripción de servicio (documento WSDL) para el Insert, Update, Delete y las operaciones Select en la SCOTT. Tabla EMP. El archivo WSDL se guarda en un archivo, EmpOperations.wsdl.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Collections.ObjectModel;  
  
// Needed for WCF and Oracle Adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Needced for MetadataExchangeClient class  
using System.ServiceModel.Description;  
// Needed for ServiceDescription class  
using System.Web.Services;  
  
namespace OracleMetadataExchange  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //create a binding  
            OracleDBBinding binding = new OracleDBBinding();  
  
            //create a metadata exchange client that will retrieve metadata according to the WS-MEX standard  
            MetadataExchangeClient client = new MetadataExchangeClient(binding);  
            client.SoapCredentials.UserName.UserName = "SCOTT";  
            client.SoapCredentials.UserName.Password = "TIGER";  
  
            //set up an endpoint address and specifies the operations for which we want metadata  
            string connectionUri = "oracledb://ADAPTER?wsdl"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select";  
  
            EndpointAddress address = new EndpointAddress(connectionUri);  
  
            //get the metadata  
            MetadataSet ms = client.GetMetadata(address);  
  
            // Check for the metadata set size   
            Collection<MetadataSection> documentCollection = ms.MetadataSections;  
            if (documentCollection != null && documentCollection.Count > 0)  
            {  
                //get the wsdl from the metadata set  
                System.Web.Services.Description.ServiceDescription wsdl = (System.Web.Services.Description.ServiceDescription)documentCollection[0].Metadata;  
  
                //save the wsdl to a file  
                wsdl.Write("EmpOperations.wsdl");  
  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos mediante programación de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)