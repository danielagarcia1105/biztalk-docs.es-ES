---
title: Ejemplo de GetMessages | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29e575fa-d68b-4975-84b8-da4f17bd2db3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2ebc4ce5b87a0b698f0295fdf29c8f7138efed7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210740"
---
# <a name="getmessages-sample"></a>Ejemplo de GetMessages
En este tema se proporciona código de ejemplo que puede utilizar para recuperar mensajes de una de las tablas sin repudio de mensajes o una de las tablas de línea de negocio (LOB) en un formato legible. Las tablas sin repudio de mensajes incluyen MessageStorageIn y MessageStorageOut de la [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]base de datos de archivo; las tablas LOB incluyen MessageFromLOB y MessageToLOB en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]base de datos.  
  
 Use `GetMessages` para solucionar problemas o desarrollo. De forma predeterminada, el código devuelve una cadena en base 64.  
  
> [!NOTE]
>  El código de ejemplo GetMessages.cs contiene dos secciones de código: uno para recuperar mensajes de una de las tablas LOB y otro para recuperar mensajes de una de las tablas sin repudio. Crear aplicaciones independientes para cada propósito.  
  
### <a name="to-retrieve-messages-from-an-lob-table"></a>Para recuperar mensajes de una tabla LOB  
  
1.  Agregue el siguiente código de ejemplo para el programa:  
  
     `private static string GetLOBMessage(string sMessageSource, string sMessageID)`  
  
2.  Establecer el `sMessageSource` parámetro a la tabla del MessagesFromLOB o MessagesToLOB.  
  
3.  Establecer el `sMessageID` parámetro en el valor de la **MessageID** campo en la base de datos.  
  
    > [!NOTE]
    >  La aplicación devuelve una cadena que contiene el mensaje recuperado.  
  
### <a name="to-retrieve-messages-from-a-non-repudiation-table"></a>Para recuperar mensajes de una tabla sin repudio  
  
1.  Agregue el siguiente código de ejemplo para el programa:  
  
     `private static string GetNRMessage(string sMessageSource, string sMessageID)`  
  
2.  Establecer el `sMessageSource` parámetro a la tabla del MessageStorageIn o MessageStorageOut.  
  
3.  Establecer el `sMessageID` parámetro en el valor de la **RecordID** campo en la base de datos.  
  
    > [!NOTE]
    >  La aplicación devuelve una cadena que contiene el mensaje recuperado.  
  
## <a name="demonstrates"></a>Demostraciones  
 El ejemplo de GetMessages incluye las siguientes dos secciones de código:  
  
-   Una sección muestra cómo recuperar un mensaje binario de una de las tablas sin repudio y convertirlos a un formato legible ASCII.  
  
-   La otra sección muestra cómo recuperar un mensaje de una de las tablas LOB. Dado que un mensaje en una tabla LOB ya está en formato ASCII, esto es una instrucción select de SQL.  
  
    > [!IMPORTANT]
    >  Con fines de demostración, el código de ejemplo proporcionado utiliza una instrucción directa de SQL que es susceptibles de vulnerabilidades de inyección de SQL. En un entorno de producción, se recomienda utilizar procedimientos almacenados de SQL con parámetros, en lugar de la instrucción SQL directa, para evitar estas vulnerabilidades.  
  
## <a name="example"></a>Ejemplo  
 Utilice una de las dos secciones en el siguiente ejemplo de código para recuperar mensajes de una de las tablas sin repudio o una de las tablas LOB.  
  
```  
using System;  
using System.Text;  
using System.Data.SqlClient;   
using Microsoft.Solutions.BTARN.Shared;  
  
namespace Microsoft.Solutions.BTARN.Admin  
{  
  
      /// <summary>  
      /// Summary description for GetMessages.  
      /// </summary>  
      class GetMessages  
      {  
            /// <summary>  
            /// The main entry point for the application.  
            /// </summary>  
            [STAThread]  
            static void Main(string[] args)  
            {  
                  Console.WriteLine(GetLOBMessage("MessagesFromLOB", "bce5b580daf543a990a4f37331f31e42"));  
                  Console.WriteLine(GetLOBMessage("MessagesToLOB", "bce5b580daf543a990a4f37331f31e42"));  
                  Console.WriteLine(GetNRMessage("MessageStorageIn", "dc06e9cfecd746a889dd6ea7beb3ba21"));  
                  Console.WriteLine(GetNRMessage("MessageStorageOut", "dc06e9cfecd746a889dd6ea7beb3ba21"));  
            }  
  
            /// <summary>  
            /// Retrieve a message from the LOB tables in the BTARNDATA database  
            /// </summary>  
            /// <param name="sMessageSource">Can be either MessagesFromLOB or MessagesToLOB</param>  
            /// <param name="sMessageID">The value of the MessageID field in the database</param>  
            /// <returns>Returns a string that contains the retrieved message</returns>        
            private static string GetLOBMessage(string sMessageSource, string sMessageID)  
            {  
                  SqlDataReader localReader = null;  
                  SqlConnection sqlConnection = null;  
                  SqlCommand sqlCommand = null;  
                  string sReturnedMessage="";              
                  string sQuery;  
  
                  sqlConnection = new SqlConnection(RuntimeGlobal.DataDbConnectionString);  
                  sQuery = "SELECT ServiceContent from " + sMessageSource + " WHERE MessageID=N'" + sMessageID +"'";  
  
                  sqlCommand = new SqlCommand(sQuery, sqlConnection);  
                  sqlConnection.Open();  
  
                  localReader = sqlCommand.ExecuteReader();  
  
                  if (localReader.Read())  
                        sReturnedMessage=localReader.GetString(0);  
  
                  localReader.Close();  
                  sqlConnection.Close();        
                  return sReturnedMessage;              
            }  
  
            /// <summary>  
            /// Retrieve a message from the non-repudiation tables in the BTARNArchive database  
            /// </summary>  
            /// <param name="sMessageSource">Can be either MessageStorageIn or MessageStorageOut</param>  
            /// <param name="sMessageID">The value of the RecordID field in the database</param>  
            /// <returns>Returns a string that contains the retrieved message</returns>  
            private static string GetNRMessage(string sMessageSource, string sMessageID)  
            {  
                  SqlDataReader localReader = null;  
                  SqlConnection sqlConnection = null;  
                  SqlCommand sqlCommand = null;  
                  string sReturnedMessage="";              
                  string sQuery;  
  
                  sqlConnection = new SqlConnection(RuntimeGlobal.ArchiveDbConnectionString);  
                  sQuery = "SELECT Content from " + sMessageSource + " WHERE RecordID=N'" + sMessageID +"'";  
  
                  sqlCommand = new SqlCommand(sQuery, sqlConnection);  
                  sqlConnection.Open();  
  
                  localReader = sqlCommand.ExecuteReader();  
  
                  if (localReader.Read())  
                  {  
                        //Determine the size of the field in bytes and create a new byte array  
                        byte[] bData= new byte[localReader.GetBytes(0, 0, null, 0, 0)];  
  
                        //Read the value of the field into bData  
                        localReader.GetBytes(0, 0, bData, 0, bData.Length);  
  
                        //Convert the byte array into a string  
                        sReturnedMessage=Encoding.ASCII.GetString(bData);  
                  }  
  
                  localReader.Close();  
                  sqlConnection.Close();        
                  return sReturnedMessage;              
            }  
      }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de mensajería](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)