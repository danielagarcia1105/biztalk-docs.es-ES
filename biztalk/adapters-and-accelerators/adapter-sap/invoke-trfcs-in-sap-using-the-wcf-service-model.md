---
title: Invocar tRFCs en SAP mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tRFCs, invoking by using the WCF service model
- WCF service model, invoking tRFCs
ms.assetid: 456fa869-2f1a-42e0-adbf-86bfe0876846
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f23ee3e863318c9d75be9136e7b7fc0fa37b921
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-trfcs-in-sap-using-the-wcf-service-model"></a>Invocar tRFCs en SAP mediante el modelo de servicio de WCF
Llamadas a funciones remotas transaccionales (tRFCs) garantizar un *única* ejecución de una solicitud de cambio en un sistema SAP. Puede invocar cualquiera de los documentos de RFC obtenidas por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como un tRFC. Invocar un tRFC en el modelo de servicio WCF es similar a invocar una solicitud de cambio con las siguientes diferencias:  
  
-   El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies tRFCs bajo un nodo diferente (TRFC) que las solicitudes de cambio (RFC).  
  
-   llamadas de cliente tRFC no devuelven valores de exportación SAP y cambiar los parámetros.  
  
-   operaciones de tRFC incluyen un parámetro GUID que está asignado al identificador de transacción de SAP (TID) para el tRFC por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   Después de invocar un tRFC, debe invocar la operación de RfcConfirmTransID para confirmar la tRFC en el sistema SAP (confirman). Esta operación aparece directamente debajo del nodo TRFC.  
  
 Para obtener más información sobre las operaciones de tRFC y la operación de RfcConfirmTransID, consulte [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).  
  
 Las secciones siguientes muestran cómo invocar tRFCs en el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies todas las operaciones de tRFC bajo un contrato de servicio único, "Trfc". Esto significa que una sola clase de cliente WCF, **TrfcClient**, se crea para todas las operaciones de tRFC que desea invocar. Cada tRFC de destino se representa como un método de esta clase. Para cada método:  
  
-   Tipos complejos de SAP como estructuras aparecen como clases de .NET con propiedades que corresponden a los campos del tipo SAP. Estas clases se definen en el espacio de nombres siguiente: **microsoft.lobservices.sap._2007._03.Types.Rfc**.  
  
 El código siguiente muestra parte de la **TrfcClient** clase y el método que invoca BAPI_SALESORDER_CREATEFROMDAT2 (como un tRFC) en el sistema SAP. El **TransactionalRfcOperationIdentifier** parámetro contiene el GUID asignado al TID de SAP. No todos los parámetros para el método se muestran.  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class TrfcClient : System.ServiceModel.ClientBase<Trfc>, Trfc {  
  
    ....  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    public void BAPI_SALESORDER_CREATEFROMDAT2(  
                string BEHAVE_WHEN_ERROR,   
                string BINARY_RELATIONSHIPTYPE,   
                string CONVERT,   
                string INT_NUMBER_ASSIGNMENT,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDLS LOGIC_SWITCH,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1 ORDER_HEADER_IN,   
  
                …  
  
               microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIADDR1[] PARTNERADDRESSES,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2[] RETURN,   
                ref System.Guid TransactionalRfcOperationIdentifier) { ...  }  
}  
```  
  
 El código siguiente muestra el método que se genera para la operación de RfcConfirmTransID. Debe asegurarse de que este método se genera como parte de la **TrfcClient**. La operación de RfcConfirmTransID aparece directamente debajo del nodo TRFC.  
  
```  
public void RfcConfirmTransID(System.Guid TransactionalRfcOperationIdentifier) {…}  
```  
  
## <a name="how-to-create-a-trfc-client-application"></a>Cómo crear una aplicación de cliente tRFC  
 Los pasos para crear una aplicación que invoca tRFCs son similares a los pasos que debe seguir para invocar las solicitudes de cambio, con las siguientes excepciones:  
  
-   Debe recuperar las operaciones de destino en el nodo TRFC.  
  
-   Se debe recuperar la operación de RfcConfirmTransID. Esto aparece directamente debajo del nodo TRFC.  
  
-   Para confirmar una operación de tRFC en el sistema SAP (confirman), debe invocar la operación de RfcConfirmTransID con el GUID que se devolvió para esa operación tRFC.  
  
#### <a name="to-create-a-trfc-client-application"></a>Para crear una aplicación de cliente tRFC  
  
1.  Generar un **TrfcClient** clase. Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos de herramienta de utilidad ServiceModel (svcutil.exe) para generar un **TrfcClient** clase que tenga como destino las RFC con el que desea trabajar. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio de WCF para la solución SAP artefactos](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md). Asegúrese de que la operación de RfcConfirmTransID se incluye en el **TrfcClient** clase.  
  
2.  Cree una instancia de la **TrfcClient** clase generado en el paso 1 y especificar un enlace del cliente. Especificación de un enlace de cliente implica especificar el enlace y el punto de conexión de dirección que el **TrfcClient** va a usar. Puede hacerlo imperativamente en código o mediante declaración en configuración. Para obtener más información sobre cómo especificar un enlace del cliente, consulte [configurar un enlace de cliente para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md). El siguiente código inicializa el **TrfcClient** de configuración y establece las credenciales para el sistema SAP.  
  
    ```  
    TrfcClient trfcClient = new TrfcClient("SAPBinding_Rfc");  
  
    trfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
    trfcClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  Abra la **TrfcClient**.  
  
    ```  
    trfcClient.Open();  
    ```  
  
4.  Invocar el método adecuado en el **TrfcClient** creado en el paso 2 para invocar el tRFC de destino en el sistema SAP. Puede pasar una variable que contiene un GUID o que contiene un GUID vacío para la **TransactionalRrcOperationIdentifier** parámetro. Si se pasa un GUID vacío, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] genera uno automáticamente. El código siguiente invoca BAPI_SALESORDER_CREATEFROMDAT2 como un tRFC en el sistema SAP (no todos los parámetros del método se muestran). Se especificó un GUID.  
  
    ```  
    transactionalRfcOperationIdentifier = Guid.NewGuid();  
  
    //invoke RFC_CUSTOMER_GET as a tRFC  
    trfcClient.BAPI_SALESORDER_CREATEFROMDAT2(  
                                    request.BEHAVE_WHEN_ERROR,  
                                    request.BINARY_RELATIONSHIPTYPE,  
                                    request.CONVERT,  
  
                                    ...  
  
                                    ref transactionalRfcOperationIdentifier);  
    ```  
  
5.  Para confirmar el TID asociado con la tRFC en el sistema SAP, invocar el **RfcConfirmTransID** método en el **TrfcClient**. Especifique el GUID devuelto en el paso 4 para el **TransactionRfcOperationIdentifier**parámetro.  
  
    ```  
    trfcClient.RfcConfirmTransID(transactionalRfcOperationIdentifier);  
    ```  
  
6.  Cerrar la **TrfcClient** cuando haya terminado usarlo (una vez que haya terminado de invocar tRFCs todos).  
  
    ```  
    trfcClient.Close();   
    ```  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo invocar BAPI_SALESORDER_CREATE como un tRFC.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, the WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for WCF LOB Adapter SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using microsoft.lobservices.sap._2007._03.Types.Rfc;  
  
// This example demonstrates sending BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC. The client has   
// methods to:  
//      send the BAPI (BAPI_SALESORDER_CREATEFROMDAT2)and to  
//      Confirm the transaction (RfcConfirmTransID)  
// An instance of BAPI_SALESORDER_CREATEFROMDAT2Request (generated)   
// is used to format the BAPI before invoking BAPI_SALESORDER_CREATEFROMDAT2. This   
// is not necessary, but is done to make it easier to read the code.  
// tRFC invocations always includes a ref parameter that contains a GUID. You can optionally   
// set this parameter when you invoke the method; however, you must use the value returned by  
// the adapter when you call RfcConfirmTransID to confirm the transaction on the SAP system.   
// You can call the utility method, SAPAdapterUtilities.ConvertGuidToTid, to get the value  
// of the SAP transaction Id from the GUID that the adapter returns.  
namespace SapTrfcClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            TrfcClient sapTrfcClient = null;  
  
            try  
            {  
                Console.WriteLine("SAP TRFC client sample started");  
                Console.WriteLine("Creating the TRFC client");  
                // Create the SAP Trfc Client from configuration  
                sapTrfcClient = new TrfcClient("SAPBinding_Trfc");  
                sapTrfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
                sapTrfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                Console.WriteLine("Opening the TRFC client");  
                // Open the Trfc Client  
                sapTrfcClient.Open();  
  
                // Create a GUID -- note: this is optional. If you do not pass a GUID,  
                // for the TransactionalRfcOperationIdentifier parameter, the SAP adapter will   
                // generate one, associate it with the SAP TID, and set the   
                // TransactionalRfcOperationIdentifier parameter.  
                Guid tidGuid = Guid.NewGuid();  
  
                BAPI_SALESORDER_CREATEFROMDAT2Request request = new BAPI_SALESORDER_CREATEFROMDAT2Request();  
  
                request.ORDER_HEADER_IN = new BAPISDHD1();  
                request.ORDER_HEADER_IN.DOC_TYPE = "TA";  
                request.ORDER_HEADER_IN.SALES_ORG = "1000";  
                request.ORDER_HEADER_IN.DISTR_CHAN = "10";  
                request.ORDER_HEADER_IN.DIVISION = "00";  
                request.ORDER_HEADER_IN.SALES_OFF = "1000";  
                request.ORDER_HEADER_IN.REQ_DATE_H = DateTime.Now;  
                request.ORDER_HEADER_IN.PURCH_DATE = DateTime.Now;  
                request.ORDER_HEADER_IN.PURCH_NO_C = "Cust PO";  
                request.ORDER_HEADER_IN.CURRENCY = "EUR";  
  
                BAPISDITM[] orderItems = new BAPISDITM[1];  
                orderItems[0] = new BAPISDITM();  
                orderItems[0].MATERIAL = "P-109";  
                orderItems[0].PLANT = "1000";  
                orderItems[0].TARGET_QU = "ST";  
                request.ORDER_ITEMS_IN = orderItems;  
  
                BAPIPARNR[] orderPartners = new BAPIPARNR[1];  
                orderPartners[0] = new microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPARNR();  
                orderPartners[0].PARTN_ROLE = "AG";  
                orderPartners[0].PARTN_NUMB = "0000001390";  
                request.ORDER_PARTNERS = orderPartners;  
  
                // Create a GUID -- note: this is optional. If you do not pass a GUID,  
                // for the TransactionalRfcOperationIdentifier parameter, the SAP adapter will   
                // generate one, associate it with the SAP TID, and set the   
                // TransactionalRfcOperationIdentifier parameter.  
                request.TransactionalRfcOperationIdentifier = Guid.NewGuid();  
  
                Console.WriteLine("Invoking BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC");  
  
                //invoke RFC_CUSTOMER_GET as a tRFC  
                sapTrfcClient.BAPI_SALESORDER_CREATEFROMDAT2(request.BEHAVE_WHEN_ERROR,  
                                                                request.BINARY_RELATIONSHIPTYPE,  
                                                                request.CONVERT,  
                                                                request.INT_NUMBER_ASSIGNMENT,  
                                                                request.LOGIC_SWITCH,  
                                                                request.ORDER_HEADER_IN,  
                                                                request.ORDER_HEADER_INX,  
                                                                request.SALESDOCUMENTIN,  
                                                                request.SENDER,  
                                                                request.TESTRUN,  
                                                                request.EXTENSIONIN,  
                                                                request.ORDER_CCARD,  
                                                                request.ORDER_CFGS_BLOB,  
                                                                request.ORDER_CFGS_INST,  
                                                                request.ORDER_CFGS_PART_OF,  
                                                                request.ORDER_CFGS_REF,  
                                                                request.ORDER_CFGS_REFINST,  
                                                                request.ORDER_CFGS_VALUE,  
                                                                request.ORDER_CFGS_VK,  
                                                                request.ORDER_CONDITIONS_IN,  
                                                                request.ORDER_CONDITIONS_INX,  
                                                                request.ORDER_ITEMS_IN,  
                                                                request.ORDER_ITEMS_INX,  
                                                                request.ORDER_KEYS,  
                                                                request.ORDER_PARTNERS,  
                                                                request.ORDER_SCHEDULES_IN,  
                                                                request.ORDER_SCHEDULES_INX,  
                                                                request.ORDER_TEXT,  
                                                                request.PARTNERADDRESSES,  
                                                                request.RETURN,  
                                                                ref request.TransactionalRfcOperationIdentifier);  
  
                string sapTxId = null;  
                sapTxId = SAPAdapterUtilities.ConvertGuidToTid(request.TransactionalRfcOperationIdentifier);  
  
                Console.WriteLine("BAPI_SALESORDER_CREATEFROMDAT2 Sent");  
                Console.WriteLine("The SAP Transaction Id is " + sapTxId);  
  
                // Invoke the RfcConfirmTransID method to confirm (commit) the transaction on  
                // the SAP system. This step is required to complete the transaction. The SAP  
                // adapter will always return a TranactionalRfcOperationIdentifier, whether   
                // one was supplied in the call or not.  
                sapTrfcClient.RfcConfirmTransID(request.TransactionalRfcOperationIdentifier);  
  
                Console.WriteLine("SAP Transaction {0} has been committed", sapTxId);  
  
                Console.WriteLine("\nHit <RETURN> to end");  
                Console.ReadLine();  
  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
                throw;  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw;  
            }  
            finally  
            {  
                // Close the client  
                if (sapTrfcClient != null)  
                {  
                    if (sapTrfcClient.State == CommunicationState.Opened)  
                        sapTrfcClient.Close();  
                    else  
                        sapTrfcClient.Abort();  
                }  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [Operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)