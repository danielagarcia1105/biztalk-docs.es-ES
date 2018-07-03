---
title: PartyResolution (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, parties
- orchestrations, examples
- parties, examples
- parties, orchestrations
- examples, routing
- orchestrations, parties
- examples, orchestrations
- examples, messages
- routing, messages
- messages, routing
ms.assetid: 220e6bc5-6f04-4f37-b0d0-f11c2cc14422
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35334b61199d758a5eafe8623ea576a047799925
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984437"
---
# <a name="partyresolution-biztalk-server-sample"></a>PartyResolution (ejemplo de BizTalk Server)
En el ejemplo de PartyResolution se muestra cómo utilizar orquestaciones de BizTalk con resolución de entidades para enrutar mensajes a uno de los dos destinatarios posibles.  

## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo se ejecutan varias orquestaciones que muestran los distintos roles siguientes:  

-   Orquestación del comprador, que se  utiliza para iniciar el procesamiento de mensajes de pedidos.  

-   Orquestación del proveedor, que muestra tanto la resolución de entidades entrantes como salientes.  

-   Orquestaciones ShipmentAgency1 y ShipmentAgency2, que responden a la orquestación del proveedor basada en el destino de envío del pedido.  

## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 La resolución de entidades se refiere al proceso de determinar quién envía un mensaje (es decir, qué entidad). Por ejemplo, es posible que desee habilitar a enviar mensajes solo a las entidades conocidas. La resolución de entidades salientes es el proceso por el que se determina a qué entidades se les debería enviar un mensaje.  

 Además de la resolución de entidades, en este ejemplo se muestra cómo implementar y usar roles. Por ejemplo, para procesar el envío de su producto, se crea un puerto de envío al que se envía un documento para indicar al remitente que envíe su producto. Si tiene que elegir entre varios remitentes, puede crear un rol de remitente en su orquestación en vez de crear varios puertos de envío cuya única diferencia sea la dirección URL del remitente. Puede enviar mensajes relacionados con el envío del producto al rol de remitente. Cree entidades y asocie un puerto de envío a cada entidad y certificado de entidades. Por último, dé de alta cada entidad al rol de remitente para habilitarla. En la orquestación, puede especificar dinámicamente a qué remitente está enviando el mensaje.  

 Este ejemplo también muestra cómo utilizar correlaciones para que el mensaje entrante coincida con la instancia de orquestación derecha.  

- A continuación se muestran los flujos de procesos empresariales para el comprador, el proveedor y las agencias de envío:  

- Flujo de procesos empresariales del comprador:  

  1.  Recibir mensajes de pedido de departamentos internos como archivo .xml.  

  2.  Enviar mensajes de pedido al proveedor.  

- Flujo de procesos empresariales del proveedor:  

  1.  Resuelve la entidad (resolución de entidad entrante) para actualizar la entidad de origen basada en el certificado de firma.  

  2.  Recibir un mensaje de activación (pedido) del comprador.  

  3.  Enviar un mensaje de confirmación de pedido al comprador.  

  4.  Comprobar el país de entrega.  

  5.  Resolver la entidad saliente para encontrar la agencia de envío que se va a utilizar. Si EE.UU. es el país, la agencia de envío es ShipmentAgency2. Si Canadá es el país, la agencia de envío es ShipmentAgency1.  

  6.  Enviar un mensaje de solicitud de envío de pedido a la agencia de envío correspondiente.  

  7.  Recibir el mensaje de confirmación de envío de pedido de la agencia de envío correspondiente.  

  8.  Enviar un mensaje de consejo de envío a la agencia de envío correspondiente.  

  9. Recibir un mensaje de confirmación de consejo de envío de la agencia de envío correspondiente.  

  10. Enviar un mensaje final de notificación de entrega de pedido al comprador.  

- Flujo de procesos empresariales de la agencia de envío (igual para las dos agencias de envío):  

  1.  Recibir el mensaje de solicitud de envío de pedido del proveedor.  

  2.  Generar y enviar un mensaje de confirmación para el mensaje de solicitud de envío de pedido.  

  3.  Recibir un mensaje de consejo de envío del proveedor.  

  4.  Generar y enviar un mensaje de confirmación para el mensaje de consejo de envío.  

  Las instrucciones siguientes explican cómo se diseña este ejemplo:  

- La orquestación BuyerProcess.odx recibe un mensaje y utiliza la canalización personalizada MimePartyResSendPipeline para codificar el mensaje y enviarlo al proveedor. Esta operación se realiza mediante el Diseñador de canalizaciones para generar e implementar una canalización de envío personalizada. Antes de enviar el mensaje al proveedor, el mensaje se firma digitalmente con la clave privada del comprador que se especifica en Propiedades del grupo de BizTalk de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

- La orquestación SupplierProcess.odx utiliza la canalización personalizada MimePartyResReceivePipeline, que incluye un componente descodificador de MIME/SMIME para descodificar el mensaje y realizar resolución de entidades entrantes mediante la clave pública del comprador para resolver y validar la identidad del comprador. Esta operación se realiza al generar e implementar una canalización de recepción personalizada.  

- La orquestación del proveedor inicia el POCorrelationSets, que está definido para que se base en una propiedad promocionada PONo. La propiedad PONo se utiliza para que coincidan los mensajes entrantes y salientes de esta instancia de orquestación en la fase posterior, ya que existen varias acciones de envío y recepción a través de toda la orquestación.  

- La orquestación del proveedor implementa vínculos de rol para que se ocupen de la resolución de entidades entrantes y salientes. La orquestación del proveedor usa dos tipos de vínculo de rol:  

  -   Tipo de vínculo de rol Buyer_Supplier  

  -   Tipo de vínculo de rol Supplier_Shipment  

- En el Buyer_Supplier **vínculo de función** forma, el proveedor se encuentra en el rol de proveedor y el comprador se encuentra en el rol de consumidor porque el proveedor recibe el primer mensaje del comprador. Cuando la orquestación del proveedor envía la confirmación al rol de comprador, hay un puerto de envío asociado al comprador, y se envía el mensaje al comprador a través del puerto de envío especificado. Para buscar el puerto de envío, haga clic en **BuyerAgency** en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración y, a continuación, haga clic en **propiedades**. El puerto de envío se muestra bajo **puertos de envío**.  

- Después, la orquestación utiliza la expresión siguiente para devolver la información de socios comerciales y escribe un archivo XML en una carpeta mediante una llamada a un ensamblado externo denominado CheckPartyName.  

  ```  
  Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty)  
  ```  

- En el Supplier_Shipment **vínculo de función** forma, el rol de envío contiene un puerto de envío con dos operaciones que se usan para enviar el mensaje del proveedor a la Agencia de envío adecuado según la entidad de destino. El rol de proveedor contiene un puerto de recepción con dos operaciones que se usan para recibir la respuesta de la agencia de envío. La correlación se utiliza al enviar y recibir estos mensajes y se basa en el PONo.  

  > [!NOTE]
  >  Al enlazar la orquestación del proveedor, se encontrará con que solo es necesario que se enlace un puerto de envío y dos puertos de recepción. Esto se debe a que los puertos de envío de las entidades de destino ya están enlazados con las entidades. Además, uno de los puertos de recepción en la orquestación contiene dos operaciones de recepción, por lo que aunque vea tres **recepción** formas, sólo dos de ellos deben estar enlazados.  

- La orquestación del proveedor utiliza la primera línea en el código siguiente para obtener la agencia de envío llamando a un ensamblado externo denominado QueryShipmentCatalogComponent. A continuación, usa la segunda línea para establecer la entidad de destino del rol de envío.  

  ```  
  strShipmentName= objQueryShipmentCatalog.GetShipmentDetails(POMessage.MessagePart_1.POHeader.Address.Country);  
  Supplier_Shipment(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party(strShipmentName,"OrganizationName");  
  ```  

- Shipper1Process.odx y Shipper2Process.odx se generan para recibir el pedido de envío y el consejo de envío de SupplierProcess.odx y enviar la respuesta de nuevo a SupplierProcess.odx. En las dos orquestaciones de remitente, se utiliza la correlación y el tipo de correlación se basa en la propiedad promocionada PONo.  

## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de la ruta de acceso\>* \Orchestrations\PartyResolution\  

 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  


|                                                                                                                                 Archivos                                                                                                                                 |                                                                                                                                                              Descripción                                                                                                                                                              |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                      BuyerBinding.xml ShippingAgency1Binding.xml, ShippingAgency2Binding.xml, SupplierBinding.xml,                                                                                      |                                                                                                                                            Se usa para la instalación automatizada, como el enlace de puerto.                                                                                                                                             |
|                                                                                                                               Cleanup.bat                                                                                                                               |                                                                   Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global. Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.                                                                    |
|                                                                                                                           PartyResolution.sln                                                                                                                           |                                                                                                                              Archivo de solución que contiene todos los proyectos en varias subcarpetas.                                                                                                                               |
|                                                                                                                            PurchaseOrder.xml                                                                                                                            |                                                                                                                                                           Pedido de entrada de ejemplo.                                                                                                                                                            |
|                                                                                                                                Setup.bat                                                                                                                                |                                                                                                                                         Se utiliza para crear e iniciar partes de este ejemplo.                                                                                                                                         |
|                                                                                                    En la carpeta \Buyer:<br /><br /> Buyer.btproj BuyerProcess.odx                                                                                                     |                                                                                                                             Proyecto y orquestación de BizTalk utilizados para implementar al comprador en este ejemplo.                                                                                                                             |
|                                                                                                             En la carpeta \Catalog:<br /><br /> Catalog.xml                                                                                                             |                                                                                                                         Se utiliza para determinar la agencia de envío en función del destino de envío especificado en el pedido.                                                                                                                          |
|                                                                                      En la carpeta \CheckPartyName:<br /><br /> AssemblyInfo.cs, CheckPartyName.csproj, Class1.cs                                                                                       |                                                                                                  Archivos de origen y de proyecto de Visual C# de Microsoft para la aplicación CheckPartyName utilizada para obtener acceso a las propiedades de la entidad de origen.                                                                                                   |
|                                                                En la carpeta \FilePolling:<br /><br /> App.ico, AssemblyInfo.cs, FilePolling.cs, FilePolling.csproj, FilePolling.resx, FilePolling.sln,                                                                 |                                                                 Solución, proyecto, origen y archivos asociados de Visual C# para la aplicación FilePolling.<br /><br /> Utilice esta aplicación para mantenerse informado acerca del estado de procesamiento de este escenario automatizado.                                                                  |
|                                                                            En la carpeta \Pipeline\projectschema:<br /><br /> MimePartyResReceivePipeline.btp, MimePartyResSendPipeline.btp                                                                             |                                                                                             Archivos de canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que usan los distintos roles en este ejemplo.                                                                                             |
|                                                                En la carpeta \QueryShipmentCatalogComponent:<br /><br /> AssemblyInfo.cs, QueryShipmentCatalog.cs, QueryShipmentCatalogComponent.csproj                                                                 | Archivos de origen y proyecto de Visual C # para el componente QueryShipmentCatalog que se utiliza para obtener acceso al catálogo de envío definido en el archivo Catalog.xml.<br /><br /> El componente QueryShipmentCatalog determina qué agencia de envío utilizará el proveedor. Utiliza datos de Catalog.xml para determinar el mejor remitente basado en la geografía. |
| En la carpeta \Schemas:<br /><br /> PODeliveryReceipt.xsd, POPropertySchema.xsd, PurchaseOrder.xsd, PurchaseOrderAcknowledgement.xsd, Schemas.btproj, ShipmentAdvice.xsd, ShipmentAdviceAcknowledgement.xsd, ShipmentOrderAcknowledgement.xsd, ShipmentOrderRequest.xsd |                                                                                                                                           Esquemas que varios roles usan en este ejemplo.                                                                                                                                           |
|                                                                  En la carpeta \ShipmentAgency1:<br /><br /> ShipmentAdviceAck.btm, ShipmentAgency1.btproj, ShipmentOrderAck.btm, Shipper1Process.odx                                                                   |                                                                                                                      Asignaciones, orquestación y proyecto de BizTalk que se utilizan para implementar ShipmentAgency1 en este ejemplo.                                                                                                                       |
|                                                                  En la carpeta \ShipmentAgency2:<br /><br /> ShipmentAdviceAck.btm, ShipmentAgency2.btproj, ShipmentOrderAck.btm, Shipper2Process.odx                                                                   |                                                                                                                      Asignaciones, orquestación y proyecto de BizTalk que se utilizan para implementar ShipmentAgency2 en este ejemplo.                                                                                                                       |
|                                     En la carpeta \Supplier:<br /><br /> PO_POAck.btm, PO_ShipmentOrderRequest.btm, ShipmentAdviceAck_PODeliveryReceipt.btm, ShipmentOrder_ShipmentAdvice.btm, Supplier.btproj, SupplierProcess.odx                                     |                                                                                                                        Asignaciones, orquestación y proyecto de BizTalk que se utilizan para implementar al remitente en este ejemplo.                                                                                                                        |

## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  

> [!NOTE]
>  Antes de generar e inicializar este ejemplo, se debe asegurar de que el host En curso de BizTalk predeterminado está configurado como Autenticación de confianza. Para obtener más información, consulte [recomendaciones de seguridad en tiempo de ejecución de BizTalk Server](../core/biztalk-server-runtime-security-recommendations.md).  

 El componente de canalización MIME no es compatible con una instancia de host de 64 bits. El host asociado con el controlador de envío y de recepción para el adaptador de archivo debe configurarse como un host de solo 32 bits. Para obtener más información sobre este, consulte [cómo modificar las propiedades de Host](../core/how-to-modify-host-properties.md). Si ya tiene un host de solo 32 bits configurado en el sistema y desea usarlo, vea [configurar el adaptador de archivo](../core/configure-the-file-adapter.md) para obtener instrucciones sobre cómo configurar hosts asociados con el adaptador de archivo de envío y controlador de recepción.  

 El certificado que se menciona en esta sección debe agregarse al almacén Personal de la cuenta de inicio de sesión configurada para la instancia de host en proceso predeterminada de BizTalk que va a firmar los mensajes.  

 De forma predeterminada, el archivo setup.bat mencionado más abajo instalará el ejemplo de resolución de entidad en la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] predeterminada. Para modificar el archivo setup.bat e implementar el ejemplo en una nueva aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe abrir el archivo setup.bat y reemplazar la sección precedida por la instrucción `@ECHO Deploy Assemblies...` por lo siguiente:  

```  
@ECHO Deploy Assemblies...  

btstask AddApp -ApplicationName:PartyResolutionSample -Description:"Party Resolution Orchestration sample from the SDK"  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Schemas\bin\Release\Schemas.dll -Options:GacOnAdd  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Pipeline\projectschema\bin\Release\ProjectSchema.dll -Options:GacOnAdd   
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Buyer\bin\Release\Buyer.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%BuyerBindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:ShipmentAgency1\bin\Release\ShipmentAgency1.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%ShipmentAgency1BindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:ShipmentAgency2\bin\Release\ShipmentAgency2.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%ShipmentAgency2BindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Supplier\bin\Release\Supplier.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%SupplierBindingFileName%  
```  

#### <a name="to-build-and-initialize-the-partyresolution-sample"></a>Para crear e iniciar el ejemplo PartyResolution  

1. En una ventana de comandos, desplácese a la siguiente carpeta:  

    \<*Ejemplos de la ruta de acceso*> \Orchestrations\PartyResolution  

2. Ejecute el archivo Setup.bat que realiza las acciones siguientes:  

   - Compila los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo e implementa los ensamblados resultantes.  

   - Crea y enlaza los puertos de envío y recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

      Puede recibir las advertencias siguientes o similares durante el proceso de instalación. Los puede pasar por alto sin que afecte a la seguridad.  

     ```  
     "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\PartyResolution.sln" (Buildtarget) (1) ->  
     "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5) ->  
     "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5:2) ->  
     (CompileODX target) ->  
       C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(831,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  
       C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(841,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  

     ```  

3. Iniciar **símbolo del sistema de Visual Studio**.  

4. Escriba los siguientes comandos para instalar los ensamblados en la caché de ensamblados global:  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Schemas\bin\Release\schemas.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Pipeline\projectschema\bin\Release\ProjectSchema.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Buyer\bin\Release\Buyer.dll   

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency1\bin\Release\ShipmentAgency1.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency2\bin\Release\ShipmentAgency2.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Supplier\bin\Release\Supplier.dll  

5. Obtenga un certificado de correo electrónico seguro de una entidad emisora de certificados (CA). La entidad emisora de certificados podría ser una autoridad de terceros o la autoridad dentro de su organización. Después de obtener el certificado, exporte la clave pública y la clave privada.  

6. Para importar la clave privada al almacén Personal de la cuenta de inicio sesión de la instancia de host, así como la clave pública al almacén Otras personas del equipo local, haga lo siguiente:  

   1. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda el grupo de BizTalk y, a continuación, expanda **configuración de plataforma**.  

   2. Haga clic en **instancias de Host** y busque la cuenta de inicio de sesión que aparece para la instancia de host en proceso predeterminada. En una instalación predeterminada, el host en proceso predeterminado debe denominarse BizTalkServerApplication.  

   3. Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**. En el **ejecutar** , escriba **mmc.exe**y, a continuación, haga clic en **Aceptar**. Escriba la contraseña correcta de la cuenta de inicio de sesión de la instancia de host para abrir Microsoft Management Console (MMC) en esa cuenta.  

   4. En el menú **Archivo** , haga clic en **Agregar o quitar complemento**.  

   5. En el **agregar o quitar complementos** cuadro de diálogo, seleccione **certificados**y, a continuación, haga clic en **agregar**.  

   6. En el **complemento certificados** cuadro de diálogo, seleccione **mi cuenta de usuario**y, a continuación, haga clic en **finalizar**.  

   7. En el **agregar o quitar complementos** cuadro de diálogo, seleccione **certificados**y, a continuación, haga clic en **agregar**.  

   8. En el **complemento certificados** cuadro de diálogo, seleccione **cuenta de equipo**y, a continuación, haga clic en **siguiente**.  

   9. En el **Seleccionar equipo** cuadro de diálogo, seleccione **ordenador**y, a continuación, haga clic en **finalizar**.  

   10. En el **agregar o quitar complementos** cuadro de diálogo, haga clic en **Aceptar**.  

   11. Expanda el **certificados - usuario actual** nodo y, a continuación, expanda **Personal**. Haga clic en **certificados**, haga clic en **todas las tareas**y, a continuación, haga clic en **importación**.  

   12. Importe la clave privada y proporcione una contraseña en el asistente.  

   13. Expanda el **certificados (equipo Local)** nodo y, a continuación, expanda **otras personas**. Haga clic en **certificados**, haga clic en **todas las tareas**y, a continuación, haga clic en **importación**.  

   14. Importe la clave pública.  

7. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **grupo de BizTalk** nodo y, a continuación, haga clic en **propiedades**. En el **grupo de BizTalk - propiedades de grupo** cuadro de diálogo, seleccione **certificado**.  

8. En el **certificado** cuadro de diálogo, haga clic en **examinar** y seleccione la clave privada que acaba de importar. El certificado que aquí se especifica se usa para firmar el mensaje de salida. Haga clic en **Aceptar**.  

9. Para actualizar la entidad BuyerAgency en este ejemplo, haga lo siguiente:  

   1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **partes**.  

   2. Haga clic en **BuyerAgency** y, a continuación, haga clic en **propiedades**. En el **buyeragency – propiedades de entidad** cuadro de diálogo, seleccione **General**.  

   3. En el **alias** sección del cuadro de diálogo, agregar un nuevo alias con el nombre y el calificador establecido en **WindowsUser**. Establezca el valor en un nombre de usuario en formato de \<dominio\nombre de usuario > (por ejemplo, undominio\unusuario).  

   4. Seleccione **certificado** y, a continuación, haga clic en **examinar** y seleccione la clave pública que acaba de importar. Se utiliza el certificado especificado aquí para validar la identidad del remitente del mensaje entrante. Haga clic en **Aceptar**.  

10. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **configuración de plataforma**y, a continuación, seleccione **Hosts**.  

11. Haga clic en **BizTalkServerApplication** y, a continuación, haga clic en **propiedades**. En el **BizTalkServerApplication - propiedades de Host** cuadro de diálogo, seleccione **certificados**.  

12. Haga clic en **examinar** y seleccione la clave privada que acaba de importar. El certificado que aquí se especifica se usa para descifrar los mensajes de entrada. Haga clic en **Aceptar**.  

13. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **configuración de plataforma**y, a continuación, seleccione **instancias de Host**.  

14. Haga clic en **BizTalkServerApplication** y, a continuación, haga clic en **reiniciar**.  

## <a name="running-this-sample"></a>Ejecución del ejemplo  

#### <a name="to-run-the-partyresolution-sample"></a>Para ejecutar el ejemplo de PartyResolution  

1.  Ejecute FilePolling.exe desde la carpeta siguiente:  

     *\<Ejemplos de la ruta de acceso >* \Orchestrations\PartyResolution\FilePolling\bin\Debug  

2.  Haga clic en **iniciar sondeo**.  

3.  Pegue una copia del archivo de instancia de pedido proporcionado PurchaseOrder.xml en la carpeta siguiente:  

     *\<Ejemplos de la ruta de acceso >* \Orchestrations\PartyResolution\FileDrop\PurchaseOrder  

4.  Observe la secuencia de mensajes que se proporcionan en forma de cuadros de mensajes, que le mantienen informado acerca del progreso del ejemplo:  

    1.  Cuando el proveedor recibe el pedido del comprador.  

    2.  Cuando se recibe una solicitud de envío de pedido de agencia de envío 1 o 2.  

    3.  Cuando la agencia de envío 1 o 2 recibe un consejo de envío.  

    4.  Cuando el proveedor envía la confirmación de entrega de pedido al comprador.  

5.  Haga clic en **Exit** para cerrar el programa de sondeo de archivos.  

> [!NOTE]
>  Puede cambiar la ficha País de PurchaseOrder.xml a "EE. UU." y, a continuación, repetir los pasos 2 y 3. Observe que el pedido de envío se envía ahora a la agencia de envío 2.  

## <a name="uninstalling-this-sample"></a>Desinstalar este ejemplo  

#### <a name="to-uninstall-the-partyresolution-sample"></a>Para desinstalar el ejemplo PartyResolution  

1. En un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie el directorio (**cd**) a \< *ruta de ejemplos*> \Orchestrations\ PartyResolution\\.  

2. Ejecute Cleanup.bat.  

## <a name="see-also"></a>Vea también  
 [Componente de canalización de resolución de entidades](../core/party-resolution-pipeline-component.md)   
 [Cómo configurar el componente de canalización de codificador de MIME / SMIME](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)   
 [Cómo configurar el componente de canalización de descodificador de MIME / SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)   
 [Orquestaciones (carpetas de ejemplos de BizTalk Server)](../core/orchestrations-biztalk-server-samples-folder.md)