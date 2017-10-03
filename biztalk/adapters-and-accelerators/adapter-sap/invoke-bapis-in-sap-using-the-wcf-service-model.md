---
title: Invocar BAPI en SAP mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAPIs, invoking by using the WCF service model
- WCF service model, invoking BAPIs
ms.assetid: be3c48d6-2213-4ae5-97f4-634fbc423022
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 437c88516cfb771e0e5ae10807391235d602eb37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-bapis-in-sap-using-the-wcf-service-model"></a>Invocar BAPI en SAP mediante el modelo de servicio de WCF
El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies BAPI como:  
  
-   **Operaciones de RFC**. BAPI como cualquier otro RFC aparecen bajo el nodo RFC en la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
-   **Métodos de objetos comerciales SAP**. Como métodos de objetos comerciales, objeto de negocios en el nodo BAPI Emerge BAPI el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
 Si se invoca una BAPI como una operación de RFC o como un método del objeto comercial, cada BAPI siempre forma parte de un LUW en el sistema SAP.  
  
 Para obtener información general del uso del [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite BAPI, consulte [operaciones de BAPI en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).  
  
 Cuando use el modelo de servicio WCF para invocar BAPI como métodos de objetos comerciales, cada objeto de negocios SAP se representa mediante una clase de cliente WCF y la BAPI de ese objeto de negocios se representa como métodos en el cliente. Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF para objetos de negocio específico que contiene métodos para cada BAPI que desea invocar en el código. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera tipos de .NET para encapsular los parámetros y tipos de datos utilizados por cada BAPI. A continuación, puede crear una instancia de esta clase de cliente WCF y llamar a sus métodos para invocar el destino BAPI.  
  
 Las secciones siguientes muestran cómo invocar BAPI como métodos de objetos comerciales y explican cómo se admiten las transacciones de BAPI en el modelo de servicio WCF.  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone un contrato de servicio diferente para cada objeto de negocios. Esto significa que para cada objeto de negocios WCF único se crea la clase de cliente. El nombre de esta clase se basa en el tipo de objeto de negocios. Por ejemplo para el objeto de negocios de pedido de venta (tipo de objeto de negocios BUS2032), la clase de cliente WCF es **BapiBUS2032Client**. Cada destino BAPI en el objeto comercial se representa como un método en la clase de cliente WCF generada. En cada método:  
  
-   Los parámetros de exportación SAP aparecen como **out** parámetros  
  
-   Parámetros de llamada de SAP aparecen como **ref** parámetros.  
  
-   Tipos complejos de SAP como estructuras aparecen como clases de .NET con propiedades que corresponden a los campos del tipo SAP. Estas clases se definen en el espacio de nombres siguiente: microsoft.lobservices.sap._2007._03.Types.Rfc.  
  
 BAPI_TRANSACTION_COMMIT y BAPI_TRANSACTION_ROLLBACK aparecen para cada objeto de negocios y siempre debería incluir estas opciones en el cliente WCF.  
  
 El código siguiente muestra parte de una clase de cliente WCF generada por el objeto de negocios de pedido de venta. Este cliente contiene métodos para invocar CREATEFROMDAT2, BAPI_TRANSACTION_COMMIT y BAPI_TRANSACTION_ROLLBACK. Para mayor claridad los constructores y otro código se ha omitido.  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class BapiBUS2032Client : System.ServiceModel.ClientBase<BapiBUS2032>, BapiBUS2032 {  
  
    // Code has been removed for clarity  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="SALESDOCUMENT">Number of Generated Document</param>  
    /// <param name="BEHAVE_WHEN_ERROR">Error Handling</param>  
    /// …  
    /// <param name="ORDER_TEXT">Texts</param>  
    /// <param name="PARTNERADDRESSES">BAPI Reference Structure for Addresses (Org./Company)</param>  
    /// <param name="RETURN">Return Messages</param>  
    /// <returns></returns>  
    public string CREATEFROMDAT2(  
                string BEHAVE_WHEN_ERROR,   
                string BINARY_RELATIONSHIPTYPE,   
                string CONVERT,   
                string INT_NUMBER_ASSIGNMENT,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDLS LOGIC_SWITCH,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1 ORDER_HEADER_IN,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1X ORDER_HEADER_INX,   
                string SALESDOCUMENTIN,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPI_SENDER SENDER,   
                string TESTRUN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPAREX[] EXTENSIONIN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICCARD[] ORDER_CCARD,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUBLB[] ORDER_CFGS_BLOB,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUINS[] ORDER_CFGS_INST,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUPRT[] ORDER_CFGS_PART_OF,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUCFG[] ORDER_CFGS_REF,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUREF[] ORDER_CFGS_REFINST,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUVAL[] ORDER_CFGS_VALUE,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUVK[] ORDER_CFGS_VK,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICOND[] ORDER_CONDITIONS_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICONDX[] ORDER_CONDITIONS_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDITM[] ORDER_ITEMS_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDITMX[] ORDER_ITEMS_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDKEY[] ORDER_KEYS,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPARNR[] ORDER_PARTNERS,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISCHDL[] ORDER_SCHEDULES_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISCHDLX[] ORDER_SCHEDULES_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDTEXT[] ORDER_TEXT,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIADDR1[] PARTNERADDRESSES,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2[] RETURN) { ...}  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="RETURN">Confirmations</param>  
    /// <param name="WAIT">Using the command `COMMIT AND WAIT`</param>  
    /// <returns></returns>  
    public microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2 BAPI_TRANSACTION_COMMIT(string WAIT) { ... }  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="RETURN">Confirmations</param>  
    /// <returns></returns>  
    public microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2 BAPI_TRANSACTION_ROLLBACK() { ... }  
}  
```  
  
## <a name="bapi-transactions-in-the-wcf-service-model"></a>Transacciones de BAPI en el modelo de servicio WCF  
 Cada BAPI, si se invoca como una solicitud de cambio o como un método del objeto comercial, forma parte de una transacción (LUW) en el sistema SAP; y cada BAPI recibido a través de la misma conexión de SAP forma parte de la misma transacción BAPI en el sistema SAP. SAP confirma o revierte la transacción de BAPI cuando recibe un BAPI_TRANSACTION_COMMIT o un BAPI_TRANSACTION_ROLLBACK en la conexión. Después de haber realizado una instrucción commit o rollback, la siguiente BAPI recibida a través de la conexión inicia una transacción nueva.  
  
 Para el adaptador de cada canal WCF tiene una conexión dedicada de SAP. En el modelo de servicio WCF, cada cliente WCF tiene un canal interno que es un mensaje de envío usado para el sistema SAP. Esto significa que la BAPI que se invoca mediante un cliente WCF específico forman parte de una transacción de BAPI única en el sistema SAP. Esto supone una limitación importante al utilizar el modelo de servicio WCF para invocar BAPI como métodos de objetos comerciales. Dado que cada objeto de negocios SAP se representa mediante una clase de cliente WCF dedicada, no se puede invocar BAPI de dos objetos de negocio diferente como parte de la misma transacción. La forma de hacerlo consiste en llamar la BAPI como operaciones de RFC. Esto es porque el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera un solo cliente WCF para las operaciones de RFC, y, por lo tanto, todas las operaciones que se invocan mediante ese cliente se envían a través del mismo canal WCF.  
  
> [!IMPORTANT]
>  Si desea incluir BAPI de diferentes objetos de negocios SAP en la misma transacción BAPI, se debe invocar como operaciones de RFC (con el mismo cliente WCF). No se puede invocar a ellos como métodos de objetos comerciales.  
  
 Se llama a BAPI_TRANSACTION_COMMIT o BAPI_TRANSACTION_ROLLBACK para confirmar o revertir la transacción BAPI en el sistema SAP. El adaptador de superficies de estos dos BAPI:  
  
-   En el nodo de base como operaciones de RFC.  
  
-   En cada objeto de negocios.  
  
 Para obtener más información acerca del modo en que el adaptador admite transacciones de BAPI en SAP, consulte [operaciones de BAPI en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).  
  
## <a name="how-to-create-an-application-that-invokes-bapis-as-methods-of-business-objects"></a>Cómo crear una aplicación que invoca BAPI como métodos de objetos comerciales  
 Esta sección proporciona información sobre cómo invocar BAPI como métodos de objetos comerciales. Debe seguir el mismo procedimiento básico para invocar BAPI como operaciones de RFC, excepto en que crear a un cliente WCF que tiene como destino la BAPI como operaciones de RFC y usarlo para invocar cada BAPI.  
  
 Para crear una aplicación de cliente BAPI, realice los pasos siguientes.  
  
#### <a name="to-create-an-bapi-client-application"></a>Para crear una aplicación de cliente BAPI  
  
1.  Generar una clase de cliente WCF. Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos herramienta de utilidad ServiceModel (svcutil.exe) para generar una clase de cliente WCF (o clases) destinado a los objetos de negocio y BAPI con el que desea trabajar. No olvide incluir el BAPI_TRANSACTION_COMMIT y los métodos BAPI_TRANSACTION_ROLLBACK (BAPI) expuestos para cada objeto de comercial de destino. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio de WCF para los artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
2.  Cree una instancia de la clase de cliente WCF generada en el paso 1 y crear y configurar a un cliente de WCF. Configurar al cliente de WCF implica especificar el enlace y la dirección del extremo que utilizará el cliente. Puede hacerlo imperativamente en código o mediante declaración en configuración. Para obtener más información sobre cómo especificar un enlace del cliente, consulte [configurar un enlace de cliente para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md). El código siguiente inicializa al cliente WCF para el objeto de negocios SAP de pedido de venta (BUS2032) de configuración y establece las credenciales para el sistema SAP.  
  
    ```  
    BapiBUS2032Client bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
    bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
    bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  Abra al cliente de WCF.  
  
    ```  
    bapiClient.Open();  
    ```  
  
4.  Invocar métodos en el cliente WCF que creó en el paso 2 para invocar la BAPI adecuado en el sistema SAP. Puede invocar varias BAPI en el sistema SAP.  
  
5.  Finalizar la transacción por:  
  
    1.  Invocar el método BAPI_TRANSACTION_COMMIT para confirmar la transacción.  
  
        ```  
        bapiClient.BAPI_TRANSACTION_COMMIT("X");  
        ```  
  
    2.  Invocar el método BAPI_TRANSACTION_ROLLBACK para revertir la transacción.  
  
        ```  
        bapiClient.BAPI_TRANSACTION_ROLLBACK();  
        ```  
  
6.  Cierre al cliente WCF.  
  
    ```  
    bapiClient.Close();   
    ```  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se invoca el BAPI CREATEFROMDAT2 en el objeto de negocios de pedido de venta. Invoca la BAPI varias veces y, a continuación, invoca BAPI_TRANSACTION_COMMIT para confirmar la transacción. Si se produce un error al invocar el BAPI, BAPI_TRANSACTION_ROLLBACK se invoca en el controlador de excepción para revertir la transacción.  
  
 El método CREATEFROMDAT2 toma varios parámetros; estos se omiten en el ejemplo por brevedad. Puede encontrar un ejemplo que muestra las transacciones de BAPI en los ejemplos incluidos con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos para el adaptador SAP ](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, Adapter LOB SDK, and SAP Adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for Adapter LOB SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using microsoft.lobservices.sap._2007._03.Types.Rfc;  
  
// This Example demonstrates BAPI transactions. Two sales orders are  
// created using the CREATEFROMDAT2 method of a SAP Business Object.   
// After the orders are created, the BAPI transaction is committed.   
// If an exception occurs when sending the BAPIs, the BAPI transaction is   
// rolled back.  
//   
  
namespace SapBapiTxClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create the BAPI client from the generated endpoint configuration.  
  
            BapiBUS2032Client bapiClient = null;  
  
            Console.WriteLine("BAPI transaction sample started");  
            Console.WriteLine("\nCreating business object client");  
  
            try  
            {  
                bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
                bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
                bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                // Open the BAPI Client  
                bapiClient.Open();  
  
                ...  
  
                // send first BAPI  
                try  
                {  
                    string salesDocNumber1 = bapiClient.CREATEFROMDAT2(  
                        ...  
                        // parameters ommitted  
                        ...                          
                        );  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
                // send second BAPI  
                try  
                {  
                    string salesDocNumber1 = bapiClient.CREATEFROMDAT2(  
                        ...  
                        // parameters omitted  
                        ...                          
                        );  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
                // Commit BAPI Transaction  
                try  
                {  
                    bapiClient.BAPI_TRANSACTION.Commit();  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
            }  
            catch (ConnectionException cex)  
            {  
                // Get here if problem connecting to the SAP system   
  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                // Get here if the SAP system returns an exception  
  
                Console.WriteLine("Exception occurred on the SAP System");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
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
            // Close the client when finished  
                if (bapiClient != null)  
                {  
                    if (bapiClient.State == CommunicationState.Opened)  
                        bapiClient.Close();  
                    else  
                        bapiClient.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)  
 [Operaciones de BAPI en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)