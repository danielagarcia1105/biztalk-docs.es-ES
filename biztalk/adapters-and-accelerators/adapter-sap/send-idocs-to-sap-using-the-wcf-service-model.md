---
title: Enviar los IDOC a SAP mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, sending IDOCs to SAP
- IDOCs, sending to SAP by using the WCF service model
ms.assetid: 84077234-b82b-4e88-b858-ce2cb1383fb4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d9d550887271e2ba54d858456347ea85825554e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="send-idocs-to-sap-using-the-wcf-service-model"></a>Enviar los IDOC a SAP mediante el modelo de servicio de WCF
Internamente, el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] envía IDOC al sistema SAP mediante la invocación de una de las dos siguientes RFC:  
  
-   IDOC_INBOUND_ASYNCHRONOUS para IDOC versión 3.  
  
-   INBOUND_IDOC_PROCESS para IDOC versión 2.  
  
 Puede enviar un IDOC al adaptador mediante la invocación de la RFC adecuado (o tRFC); Sin embargo, también puede usar las dos operaciones siguientes para enviar IDOC al adaptador:  
  
-   **SendIdoc** aparece directamente bajo el nodo de raíz IDOC. La operación de SendIdoc envía el IDOC como datos de cadena (débilmente tipada) en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   **Enviar** aparece individualmente para cada IDOC. La operación de envío envía el IDOC como datos fuertemente tipados a la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
 Estas operaciones determinan cómo se envían los datos IDOC al adaptador, no cómo se envía al sistema SAP. El adaptador siempre envía el IDOC al sistema SAP mediante el tRFC adecuado.  
  
 Dado que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] envía el IDOC como un tRFC, las operaciones de envío y SendIdoc exponen un parámetro GUID que use para confirmar el IDOC (confirman). El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] internamente se asigna este GUID con la transacción de SAP TID (Id.) que está asociado a la tRFC. Puede confirmar el IDOC en uno de dos maneras:  
  
-   Mediante el uso de la **AutoConfirmSentIdocs** propiedad de enlace. Si se establece esta propiedad de enlace en **true**, el adaptador confirma automáticamente la tRFC usado para enviar el IDOC.  
  
-   Al invocar RfcConfirmTransID. Invocar esta operación con el GUID asociado con el IDOC.  
  
 Las secciones siguientes muestran cómo enviar IDOC a un sistema SAP mediante las operaciones de envío y SendIdoc. Para que obtener más información para ayudarle a enviar un IDOC como un tRFC, consulte [invocar tRFCs en SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md).  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
  
### <a name="the-sendidoc-operation"></a>La operación de SendIdoc  
 La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone una única operación (y el contrato de servicio) para enviar un IDOC en formato de cadena. El nombre del contrato de servicio es "Idoc" y la clase de cliente WCF es **IdocClient**.  
  
 Puede enviar todos los IDOC a SAP mediante el uso de este cliente. Contiene un método único, **SendIdoc**, que toma dos parámetros:  
  
-   **idocData** es una cadena que contiene los datos IDOC  
  
-   **GUID** es el GUID que se asigna al TID de SAP.  
  
 El código siguiente muestra al cliente WCF que se genera para la operación de SendIdoc.  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocClient : System.ServiceModel.ClientBase<Idoc>, Idoc {  
  
    public void SendIdoc(string idocData, ref System.Nullable\<System.Guid\> guid) {…}  
}  
```  
  
### <a name="the-send-operation"></a>La operación de envío  
 Dado que la operación de envío utiliza datos fuertemente tipados, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone un contrato de servicio único para cada IDOC. El nombre de la interfaz (y la clase de cliente WCF) genera para este contrato se basa en el tipo IDOC, la versión, el número de versión y el tipo CIM (si procede). Por ejemplo, para el IDOC ORDERS03.v3.620, la interfaz se denomina "IdocORDERS03V3R620" y la clase de cliente WCF es **IdocORDERS03V3R620Client**.  
  
 Debe generar a un cliente único para cada tipo de IDOC diferente. Este cliente contiene un método único, **enviar**, que toma dos parámetros:  
  
-   **idocData** es una clase que representa los datos IDOC fuertemente tipada.  
  
-   **GUID** es una representación de cadena del GUID que se asigna al TID de SAP.  
  
 El código siguiente muestra al cliente WCF que se genera para la operación de envío exhibe para el IDOC ORDERS03.v3.620.  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocORDERS03V3R620Client : System.ServiceModel.ClientBase<IdocORDERS03V3R620>, IdocORDERS03V3R620 {  
  
    ...  
  
    public void Send(ORDERS03 idocData, ref string guid) { ... }  
}  
```  
  
## <a name="how-to-create-an-application-to-send-idocs"></a>Cómo crear una aplicación para enviar los IDOC  
 Para enviar un IDOC a un sistema SAP, realice los pasos siguientes.  
  
#### <a name="to-send-an-idoc-to-an-sap-system"></a>Para enviar un IDOC a un sistema SAP  
  
1.  Generar una clase de cliente WCF. Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos herramienta de utilidad ServiceModel (svcutil.exe) para generar la clase de cliente WCF que tenga como destino el IDOC con el que desea trabajar. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio de WCF para los artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md). Si desea confirmar explícitamente IDOC, asegúrese de que genera al cliente de WCF para la operación de RfcConfirmTransID. Las operaciones pueden encontrarse en los nodos siguientes:  
  
    -   Operación de SendIdoc. Directamente bajo el nodo IDOC.  
  
    -   Operación de envío. En el nodo correspondiente al número de tipo, versión y lanzamiento del destino IDOC.  
  
    -   Operación de RfcConfirmTransID. Directamente bajo el nodo TRFC.  
  
2.  Cree una instancia de la clase de cliente WCF generada en el paso 1, y especifique un enlace del cliente. Especificación de un enlace de cliente implica especificar el enlace y la dirección del extremo que se va a usar el cliente de WCF. Puede hacerlo imperativamente en código o mediante declaración en configuración. Para obtener más información sobre cómo especificar un enlace del cliente, consulte [configurar un enlace de cliente para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md). El código siguiente inicializa un IdocClient (para la operación de envío) de configuración y establece las credenciales para el sistema SAP.  
  
    ```  
    SAPBinding binding = new SAPBinding();  
  
    // Set endpoint address  
    EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
    // Create client and set credentials  
    idocClient = new IdocClient(binding, endpointAddress);  
    idocClient.ClientCredentials.UserName.UserName = "YourUserName";  
    idocClient.ClientCredentials.UserName.Password = "YourPassword";;  
    ```  
  
3.  Si desea que el adaptador para confirmar la tRFC en el sistema SAP después envía el IDOC, establezca el **AutoConfirmSentIdocs** enlazar la propiedad a **true**. Debe hacerlo antes de abrir al cliente de WCF.  
  
    ```  
    // Set AutoConfirmSentIdocs property to true  
    binding.AutoConfirmSentIdocs = true;  
    ```  
  
4.  Abra al cliente de WCF.  
  
    ```  
    idocClient.Open();  
    ```  
  
5.  Invocar el método apropiado en el cliente WCF que creó en el paso 2 para enviar el IDOC al sistema SAP. Puede pasar una variable que contiene un GUID o que se establece en **null** para el **guid** parámetro. Si no especifica un GUID, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] genera uno para la operación (**guid** es un **ref** parámetro). El siguiente código lee un IDOC (en formato de cadena) de un archivo y lo envía al sistema SAP mediante una operación SendIdoc.  
  
    ```  
    // Read IDOC into string variable  
    using (StreamReader reader = new StreamReader("ORDERS03.txt"))  
    {  
    idocData = reader.ReadToEnd();  
    }  
  
    //Get a new GUID to pass to SendIdoc. You can also assign a null  
    //value to have the adapter generate a GUID.  
    adapterTxGuid = Guid.NewGuid();  
  
    //Invoke SendIdoc on the client to send the IDOC to the SAP system  
    idocClient.SendIdoc(idocData, ref adapterTxGuid);  
    ```  
  
6.  Si no estableció el **AutoConfirmSentIdocs** enlazar la propiedad a **true** (en el paso 3), a continuación, debe confirmar la tRFC en el sistema SAP. Para ello debe invocar el **RfcConfirmTransID** método en un **TrfcClient** (no se muestra la creación). Especifique el GUID devuelto en el paso 4 para el parámetro.  
  
    ```  
    trfcClient.RfcConfirmTransID(adapterTxGuid);  
    ```  
  
7.  Cerrar el cliente de WCF (y **TrfcClient**, si se usa) cuando haya terminado con él (cuando haya terminado de enviar idoc).  
  
    ```  
    idocClient.Close();   
    ```  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se envía un IDOC a un sistema SAP mediante el método SendIdoc. El IDOC se lee desde un archivo, ORDERS03.txt. Este archivo contiene un ORDERS03. V3.620 IDOC y se incluye con los ejemplos; Sin embargo, la operación de SendIdoc puede utilizarse para enviar todos los IDOC.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.IO;  
  
// Add WCF, WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for WCF LOB Adapter SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// This example sends a flat IDOC to the SAP system by using the SendIdoc operation.  
namespace SapIdocStringClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // variable for the IDOC client  
            IdocClient idocClient = null;  
  
            Console.WriteLine("IDOC string client sample started");  
            try  
            {  
                // Variable for the GUID  
                System.Nullable<System.Guid> adapterTxGuid;  
                // string to hold the Idoc data  
                string idocData;  
                // string to hold the SAP transaction ID (TID)  
                string sapTxId;  
  
                // The client can be configured from app.config, but it is   
                // explicitly configured here for demonstration.  
                // set AutoConfirmSentIdocs property to true  
                SAPBinding binding = new SAPBinding();  
                binding.AutoConfirmSentIdocs = true;  
  
                // Set endpoint address  
                EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPServer/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
                // Create client and set credentials  
                idocClient = new IdocClient(binding, endpointAddress);  
                idocClient.ClientCredentials.UserName.UserName = "YourUserName";  
                idocClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                // Open the client and send the Idoc  
                idocClient.Open();  
  
                // Read IDOC into string variable  
                using (StreamReader reader = new StreamReader("ORDERS03.txt"))  
                {  
                    idocData = reader.ReadToEnd();  
                }  
  
                //Get a new GUID to pass to SendIdoc. You can also assign a null.  
                //value to have the adapter generate a GUID.  
                adapterTxGuid = Guid.NewGuid();  
  
                //Invoke SendIdoc on the client to send the IDOC to the SAP system.  
                idocClient.SendIdoc(idocData, ref adapterTxGuid);  
  
                // The AutoConfirmSentIdocs binding property is set to true, so there is no need to  
                // confirm the IDOC. If this property is not set to true, you must call the   
                // RfcConfirmTransID method of a TrfcClient with adapterTxGuid to   
                // confirm the transaction on the SAP system.   
  
                // Get SAP tx id from GUID  
                sapTxId = SAPAdapterUtilities.ConvertGuidToTid((Guid) adapterTxGuid);  
  
                Console.WriteLine("IDOC sent");  
                Console.WriteLine("The SAP Transaction Id is : " + sapTxId);  
  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
                // Close the IDOC client  
                if (idocClient != null)  
                {  
                    if (idocClient.State == CommunicationState.Opened)  
                        idocClient.Close();  
                    else  
                        idocClient.Abort();  
                }  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)