---
title: "Invocación de RFC y BAPI utilizando el comando EXEC en SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EXEC command, invoking RFCs and BAPIs
- BAPIs and RFCs, invoking by using the EXEC command
- RFCs and BAPIs, invoking by using the EXEC command
ms.assetid: 55443679-2fa8-4c13-ac3b-1c85b5166cd2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 500e0f932a8245f76954aa7a8785dbec012321e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-rfcs-and-bapis-using-the-exec-command-in-sap"></a>Invocación de RFC y BAPI utilizando el comando EXEC en SAP
La [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] expone el sistema SAP como un origen de datos ADO.NET. Mediante el uso de [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], puede invocar RFC y BAPI en el sistema SAP a través de un comando EXEC.  
  
## <a name="how-to-invoke-rfcs-and-bapis-on-the-sap-system"></a>Cómo invocar RFC y BAPI en el sistema SAP  
 Para invocar una RFC o BAPI usando la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], siga estos pasos:  
  
#### <a name="to-invoke-an-rfc-or-bapi"></a>Para invocar una RFC o BAPI  
  
1.  Incluir una referencia (y una con la instrucción en el código) para **Microsoft.Data.SAPClient**.  
  
2.  Crear un **SAPConnection** objeto mediante un proveedor de datos de cadena de conexión de SAP. Para obtener más información acerca de la cadena de conexión, vea [más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).  
  
3.  Abrir una conexión con el sistema SAP mediante la invocación de **abiertos** en el **SAPConnection**.  
  
4.  Crear un **SAPCommand** objeto desde el **SAPConnection**.  
  
5.  Especificar la llamada BAPI o RFC en la **CommandText** propiedad de la **SAPCommand**. Si es necesario, puede especificar parámetros mediante **SAPParameter** objetos. Para obtener más información sobre cómo especificar una llamada BAPI o RFC mediante una instrucción EXEC, consulte [sintaxis de una instrucción EXEC en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md). Para obtener ejemplos de cómo especificar un BAPI o RFC, consulte [ejemplos de la instrucción EXEC](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md).  
  
6.  Ejecute el comando para invocar la RFC o BAPI y obtener los resultados en un **SAPDataReader**.  
  
7.  Lea los resultados de la **SAPDataReader**.  
  
8.  Cuando haya terminado de usarlos, cerrar (o eliminar) la **SAPConnection** y **SAPDataReader**.  
  
 El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] también expone un **SAPClientFactory** (clase), que puede usar para crear **SAPConnection**, **SAPCommand** y **SAPConnection** objetos. Para obtener más información acerca de las clases ADO.NET que se extiende el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se invoca SD_RFC_CUSTOMER_GET para recuperar la información de cliente para todos los clientes cuyos nombres empiezan por "AB". A continuación, escribe al cliente registros en la consola.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoExec  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string connstr = "TYPE=A; ASHOST=YourSAPHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
  
            using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "exec sd_rfc_customer_get @name1='AB*' ";  
                    using (SAPDataReader dr = cmd.ExecuteReader())  
                    {  
                        do  
                        {  
                            int rows = 0;  
                            while (dr.Read())  
                            {  
                                rows++;  
                                StringBuilder b = new StringBuilder();  
                                for (int i = 0; i < dr.FieldCount; i++)  
                                {  
                                    b.Append(dr[i].ToString() + " ");  
                                }  
                                Console.WriteLine("row {0}: {1} ", rows, b.ToString());  
                            }  
                            Console.WriteLine("Number of rows:{0}", rows);  
                        } while (dr.NextResult());  
  
                    }  
                }  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Usar el proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)   
 [Ejemplos](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)