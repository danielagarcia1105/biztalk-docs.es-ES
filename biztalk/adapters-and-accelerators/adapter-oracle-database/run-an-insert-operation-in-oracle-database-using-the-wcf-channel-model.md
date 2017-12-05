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
ms.openlocfilehash: 9fd689cbf378f41578c5f46b3067410a184cf650
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="b9200-102">Ejecutar una operación Insert en la base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="b9200-102">Run an Insert Operation in Oracle Database using the WCF Channel Model</span></span>
<span data-ttu-id="b9200-103">Esta sección muestra cómo insertar un registro en una base de datos de Oracle mediante el uso de un canal.</span><span class="sxs-lookup"><span data-stu-id="b9200-103">This section shows how to insert a record into an Oracle database by using a channel.</span></span> <span data-ttu-id="b9200-104">Debe especificar un cuerpo del mensaje y una acción de mensaje cuando se envía un mensaje.</span><span class="sxs-lookup"><span data-stu-id="b9200-104">You must specify both a message body and a message action when you send a message.</span></span>  
  
## <a name="the-insert-message"></a><span data-ttu-id="b9200-105">El mensaje de inserción</span><span class="sxs-lookup"><span data-stu-id="b9200-105">The Insert Message</span></span>  
 <span data-ttu-id="b9200-106">El siguiente XML muestra un cuerpo del mensaje para una operación de inserción en el recursos humanos. Tabla de empleados.</span><span class="sxs-lookup"><span data-stu-id="b9200-106">The following XML shows a message body for an Insert operation on the HR.EMPLOYEES table.</span></span> <span data-ttu-id="b9200-107">El conjunto de registros consta de un registro de empleado único.</span><span class="sxs-lookup"><span data-stu-id="b9200-107">The record set consists of a single employee record.</span></span> <span data-ttu-id="b9200-108">Para obtener más información acerca del esquema de un mensaje de inserción, vea [esquemas de mensaje para insertar básico, Update, Delete y seleccione operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span><span class="sxs-lookup"><span data-stu-id="b9200-108">For more information about the schema of an Insert message, see [Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span> <span data-ttu-id="b9200-109">Este es el contenido del archivo Employee_Insert.xml usado en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b9200-109">This is the contents of the Employee_Insert.xml file used in the example.</span></span>  
  
```  
<!-- New namespace: http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES -->  
<Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES">  
    <RECORDSET xmlns:i="http://www.w3.org/2001/XMLSchema-instance">  
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
  
## <a name="specifying-the-message-action"></a><span data-ttu-id="b9200-110">Especifica la acción de mensaje</span><span class="sxs-lookup"><span data-stu-id="b9200-110">Specifying the Message Action</span></span>  
 <span data-ttu-id="b9200-111">Debe especificar una acción de mensaje cuando se envía un mensaje SOAP para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9200-111">You must specify a message action when you send a SOAP message to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="b9200-112">Puede especificar la acción de mensaje cuando se crea el mensaje como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b9200-112">You can specify the message action when you create the message as in the following example.</span></span>  
  
```  
Message messageIn2 = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES/Insert", readerIn2);  
```  
  
 <span data-ttu-id="b9200-113">La acción de mensaje en este ejemplo, "/ HR/tabla/empleados/Insert", especifica que una operación de inserción en el recursos humanos. Tabla de empleados que se va a ser realizada</span><span class="sxs-lookup"><span data-stu-id="b9200-113">The message action in this example, "/HR/Table/EMPLOYEES/Insert", specifies that an Insert operation on the HR.EMPLOYEES table is to be performed</span></span>  
  
## <a name="sending-the-insert-message"></a><span data-ttu-id="b9200-114">Enviar el mensaje de inserción</span><span class="sxs-lookup"><span data-stu-id="b9200-114">Sending the Insert Message</span></span>  
 <span data-ttu-id="b9200-115">Este ejemplo muestra cómo realizar una operación de inserción en una tabla de Oracle a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="b9200-115">This example shows how to perform an Insert operation on an Oracle table over a channel.</span></span> <span data-ttu-id="b9200-116">El código utiliza la operación SQLEXECUTE expuesta por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para devolver el siguiente valor de una secuencia de Oracle.</span><span class="sxs-lookup"><span data-stu-id="b9200-116">The code uses the SQLEXECUTE operation exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to return the next value of an Oracle SEQUENCE.</span></span> <span data-ttu-id="b9200-117">Este valor, a continuación, se escribe en el campo Id_Empleado en el registro de inserción.</span><span class="sxs-lookup"><span data-stu-id="b9200-117">This value is then written to the EMPLOYEE_ID field in the Insert record.</span></span> <span data-ttu-id="b9200-118">Este patrón permite insertar filas en las bases de datos que tienen un valor de clave principal generada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b9200-118">This pattern enables you to insert rows into databases that have an auto-generated primary key value.</span></span> <span data-ttu-id="b9200-119">Para obtener más información sobre cómo invocar la operación SQLEXECUTE sobre un canal, consulte [ejecutar una operación SQLEXECUTE mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="b9200-119">For more information about invoking the SQLEXECUTE operation over a channel, see [Run a SQLEXECUTE Operation by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b9200-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9200-120">See Also</span></span>  
 <span data-ttu-id="b9200-121">[Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) </span><span class="sxs-lookup"><span data-stu-id="b9200-121">[Develop Oracle Database applications Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) </span></span>  
 <span data-ttu-id="b9200-122">[Crear un canal con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) </span><span class="sxs-lookup"><span data-stu-id="b9200-122">[Create a channel using Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) </span></span>  
 <span data-ttu-id="b9200-123">[Ejecutar una operación SQLEXECUTE mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md) </span><span class="sxs-lookup"><span data-stu-id="b9200-123">[Run a SQLEXECUTE Operation by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md) </span></span>  
 [<span data-ttu-id="b9200-124">Invocar una función de base de datos de Oracle utilizando el modelo del canal de WCF</span><span class="sxs-lookup"><span data-stu-id="b9200-124">Invoke a Function in Oracle Database Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)