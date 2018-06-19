---
title: Ejecutar una consulta SAP mediante el comando EXECQUERY | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 520153bf-9477-4b35-8953-3f5cb444ab9f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86159a03858ae5aa31bb37da56b6e5ea68dac3ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217212"
---
# <a name="execute-an-sap-query-using-the-execquery-command"></a>Ejecutar una consulta SAP mediante el comando EXECQUERY
La [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] expone el sistema SAP como un origen de datos ADO.NET. Con el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], puede ejecutar las consultas predefinidas en el sistema SAP mediante la ejecución de una instrucción EXECQUERY.  
  
## <a name="how-to-perform-a-query-by-using-the-execquery-command"></a>Cómo realizar una consulta mediante el comando EXECQUERY  
 Para ejecutar SAP predefinido de consultas usando la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], siga estos pasos:  
  
#### <a name="to-perform-a-query"></a>Para realizar una consulta  
  
1.  Incluir una referencia (y una con la instrucción en el código) para **Microsoft.Data.SAPClient**.  
  
2.  Crear un **SAPConnection** objeto mediante un proveedor de datos de cadena de conexión de SAP. Para obtener más información acerca de la cadena de conexión, vea [más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).  
  
3.  Abrir una conexión con el sistema SAP mediante la invocación de **abiertos** en el **SAPConnection**.  
  
4.  Crear un **SAPCommand** objeto desde el **SAPConnection**.  
  
5.  Especifique la instrucción EXECQUERY en el **CommandText** propiedad de la **SAPCommand**. Si es necesario, puede especificar parámetros mediante **SAPParameter** objetos. Para obtener más información acerca de cómo ejecutar consultas definidas en un sistema SAP mediante una instrucción EXECQUERY, consulte [sintaxis de una instrucción EXECQUERY en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md).  
  
6.  Ejecute el comando para realizar la consulta y obtener los resultados en un **SAPDataReader**.  
  
7.  Lea los resultados de la **SAPDataReader**.  
  
8.  Cuando haya terminado de usarlos, cerrar (o eliminar) la **SAPConnection** y **SAPDataReader**.  
  
 El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] también expone un **SAPClientFactory** (clase), que puede usar para crear **SAPConnection**, **SAPCommand** y **SAPConnection** objetos. Para obtener más información acerca de las clases ADO.NET que se extiende el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se escribe los resultados de una consulta, ZTEST1, en la consola.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoExecQuery  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
           string connstr = "TYPE=A; ASHOST=YourSapHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
           using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "EXECQUERY ZTEST1 @userGRoup='SYSTQV000024',@P1='0000001390',@P2='0000080150'";  
                    cmd.Parameters.Add(new SAPParameter("@connid", 17));                      
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
                                    b.Append(dr[i].ToString()+" ");  
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
 [Ejemplos](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)