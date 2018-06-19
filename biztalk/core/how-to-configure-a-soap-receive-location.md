---
title: Cómo configurar ubicación de recepción de SOAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], virtual directories
- SOAP adapters, code samples
- configuring [SOAP adapters], receive locations
- virtual directories, SOAP adapters
- SOAP adapters, receive locations
- code samples, SOAP adapters
- configuring [SOAP adapters], code samples
- SOAP adapters, virtual directories
- receive locations, SOAP adapters
ms.assetid: 7e348409-9181-47e4-b3c0-c73eb2acffa3
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b33886296441082ea7d7e83b92659f81140d71f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250164"
---
# <a name="how-to-configure-a-soap-receive-location"></a>Cómo configurar una ubicación de recepción de SOAP
Puede configurar una ubicación de recepción SOAP mediante programación o con la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 **Cómo configurar un ubicación de recepción SOAP mediante programación**  
  
 El modelo de objetos para el Explorador de BizTalk permite crear y configurar ubicaciones de recepción mediante programación. El modelo de objetos del explorador de BizTalk expone la**IReceiveLocation** recibir interfaz de configuración de ubicación que tenga un **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta una bolsa de propiedades de configuración de ubicación de recepción SOAP con formato de un par de nombre y valor de cadenas XML. Para establecer esta propiedad en el modelo de objetos del explorador de BizTalk, debe establecer el **InboundTransportLocation** propiedad de la **IReceiveLocation** interfaz.  
  
 El **TransportTypeData** propiedad de la **IReceiveLocation** interfaz no tiene que establecerse. Si no se establece, el adaptador de SOAP utiliza los valores predeterminados de la configuración de ubicación de recepción SOAP que se incluyen en la siguiente tabla.  
  
 La siguiente tabla enumera las propiedades de configuración que se pueden establecer en el modelo de objetos del Explorador de BizTalk para la ubicación de recepción SOAP.  
  
|Nombre de la propiedad|Tipo|Description|  
|-------------------|----------|-----------------|  
|**URI**|String|Directorio virtual que contiene el servicio Web en el servidor de implementación.|  
|**AddressableURI**|String|Campo de dirección pública que contiene la dirección URL completa a la que se puede llamar.<br /><br /> Valor predeterminado: en blanco|  
|**UseSSO**|Boolean|Especifica si el adaptador de SOAP emite el vale de inicio de sesión único para los mensajes que llegan a esta ubicación de recepción.<br /><br /> Valor predeterminado: False|  
  
 Utilice el siguiente formato para establecer las propiedades:  
  
```  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
```  
  
 El **URI** y **AddressableURI** propiedades se establecen mediante el **dirección** y **PublicAddress** propiedades de la ubicación de recepción objeto.  
  
 El siguiente fragmento de código muestra la creación de una ubicación de recepción SOAP:  
  
```  
// Use BizTalk Explorer object model to create new SOAP receive location.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  
  
// Add a new Request-Response port  
ReceivePort receivePort = explorer.AddNewReceivePort(true);  
receivePort.Name = "SampleReceivePort";  
receivePort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
  
// Add primary SOAP receive location  
ReceiveLocation receiveLocation = receivePort.AddNewReceiveLocation();  
receiveLocation.Name = "SampleReceiveLocation";  
receiveLocation.Address = "/PurchaseOrder/POOrchestration.asmx";  
receiveLocation.TransportType = explorer.ProtocolTypes["SOAP"];  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
receiveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
foreach (ReceiveHandler receiveHandler in explorer.ReceiveHandlers)  
{  
if (receiveHandler.TransportType.Name == receiveLocation.TransportType.Name)  
{  
receiveLocation.ReceiveHandler = receiveHandler;   
}  
}  
  
// Save  
explorer.SaveChanges();   
```  
  
 **Cómo configurar un SOAP ubicación de recepción con la consola de administración de BizTalk Server**  
  
 Puede establecer variables de adaptador de ubicación de recepción SOAP en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si no hay propiedades establecidas en la ubicación de recepción, se usarán los valores predeterminados del controlador de recepción establecidos en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  Antes de realizar los siguientes procedimientos, debe haber agregado un puerto de recepción. Para obtener más información, consulte [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
  
### <a name="to-configure-variables-for-a-soap-receive-location"></a>Para configurar variables para una ubicación de recepción SOAP  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el aplicación que desea crear una ubicación de recepción.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en el panel izquierdo, haga clic en el **puerto de recepción** nodo. A continuación, en el panel de la derecha, haga clic con el botón secundario en el puerto de recepción asociado con una ubicación de recepción existente o que desee asociar con una nueva ubicación de recepción. A continuación, haga clic en **Propiedades**.  
  
3.  En el **propiedades de puerto de recepción** cuadro de diálogo, en el panel izquierdo, seleccione **ubicaciones de recepción**y, a continuación, en el panel derecho, haga doble clic en otra ubicación de recepción o haga clic en **New**para crear una nueva ubicación de recepción.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **transporte** junto a la sección **tipo**, seleccione **SOAP** en la lista desplegable, y, a continuación, haga clic en **configurar**.  
  
5.  En el **propiedades de transporte SOAP** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Directorio virtual más archivo .asmx de servicio Web**|Indicar el archivo .asmx creado por el Asistente para publicación de servicios Web de BizTalk.<br /><br /> El formato del mensaje es similar al siguiente:<br /><br /> /PurchaseOrder/POOrchestration.asmx<br /><br /> Donde la ubicación completa del archivo .asmx es http://localhost/PurchaseOrder/POOrchestration.asmx. **Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.|  
    |**Dirección pública**|Especificar el URI completo de la ubicación de recepción. El valor de esta propiedad es una combinación del nombre del servidor y el directorio virtual. El URI especificado debe designar la dirección URL del sitio web público para que los socios comerciales se conecten cuando envíen mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].<br /><br /> Esta información es opcional y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no la usa. Este parámetro está disponible para permitir a los administradores documentar la dirección URL pública a la que está vinculada la ubicación de recepción.|  
    |**Usar el inicio de sesión único**|Indicar que el adaptador de SOAP utilice el inicio de sesión único (SSO) empresarial. **Nota:** el Asistente para publicación de servicios Web de BizTalk permite utilizar SharePoint Portal Server Single Sign-On; esta propiedad solo habilita Enterprise Single Sign-On.|  
  
6.  Haga clic en **Aceptar**.  
  
7.  En el **propiedades de la ubicación de recepción** diálogo cuadro, escriba los valores adecuados para completar la configuración de la ubicación de recepción y, a continuación, haga clic en **Aceptar** para guardar la configuración. Para obtener información sobre la **propiedades de ubicaciones de recepción** cuadro de diálogo, vea [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
 La configuración de seguridad que utiliza la ubicación de recepción SOAP se establece en IIS. De forma predeterminada, la ubicación de recepción SOAP no está establecida para usar autenticación anónima.  
  
 Si bien el cliente SOAP llama al servicio Web, el adaptador de SOAP autentica el cliente SOAP usando autenticación anónima, básica, implícita o integrada de Windows. Si se comprueba el usuario, se pasa el contexto del usuario al controlador de recepción.  
  
> [!NOTE]
>  No será válida ninguna configuración de IIS que haga que SOAP y HTTP compartan el mismo proceso. Sólo puede haber un receptor aislado por proceso.  
  
### <a name="to-update-a-virtual-directory-to-use-aspnet-40"></a>Para actualizar un directorio virtual con el fin de usar ASP.NET 4.0  
  
1.  Inicie el Administrador de Internet Information Services (IIS). Haga clic en **iniciar**, haga clic en **todos los programas**y haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  Si necesita conectarse a un servidor IIS remoto, haga clic con el **Internet Information Services** nodo y, a continuación, haga clic en **conectar**.  
  
3.  Escriba el nombre de equipo del servidor IIS remoto y las credenciales si es necesario.  
  
4.  Expanda el nombre del servidor que aloja el sitio Web o el directorio virtual que se va a actualizar.  
  
5.  Expanda **sitios**.  
  
6.  Expanda **sitio Web predeterminado**.  
  
7.  Expanda el sitio web predeterminado para ver los directorios virtuales que contiene.  
  
8.  Haga clic en el directorio virtual que desea actualizar para usar ASP.NET 4.0, haga clic en **administrar la aplicación**y, a continuación, haga clic en **configuración avanzada**. El **grupo de aplicaciones** campo muestra el grupo de aplicaciones definido para el directorio virtual seleccionado. Haga clic en **Aceptar**.  
  
9. En la ventana del Administrador de Internet Information Services (IIS), haga clic en **grupos de aplicaciones**. El panel de detalles muestra una lista de grupos de aplicaciones del servidor.  
  
10. Haga clic en el grupo de aplicaciones establecido en el paso 8 y, a continuación, haga clic en **configuración básica**.  
  
11. En el **Modificar grupo de aplicaciones** diálogo cuadro, cambie lo siguiente:  
  
    -   **Versión de .NET framework** a **4.0**  
  
    -   **Modo de canalización administrada** a **clásico**  
  
12. Haga clic en **Aceptar** para aplicar los cambios.  
  
## <a name="see-also"></a>Vea también  
 [Consumir servicios Web](../core/consuming-web-services.md)