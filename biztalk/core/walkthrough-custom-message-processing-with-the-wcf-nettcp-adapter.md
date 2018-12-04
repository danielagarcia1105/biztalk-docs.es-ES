---
title: 'Tutorial: Mensaje personalizado procesamiento con el adaptador de WCF-NetTcp | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b56b7492-2ea0-4c63-8f1b-430eb277517d
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39f765e1e99363440d6c122f5e5f174ea50dd761
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826348"
---
# <a name="walkthrough-custom-message-processing-with-the-wcf-nettcp-adapter"></a>Tutorial: Mensaje personalizado procesamiento con el adaptador de WCF-NetTcp
En este tutorial, un cliente de [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] envía un mensaje de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] que contiene datos binarios de imagen JPEG integrados a una ubicación de recepción de BizTalk mediante el adaptador de WCF-NetTcp. Se extrae la imagen JPEG codificada en binario con una instrucción XPath (con codificación de nodo Base64) a través de la **cuerpo de mensaje entrante** configuración en la configuración del adaptador. El procesamiento de XPath difiere del método predeterminado en que usa [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para controlar los mensajes entrantes. En el método de forma predeterminada, el adaptador obtiene todo el contenido de la **cuerpo** elemento de la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] del mensaje y, a continuación, se envía a la base de datos de BizTalk MessageBox. El procesamiento de mensajes de XPath extrae partes específicas de un mensaje de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] entrante para crear un mensaje de BizTalk personalizado. En este ejemplo de procesamiento de XPath localiza un elemento XML denominado **SendPicture** en entrante [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] mensaje (que se encuentra en formato XML). Después de encontrar ese elemento, XPath extrae su valor como un objeto codificado en Base64 y coloca el valor binario en un mensaje de BizTalk. El mensaje se publica en la base de datos de cuadro de mensajes y luego se pasa a un puerto de envío de archivos con la ayuda de una suscripción de filtro de puertos de envío. No se usa ninguna orquestación en este ejemplo, y todo el procesamiento se realiza mediante la mensajería de BizTalk con XPath.  

 Se usa un adaptador de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] para comunicarse con clientes [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] y los servicios remotos de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  Permite publicar las orquestaciones y los esquemas como servicios de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y también proporciona la capacidad de que una orquestación consuma servicios WCF externos. El adaptador de WCF-NetTcp usa el **NetTcpBinding** enlace, lo que significa que el transporte TCP debe usar una codificación de mensajes binaria optimizada. El adaptador de WCF-NetTcp consta de un adaptador de envío y un adaptador de recepción. Proporciona acceso completo a características de confiabilidad, seguridad y transacciones de SOAP.  

 Cuando concluya el tutorial, comprenderá cómo se realizan las tareas siguientes:  

- Importar, mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], un archivo MSI para crear un puerto de envío, un puerto de recepción y una ubicación de recepción.  

- Mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de consola, configure un [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] ubicación de recepción para ejecutar una instrucción XPath para extraer datos desde el **SendPicture** elemento de la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] mensaje.  

> [!NOTE]
>  El **hosttrusted** elemento especifica si el host asociado con el controlador de recepción es de confianza. En el archivo bindings.xml, se establece el valor predeterminado `false` porque en el ejemplo no se tiene en cuenta el servicio de inicio de sesión único (SSO) empresarial de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. SSO permite el paso de credenciales de usuario a través de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para integrar aplicaciones de terceros en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El valor `false` impide que un mensaje de BizTalk pase a través de un servicio de BizTalk como parte del procesamiento de SSO.  

## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo los pasos descritos en este ejemplo asegurarse de que el entorno instala los siguientes requisitos previos;  

- El equipo que genera los ensamblados y ejecuta el proceso de implementación tanto el equipo que ejecuta el ejemplo requieren Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]y Microsoft BizTalk Server.  

- El equipo que se usa para generar los ensamblados y ejecutar el proceso de implementación requiere Microsoft Visual Studio.  

- El equipo que ejecuta el ejemplo requiere los adaptadores de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y las herramientas de administración de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Estas son opciones para instalar durante la instalación de Microsoft BizTalk Server.  

- En los equipos que use para realizar las tareas administrativas, debe ejecutar una cuenta de usuario que sea miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar los parámetros de aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esta cuenta de usuario también debe ser miembro del grupo de administradores local para la implementación de la aplicación, la administración de las instancias de host y otras tareas que puedan ser necesarias.  

- En cualquier equipo que requiera [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] capacidad, complete el procedimiento de instalación única para la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] ejemplos en [ http://go.microsoft.com/fwlink/?LinkId=135510 ](http://go.microsoft.com/fwlink/?LinkId=135510).  

- En el equipo que ejecuta el ejemplo e importa un archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], asegúrese de que el host no es un host de confianza. De lo contrario, se producirá un error en la importación.  

- Debe descargar el código del tutorial y extraerlo en el equipo.  Este tutorial es una parte de todo el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] paquete de tutoriales del adaptador. Puede descargar el archivo **WCFAdapterWalkthroughs.exe** desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Developer Center en [ http://go.microsoft.com/fwlink/?LinkId=194140 ](http://go.microsoft.com/fwlink/?LinkId=194140).  

### <a name="configure-the-wcfcustommessageprocessing-application-and-artifacts"></a>Configuración de la aplicación WCFCustomMessageProcessing y los artefactos  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **aplicaciones**, seleccione **importación**y, a continuación, seleccione **archivo MSI**. Vaya a la **C:\WCFCustomMessageProcessing\WCFCustomMessageProcessing.msi** de archivo y, a continuación, haga clic en **abierto**. Esto crea los siguientes artefactos para esta aplicación:  

   - **FileSP** puerto de envío: la ubicación en el sistema de archivos local de **C:\WCFCustomMessageProcessing\Out** donde envía los datos de imagen JPEG [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como el resultado final del procesamiento del ejemplo. Puede ver el filtro de puerto de envío de **BTS. ReceivePortName = NetTcpRP** configurado en el **propiedades de FileSP** cuadro de diálogo en **filtros**. El filtro está asociado con el puerto de recepción NetTcp. Ubicación de salida de puerto de envío de los mensajes aceptados en NetTcpRP puerto de recepción se enviarán a la FileSP **C:\WCFCustomMessageProcessing\Out** después de la ubicación de recepción ejecuta el procesamiento de XPath en el mensaje.  

   - **NetTcpRP** puerto de recepción: el puerto que contiene lógicamente el **NetTcpRL** ubicación de recepción.  

   - **NetTcpRL** ubicación de recepción: se usa el valor predeterminado **PassThroughTransmit** datos entrante de imagen de canalización y el adaptador de WCF-NetTcp para ejecutar una instrucción XPath para extraer la imagen JPEG [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] mensaje.  

### <a name="alternative-steps-to-configure-the-wcfcustommessageprocessing-application"></a>Otros pasos para configurar la aplicación WCFCustomMessageProcessing  

- Como alternativa, estos son los pasos manuales para configurar la aplicación sin usar la **C:\WCFCustomMessageProcessing\bindings.xml** archivo. No es necesario que haga esto si el proceso de importación de archivo de enlace anterior funciona correctamente.  Sin embargo, su lectura le proporcionará información de lo que ocurre con el archivo MSI.  

- Crear un puerto de recepción unidireccional (**NetTcpRP**) y una ubicación de recepción (**NetTcpRL**).  

  1. Expanda el **WCFCustomMessageProcessing** aplicación, haga clic en **puertos de recepción**, seleccione **New**y seleccione **puerto de recepción unidireccional**. En el **propiedades de puerto de recepción** diálogo cuadro, escriba `NetTcpRP` para **nombre**y haga clic en **Aceptar**.  

  2. Haga clic en el **NetTcpRP** puerto de recepción, seleccione **New**y seleccione **ubicación de recepción**. En el **propiedades de ubicación de recepción** diálogo cuadro, escriba `NetTcRL` para **nombre**. En el **transporte** sección, haga clic en el **tipo** cuadro de lista desplegable, seleccione **WCF-NetTcp** desde la lista desplegable y, a continuación, haga clic en **configurar**.  

  3. En el **General** , escriba **TCP://localhost/nettcprl/Image** en el **dirección (URI)** campo.  

  4. En el **seguridad** pestaña, establezca el **modo de seguridad** a **ninguno.**  

  5. En el **mensaje** ficha, seleccione el **ruta** opción para la **cuerpo del mensaje entrante de BizTalk**y escriba `/*[local-name()="SendPicture" and namespace-uri()='http://tempuri.org/']/*[local-name()="stream"]` para la expresión de ruta de cuerpo. Seleccione **Base64** como el **codificación de nodo**. El **ruta de acceso** opción se establece en valor porque el cuerpo de la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] del mensaje que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe tiene el formato siguiente:  **\<SendPicture xmlns = "http://tempuri.org/"\> \<secuencia\>*real en base 64 codifica los datos de imagen binarios*\</transmitir\>\</SendPicture\>**  

  6. En el **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  

- Cree un puerto de envío de archivos unidireccional (FileSP) suscrito al puerto de recepción NetTcpRP.  

  1.  Haga clic en **puertos de envío**, seleccione **New**y seleccione **puerto de recepción unidireccional**. Seleccione **Puerto unidireccional estático**. Escriba `FileSP` para **nombre**.  

  2.  En el **transporte** sección, haga clic en el **tipo** cuadro de lista desplegable, seleccione **archivo** desde la lista desplegable y, a continuación, haga clic en **configurar**.  

  3.  En **carpeta de destino** escriba `C:\WCFCustomMessageProcessing\Out`y haga clic en **Aceptar**.  

  4.  Haga clic en **filtros**, seleccione `BTS.ReceivePortName == NetTcpRP`y, a continuación, haga clic en **Aceptar.**  

### <a name="configure-the-send-port-and-run-the-application"></a>Configuración del puerto de envío y ejecución de la aplicación  

1. Haga clic en el **WCFCustomMessageProcessing** aplicación y seleccione **iniciar**. Esto dará de alta la ubicación de recepción NetTcpRL e iniciará el puerto de envío FileSP.  

2. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el `Client.sln` de archivos desde el **c: wcfcustommessageprocessing\client** carpeta. En el Explorador de soluciones, haga clic en el **cliente** del proyecto y seleccione **compilar**.  

3. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], seleccione **depurar**y, a continuación, seleccione **iniciar sin depurar** para ejecutar la aplicación Client.exe. Aparecerá un símbolo del sistema que indica que la imagen se envió a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

4. Observe la salida del archivo {GUID} .jpg correcta en la carpeta de archivos de puerto de envío de **C:\WCFCustomMessageProcessing\Out**. Esto muestra que el procesamiento de la aplicación para extraer el archivo JPEG y escribirlo en un puerto de envío de archivos se completó correctamente.
