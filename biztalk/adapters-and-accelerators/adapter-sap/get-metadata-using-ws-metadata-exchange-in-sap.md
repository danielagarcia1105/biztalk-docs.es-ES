---
title: Obtener metadatos con WS-Metadata Exchange en SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange
- how to, retrieve metadata
- retrieving metadata
ms.assetid: 29f85963-ac7f-4e13-96b8-bc2c94a9fcae
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae33fd76725abf15f12d95be39997fc29e67403e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-using-ws-metadata-exchange-in-sap"></a>Obtener metadatos con WS-Metadata Exchange en SAP
Como un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado, el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] expone un extremo de WS-Metadata Exchange (MEX) que puede usar para recuperar metadatos para operaciones específicas de la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].  
  
 WCF proporciona una infraestructura enriquecida para exportar, publicar, recuperar e importar metadatos de un servicio. Los servicios WCF, al igual que el adaptador, usan metadatos para describir cómo interactuar con los puntos de conexión de servicio para que las herramientas, como svcutil.exe, puedan generar automáticamente código de cliente para utilizar el servicio. WCF representa los metadatos para un servicio como una instancia de la **MetadataSet** tipo, que está estrechamente ligado al formato de serialización de metadatos definido en WS-Metadata Exchange (MEX). Puede crear un **MetadataSet** para las operaciones de destino en el adaptador mediante el uso de un **MetadataExchangeClient**.  
  
 WCF admite para el intercambio de metadatos es un tema amplio y fuera del ámbito de esta documentación. Para obtener más información sobre la compatibilidad con metadatos en WCF, vea "Metadatos" en la documentación de WCF en [http://go.microsoft.com/fwlink/?LinkId=105634](http://go.microsoft.com/fwlink/?LinkId=105634). Para obtener una descripción especialmente apropiada de la arquitectura, clases y espacios de nombres que WCF expone metadatos, vea "Información general de arquitectura de metadatos" en [http://go.microsoft.com/fwlink/?LinkId=105635](http://go.microsoft.com/fwlink/?LinkId=105635). Deberá familiarizarse con el contenido relacionado con la recuperación de metadatos de un servicio WCF en estos temas WCF antes de continuar.  
  
 Los temas siguientes contienen información sobre cómo usar un **MetadataExchangeClient** para recuperar los metadatos de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a>Usar un MetadataExchangeClient para recuperar metadatos  
 Para usar un **MetadataExchangeClient** debe especificar un URI de conexión y un enlace (**SAPBinding**). El URI de conexión identifica las operaciones para el que van a recuperar los metadatos.  
  
 Las secciones siguientes contienen información acerca de cómo especificar las propiedades de enlace importante, el URI de conexión y cómo usar un **MetadataExchangeClient** para recuperar metadatos desde el adaptador.  
  
### <a name="the-connection-uri"></a>El URI de conexión  
 Para usar el **MetadataExchangeClient** debe proporcionar un URI que especifica un extremo MEX y la o las operaciones para el que van a recuperar los metadatos de la conexión de SAP. Especificar una operación de punto de conexión y de destino MEX en el URI de conexión de la siguiente manera:  
  
-   Debe incluir el parámetro "wsdl" en la cadena de consulta. Si es el primer parámetro de la cadena de consulta, se especifica justo después del signo de interrogación (?). Si no es el primer parámetro, debe ir precedida por una y comercial (&).  
  
-   Debe seguir el parámetro "wsdl" por uno o más parámetros de "op". Cada parámetro de "op" está precedido por una y comercial (&) y especifica la acción de mensaje (Id. de nodo) de una operación de destino.  
  
 Por ejemplo, el siguiente URI de conexión tiene como destino la operación de envío para el IDOC SALESORDER_CREATEFROMDAT201 y el IDOC SALESORDER_CREATEFROMDAT202. Se resaltan los parámetros "wsdl" y "op".  
  
```  
"sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"  
```  
  
> [!NOTE]
>  No es necesario incluir parámetros de agente de escucha en el URI de conexión para las operaciones de entrada. El adaptador se conecta como un cliente para recuperar metadatos desde el sistema SAP.  
  
 También puede usar las constantes definidas en `Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants` para ayudarle a especificar operaciones cuando se crea un URI de conexión. Esto se muestra en el ejemplo de código al final de este tema.  
  
 Cómo pasar este URI de conexión para el **MetadataExchangeClient** depende de cuál de los métodos sobrecargados que utilice para crear el cliente y recuperar metadatos desde el adaptador.  
  
 Para obtener más información sobre el URI de conexión de SAP, consulte [cree el URI de conexión del sistema SAP](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
### <a name="binding-properties"></a>Propiedades de enlace  
 Cuando se crea el **MetadataExchangeClient**, debe especificar un **SAPBinding**.  
  
 Hay varias propiedades de enlace que afectan al modo en que el adaptador genera los metadatos. Estas propiedades son:  
  
-   **GenerateFlatfileCompatibleIdocSchema**  
  
-   **ReceiveIDocFormat**  
  
-   **EnableSafeTyping**  
  
-   **FlatFileSegmentIndicator**  
  
 Debe asegurarse de que estas propiedades de enlace se establecen en los valores necesarios para la aplicación antes de invocar el **GetMetadata** método en el **MetadataExchangeClient**. Para obtener más información acerca de las propiedades de enlace del adaptador SAP, consulte [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un **MetadataExchangeClient** para crear una descripción de servicio (documento WSDL) para las operaciones de BAPI_TRANSACTION_COMMIT y BAPI_TRANSACTION_ROLLBACK.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Collections.ObjectModel;  
  
// Needed for WCF and SAP adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.SAP;  
  
// Needed for MetadataExchangeClient class  
using System.ServiceModel.Description;  
// Needed for ServiceDescription class  
using System.Web.Services;  
  
namespace SapMetadataExchangeClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //Create a binding  
            SAPBinding binding = new SAPBinding();  
  
            //Create a metadata exchange client that will retrieve metadata according to the WS-MEX standard.  
            MetadataExchangeClient client = new MetadataExchangeClient(binding);  
            client.SoapCredentials.UserName.UserName = "YourUserName";  
            client.SoapCredentials.UserName.Password = "YourPassword";  
  
            //Set up an endpoint address and specify the operation for which we want metadata.  
            string connectionUri = "sap://Client=800;lang=EN@A/YourSAPHost/00?wsdl&op="  
                + Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix  
                + "BAPI_TRANSACTION_COMMIT"  
                + "&op="  
                + Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix  
                + "BAPI_TRANSACTION_ROLLBACK";  
  
            EndpointAddress address = new EndpointAddress(connectionUri);  
  
            //Get the metadata.  
            MetadataSet ms = client.GetMetadata(address);  
  
            // Check for the metadata set size.   
            Collection<MetadataSection> documentCollection = ms.MetadataSections;  
            if (documentCollection != null && documentCollection.Count > 0)  
            {  
                //Get the WSDL from the metadata set  
                System.Web.Services.Description.ServiceDescription wsdl = (System.Web.Services.Description.ServiceDescription)documentCollection[0].Metadata;  
  
                //Save the WSDL to a file.  
                wsdl.Write("BapiTx.wsdl");    
  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Al recuperar los metadatos mediante programación desde SAP](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md)   
 [Al recuperar los metadatos de SAP mediante IMetadataRetrievalContract](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)