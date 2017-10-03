---
title: "Ejecutar una operación Insert en la base de datos de Oracle mediante el modelo de canal de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inserting data, using a channel
- WCF channel model, performing an Insert operation
- how to, perform an insert operation using a channel
- channel programming, performing an insert operation
- performing an insert operation, using a channel
ms.assetid: 85c44507-0166-42ef-a908-6098f7a683fc
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540cd06f15ae95dba41636418be273a78c39f447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model"></a>Ejecutar una operación Insert en la base de datos de Oracle mediante el modelo de canal de WCF
Esta sección muestra cómo insertar un registro en una base de datos de Oracle mediante el uso de un canal. Debe especificar un cuerpo del mensaje y una acción de mensaje cuando se envía un mensaje.  
  
## <a name="the-insert-message"></a>El mensaje de inserción  
 El siguiente XML muestra un cuerpo del mensaje para una operación de inserción en el recursos humanos. Tabla de empleados. El conjunto de registros consta de un registro de empleado único. Para obtener más información acerca del esquema de un mensaje de inserción, vea [esquemas de mensaje para insertar básico, Update, Delete y seleccione operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md). Este es el contenido del archivo Employee_Insert.xml usado en el ejemplo.  
  
```  
\<!-- New namespace: http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES -->  
<Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES">  
    \<RECORDSET xmlns:i="http://www.w3.org/2001/XMLSchema-instance">  
        <EMPLOYEESRECORDINSERT>  
            <EMPLOYEE_ID>0</EMPLOYEE_ID>  
            <FIRST_NAME>Anton</FIRST_NAME>  
            <LAST_NAME>Kirilov</LAST_NAME>  
            <EMAIL></EMAIL>  
            <PHONE_NUMBER>555-0198</PHONE_NUMBER>  
            <HIRE_DATE>2007-03-01T00:00:00.0000000</HIRE_DATE>  
            <JOB_ID>FI_ACCOUNT</JOB_ID>  
            <SALARY>5000</SALARY>  
            <COMMISSION_PCT>0.15</COMMISSION_PCT>  
            <MANAGER_ID>108</MANAGER_ID>  
            <DEPARTMENT_ID>100</DEPARTMENT_ID>  
       </EMPLOYEESRECORDINSERT>  
    </RECORDSET>  
</Insert>  
```  
  
## <a name="specifying-the-message-action"></a>Especifica la acción de mensaje  
 Debe especificar una acción de mensaje cuando se envía un mensaje SOAP para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Puede especificar la acción de mensaje cuando se crea el mensaje como en el ejemplo siguiente.  
  
```  
Message messageIn2 = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES/Insert", readerIn2);  
```  
  
 La acción de mensaje en este ejemplo, "/ HR/tabla/empleados/Insert", especifica que una operación de inserción en el recursos humanos. Tabla de empleados que se va a ser realizada  
  
## <a name="sending-the-insert-message"></a>Enviar el mensaje de inserción  
 Este ejemplo muestra cómo realizar una operación de inserción en una tabla de Oracle a través de un canal. El código utiliza la operación SQLEXECUTE expuesta por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para devolver el siguiente valor de una secuencia de Oracle. Este valor, a continuación, se escribe en el campo Id_Empleado en el registro de inserción. Este patrón permite insertar filas en las bases de datos que tienen un valor de clave principal generada automáticamente. Para obtener más información sobre cómo invocar la operación SQLEXECUTE sobre un canal, consulte [ejecutar una operación SQLEXECUTE mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md).  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Xml;  
using System.IO;  
  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
  
using Microsoft.ServiceModel.Adapters;  
using Microsoft.Adapters.OracleDB;  
  
namespace OracleDMLChannel  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create Endpoint  
            EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
  
            // Create Binding  
            OracleDBBinding binding = new OracleDBBinding();  
  
            // Create Channel Factory  
            ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
            factory.Credentials.UserName.UserName = "HR";  
            factory.Credentials.UserName.Password = "TIGER";  
            factory.Open();  
  
            // Create Request Channel  
            IRequestChannel channel = factory.CreateChannel();  
            channel.Open();  
  
            // Send Request  
            System.Xml.XmlReader readerIn = System.Xml.XmlReader.Create("SQLExecute.xml");  
  
            Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
            Message messageOut = channel.Request(messageIn);  
  
            // Get Response XML  
            XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
  
            // Get Employee ID  
            string id = null;  
            XmlDocument doc = new XmlDocument();  
            doc.Load(readerOut);  
            XmlNodeList list = doc.GetElementsByTagName("ColumnValue");  
            if (list.Count > 0) id = list[0].InnerXml;  
  
            // Compose Insert XML  
            XmlDocument insertDoc = new XmlDocument();  
            insertDoc.Load("Employee_Insert.xml");  
  
            // Change Employee ID  
            XmlNodeList empidList = insertDoc.GetElementsByTagName("EMPLOYEE_ID");  
            XmlNode empidNode = empidList[0];  
            empidNode.InnerXml = id;  
  
            // Change email  
            XmlNodeList emailList = insertDoc.GetElementsByTagName("EMAIL");  
            XmlNode emailNode = emailList[0];  
            emailNode.InnerXml = "scotty" + id + "@microsoft.com";  
  
            // Change date  
            XmlNodeList dateList = insertDoc.GetElementsByTagName("HIRE_DATE");  
            XmlNode dateNode = dateList[0];  
            dateNode.InnerXml = "2007-03-01T00:00:00.0000000";  
  
            StringReader strReader = new StringReader(insertDoc.InnerXml);  
            XmlReader readerIn2 = XmlReader.Create(strReader);  
  
            // Send XML  
            Message messageIn2 = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES/Insert ", readerIn2);  
            Message messageOut2 = channel.Request(messageIn2);  
  
            // Close the messages  
            messageOut.Close();  
            messageOut2.Close();  
  
            channel.Close();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)   
 [Crear un canal con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)   
 [Ejecutar una operación SQLEXECUTE mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)   
 [Invocar una función de base de datos de Oracle utilizando el modelo del canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)