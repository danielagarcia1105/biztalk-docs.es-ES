---
title: Invocar RFC en SAP mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- invoking RFCs, using the WCF service model
- WCF service model, invoking RFCs
ms.assetid: 06a373e2-5d16-4480-81ec-611bd0b9749c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8a18e9ae4990ecd5e85c57fc86919f239d51cbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-rfcs-in-sap-using-the-wcf-service-model"></a>Invocar RFC en SAP mediante el modelo de servicio de WCF
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] presenta las solicitudes de cambio en el sistema SAP como operaciones que se pueden invocar mediante un programa cliente. En el modelo de servicio WCF, estas operaciones se invocan como métodos de una clase de cliente WCF generada. Puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF que contiene métodos para cada solicitud de cambio que desea invocar en el código. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera tipos de .NET para encapsular los parámetros y tipos de datos que se utilizan con cada solicitud de cambio. A continuación, puede crear una instancia de esta clase de cliente WCF y llamar a sus métodos para invocar el destino RFC.  
  
 Las secciones siguientes muestran cómo invocar las solicitudes de cambio en el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies todas las operaciones de RFC bajo un contrato de servicio único, "Rfc". Esto significa que una sola clase de cliente WCF, **RfcClient**, se crea para todas las operaciones de RFC que se desea invocar. Cada destino RFC se representa como un método de esta clase. En cada método:  
  
-   Los parámetros de exportación SAP aparecen como **out** parámetros  
  
-   SAP cambiantes parámetros aparecen como **ref** parámetros.  
  
-   Tipos complejos de SAP como estructuras aparecen como clases de .NET con propiedades que corresponden a los campos del tipo SAP. Estas clases se definen en el espacio de nombres siguiente: microsoft.lobservices.sap._2007._03.Types.Rfc.  
  
 El código siguiente muestra parte de la **RfcClient** clase y el método que invoca SD_RFC_CUSTOMER_GET en el sistema SAP.  
  
```  
 [System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class RfcClient : System.ServiceModel.ClientBase<Rfc>, Rfc {  
  
    ...  
  
    /// <summary>The metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="KUNNR">Customer number</param>  
    /// <param name="NAME1">Name of the customer</param>  
    /// <param name="CUSTOMER_T">Table of the selected customers</param>  
    /// <returns></returns>  
    public void SD_RFC_CUSTOMER_GET(string KUNNR, string NAME1, ref microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] CUSTOMER_T) {...}  
}  
```  
  
## <a name="how-to-create-an-rfc-client-application"></a>Cómo crear una aplicación de cliente RFC  
 Para crear una aplicación de cliente RFC, realice los pasos siguientes.  
  
#### <a name="to-create-an-rfc-client-application"></a>Para crear una aplicación de cliente RFC  
  
1.  Generar un **RfcClient** clase. Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos de herramienta de utilidad ServiceModel (svcutil.exe) para generar un **RfcClient** clase que tenga como destino las RFC con el que desea trabajar. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio de WCF para los artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
2.  Cree una instancia de la **RfcClient** clase generado en el paso 1, y especificar un enlace del cliente. Especificación de un enlace de cliente implica especificar el enlace y el punto de conexión de dirección que el **RfcClient** va a usar. Puede hacerlo imperativamente en código o mediante declaración en configuración. Para obtener más información sobre cómo especificar un enlace del cliente, consulte [configurar un enlace de cliente para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md). El siguiente código inicializa el **RfcClient** de configuración y establece las credenciales para el sistema SAP.  
  
    ```  
    RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  Abra al cliente de WCF.  
  
    ```  
    rfcClient.Open();  
    ```  
  
4.  Invocar métodos en el **RfcClient** creado en el paso 2 para realizar operaciones en el sistema SAP. El código siguiente, se invoca el **SD_RFC_CUSTOMER_GET** método de la **RfcClient** para invocar la solicitud de cambio en el sistema SAP.  
  
    ```  
    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
        new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
    ```  
  
5.  Cierre al cliente WCF.  
  
    ```  
    rfcClient.Close();   
    ```  
  
### <a name="example"></a>Ejemplo  
 El siguiente es un ejemplo de código completo que invoca SD_RFC_CUSTOMER_GET para devolver una lista de los clientes que tengan nombres que comienzan por "AB" y, a continuación, escribe el nombre y el identificador de cada cliente en la consola. Este ejemplo se crea el **RfcClient** dentro de un **con** instrucción. No es necesario cerrar explícitamente el **RfcClient**; se cerrarán cuando salga de la ruta de acceso de ejecución del contexto.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.SAP;  
  
namespace SapRfcClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                // Create client from configuration  
                using (RfcClient rfcClient = new RfcClient("SAPBinding_Rfc"))  
                {  
  
                    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
                    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                    // Open client  
                    rfcClient.Open();  
  
                    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers = new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
                    // Invoke SD_RFC_CUSTOMER_GET  
                    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
  
                    // Write the results to the console  
                    foreach (microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST customer in customers)  
                    {  
                        Console.WriteLine("Customer Name = " + customer.NAME1);  
                        Console.WriteLine("         Id   = " + customer.KUNNR);  
                        Console.WriteLine();  
                    }  
                }  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
                if (ex.InnerException != null)  
                    Console.WriteLine("Inner exception is :" + ex.InnerException);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [Esquemas de mensaje para las operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)