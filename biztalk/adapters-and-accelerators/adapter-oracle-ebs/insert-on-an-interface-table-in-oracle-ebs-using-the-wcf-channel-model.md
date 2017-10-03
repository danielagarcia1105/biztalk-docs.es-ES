---
title: "Ejecutar una operación de inserción en una tabla de interfaz en Oracle E-Business Suite mediante el modelo de canal WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a2e5ee3-552b-40a2-aaa6-5391347f1146
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703b00adeb373fe66c4a96c324f13f9c3c5ec655
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-an-insert-operation-on-an-interface-table-in-oracle-e-business-suite-using-the-wcf-channel-model"></a>Ejecutar una operación de inserción en una tabla de interfaz en Oracle E-Business Suite mediante el modelo de canal WCF
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] detecta un conjunto de operaciones Insert, Select, Update y Delete en tablas de la interfaz de Oracle E-Business Suite. Mediante el uso de estas operaciones, puede realizar simple Insert, Select, Update y eliminar instrucciones que califican Where cláusula en una tabla de la interfaz de destino. Este tema proporciona instrucciones sobre cómo realizar una operación de inserción en una tabla de interfaz mediante el modelo de canal WCF.  
  
 Para obtener más información sobre cómo el adaptador es compatible con estas operaciones, vea [operaciones en tablas de interfaz y vistas de interfaz](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md). Para obtener más información acerca de cómo realizar operaciones en Oracle E-Business Suite utilizando el modelo del canal de WCF, vea [información general del modelo del canal WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 El ejemplo de este tema realiza operaciones en la tabla de interfaz MS_SAMPLE_EMPLOYEE. La tabla se crea mediante la ejecución de la secuencia de comandos que se proporciona con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md). Obtener un ejemplo, **InsertOperation**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.  
  
## <a name="the-insert-message"></a>El mensaje de inserción  
 Para llevar a cabo operaciones en Oracle E-Business Suite mediante el modelo de canal WCF, debe tener el mensaje de solicitud específico de la operación. El mensaje de solicitud para realizar una operación de inserción en la tabla de interfaz MS_SAMPLE_EMPLOYEE es similar al siguiente:  
  
```  
<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
  <RECORDSET>  
    <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">  
      <EMP_NO>10050</EMP_NO>  
      <NAME>John Smith</NAME>  
      <DESIGNATION>Manager</DESIGNATION>  
      <SALARY>500000</SALARY>  
      <JOIN_DATE>1999-05-31</JOIN_DATE>  
    </InsertRecord>  
  </RECORDSET>  
</Insert>  
```  
  
 Este mensaje de solicitud inserta un registro con los detalles siguientes:  
  
```  
Employee Number = 10050  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 Debe copiar el mensaje a un archivo, por ejemplo, InsertRequest.xml. Este archivo se usa en este ejemplo para enviar el mensaje de solicitud a Oracle E-Business Suite mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener más información acerca del esquema de mensaje para las operaciones en la tabla, vea [esquemas de mensaje para Insert, Update, Delete y las operaciones de Select](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).  
  
## <a name="creating-a-wcf-channel-application"></a>Crear una aplicación de canal de WCF  
 Esta sección proporciona instrucciones sobre cómo crear una aplicación de canal WCF para realizar una operación de inserción en la tabla de interfaz MS_SAMPLE_EMPLOYEE.  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-table"></a>Para crear una aplicación de canal WCF para insertar registros en la tabla  
  
1.  Cree un proyecto de Visual C# en Visual Studio. De este tema, cree una aplicación de consola.  
  
2.  En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, y `System.Runtime.Serialization`.  
  
3.  Abra el archivo Program.cs y agregue los espacios de nombres siguientes:  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  Crear el enlace y el punto de conexión.  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
  
    ```  
  
5.  Dado que está realizando una operación en una tabla de interfaz, debe establecer el contexto de la aplicación. En este ejemplo, para establecer el contexto de la aplicación, especifique la **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace. Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
6.  Cree y abra el generador de canales. Esta aplicación envía el mensaje de solicitud para Oracle E-Business Suite y recibe una respuesta, por lo tanto, debe implementar la interfaz IRequestChannel.  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
7.  Crear y abrir el canal.  
  
    ```  
    IRequestChannel channel;  
    try  
    {  
       channel = factory.CreateChannel();  
       channel.Open();  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception :" + ex.Message);  
       throw;  
    }  
    ```  
  
8.  Crear y enviar el mensaje de solicitud.  
  
    ```  
    XmlReader readerIn;  
    try  
    {  
       readerIn = XmlReader.Create("InsertRequest.xml");  
       Console.WriteLine("Reader created");  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    Message messageIn;  
    Message messageOut;  
    try  
    {  
       messageIn = Message.CreateMessage(MessageVersion.Default, "InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE", readerIn);  
       messageOut = channel.Request(messageIn);  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    ```  
  
     Al crear el mensaje de solicitud, debe especificar la acción de mensaje que indica la acción que realiza el adaptador en la tabla de interfaz. Para llevar a cabo una operación de inserción en la tabla MS_SAMPLE_EMPLOYEE, la acción de mensaje es `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`. Para obtener información acerca de cómo se puede determinar la acción de mensaje para realizar diversas operaciones en tablas, vea [esquemas de mensaje para Insert, Update, Delete y las operaciones de Select](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).  
  
9. Obtiene el mensaje de respuesta.  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
10. Cierre el mensaje, el canal y el generador de canales.  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
11. Generar el proyecto. Después de compilar el proyecto, debe copiar el mensaje de solicitud, InsertRequest.xml, en la misma ubicación que el proyecto ejecutable. Normalmente, esta ubicación es \bin\Debug\ en el directorio del proyecto.  
  
12. Ejecute la aplicación. El mensaje de respuesta, Response.xml, se guarda en la ubicación especificada en la aplicación. El mensaje de respuesta contiene el número o registros insertados y es similar al siguiente:  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
      <InsertResult>1</InsertResult>  
    </InsertResponse>  
    ```  
  
     El valor "1" indica que se inserta un registro único en la tabla MS_SAMPLE_EMPLOYEE.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)