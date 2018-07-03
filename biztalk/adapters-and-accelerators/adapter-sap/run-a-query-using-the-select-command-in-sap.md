---
title: Ejecutar una consulta con el comando SELECT en SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SELECT command, performing a query
- query, performing by using the SELECT command
ms.assetid: 6f03243c-ef50-4a4a-8fe6-4e525bd7efe3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5e4edb19c3f69b14dd55219f504a6a3d0cc1688
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971085"
---
# <a name="run-a-query-using-the-select-command-in-sap"></a>Ejecutar una consulta con el comando SELECT en SAP
La [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] expone el sistema SAP como un origen de datos ADO.NET. Con el [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], puede consultar los artefactos SAP mediante la ejecución de una instrucción SELECT.  
  
## <a name="how-to-perform-a-query-by-using-the-select-command"></a>Cómo realizar una consulta mediante el comando SELECT  
 Para los artefactos SAP de consulta mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], realice los pasos siguientes:  
  
#### <a name="to-perform-a-query"></a>Para realizar una consulta  
  
1. Incluir una referencia (y una instrucción using en el código) para **Microsoft.Data.SAPClient**.  
  
2. Crear un **SAPConnection** objeto mediante el uso de un proveedor de datos de cadena de conexión de SAP. Para obtener más información acerca de la cadena de conexión, consulte [lea acerca de los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).  
  
3. Abrir una conexión con el sistema SAP mediante la invocación **abierto** en el **SAPConnection**.  
  
4. Crear un **SAPCommand** objeto desde el **SAPConnection**.  
  
5. Especifique la instrucción SELECT en la **CommandText** propiedad de la **SAPCommand**. Si es necesario, puede especificar parámetros mediante **SAPParameter** objetos. Para obtener más información acerca de cómo consultar los artefactos SAP con una instrucción SELECT, vea [sintaxis para una instrucción SELECT en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md). Para obtener ejemplos de cómo especificar una BAPI o RFC, consulte [ejemplos para la instrucción SELECT](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md).  
  
6. Ejecute el comando para realizar la consulta y obtener los resultados en un **SAPDataReader**.  
  
7. Lea los resultados de la **SAPDataReader**.  
  
8. Cuando haya terminado con ellos, cerrar (o eliminar) la **SAPConnection** y **SAPDataReader**.  
  
   El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] también expone un **SAPClientFactory** (clase), que puede usar para crear **SAPConnection**, **SAPCommand** y **SAPConnection** objetos. Para obtener más información acerca de las clases ADO.NET extendida la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente escribe los resultados de una instrucción select en una instrucción de combinación interna con parámetros en la consola.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoSelect  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
        /// <summary>  
        /// select top 1 * from sflight inner join spfli on sflight.connid = spfli.connid where spfli.connid = @connid  
        /// </summary>  
  
        string connstr = "TYPE=A; ASHOST=YourSapHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
  
           using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "select top 1 * from sflight inner join spfli on sflight.connid = spfli.connid where spfli.connid = @connid";  
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