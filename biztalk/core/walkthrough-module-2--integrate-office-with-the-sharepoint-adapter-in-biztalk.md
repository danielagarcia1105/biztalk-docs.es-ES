---
title: 'Tutorial: Módulo 2: integrar Office con Windows SharePoint Services adaptador | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, InfoPath forms
- InfoPath forms, creating
- InfoPath forms, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, integrating Microsoft Office
- Windows SharePoint Services, document libraries
ms.assetid: 2f81a712-bb20-4c32-bbac-fb438deded38
caps.latest.revision: 48
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64e23cef8b362accba726c60945548a3345c9c45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22291460"
---
# <a name="walkthrough-module-2---integrating-office-with-the-windows-sharepoint-services-adapter"></a>Tutorial: Módulo 2: integrar Office con el adaptador de Windows SharePoint Services
En este tutorial es la continuación de [Tutorial: módulo 1 – enviar y recibir mensajes con el adaptador de Windows SharePoint Services](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md) y se muestra cómo integrar Microsoft Office con el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] basado en contenido aplicación de enrutamiento (CBR) que ha creado. Para obtener una introducción al adaptador de Windows SharePoint Services, vea [¿qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:  
  
-   Debe tener una implementación de un solo servidor con una instalación completa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Debe completar el siguiente tutorial: [Tutorial: módulo 1 – enviar y recibir mensajes con el adaptador de Windows SharePoint Services](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)  
  
 Para obtener información acerca de cómo utilizar el adaptador de Windows SharePoint Services en una implementación multiservidor, vea [configurar e implementar el adaptador de Windows SharePoint Services](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).  
  
## <a name="create-a-biztalk-project"></a>Crear un proyecto de BizTalk  
 En este procedimiento, creará un proyecto de BizTalk vacío y un esquema utilizando el Editor de BizTalk. Este procedimiento se requiere para crear el esquema del formulario de InfoPath que se utilizará posteriormente.  
  
#### <a name="create-a-strong-name-key-file"></a>Crear un archivo de clave de nombre seguro  
  
1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
2.  Tipo de `sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`y, a continuación, presione **ENTRAR**. Se escribirá el par de claves.  
  
3.  Cierre el símbolo del sistema.  
  
#### <a name="create-an-empty-biztalk-project"></a>Crear un proyecto de BizTalk vacío  
  
1.  Iniciar **Microsoft Visual Studio**.  
  
2.  Haga clic en **archivo**, **New**y, a continuación, haga clic en **proyecto**.  
  
3.  En **tipos de proyecto**, seleccione **proyectos de BizTalk**.  
  
4.  En **plantillas**, seleccione **proyecto vacío de servidor BizTalk**.  
  
5.  Tipo de `OrderProcess` en el **nombre** campo.  
  
6.  Escriba la ruta de acceso al directorio de trabajo en el **ubicación** campo. Por ejemplo, `C:\WSSAdapterWalkthrough\`.  
  
7.  Haga clic en **Aceptar**.  
  
#### <a name="associate-the-key-file-with-the-assembly"></a>Asociar el archivo de clave al ensamblado  
  
1.  En el Explorador de soluciones, haga clic en el `OrderProcess` del proyecto y, a continuación, haga clic en **propiedades** para iniciar el Diseñador de proyectos.  
  
2.  Haga clic en la pestaña **Firma** .  
  
3.  Seleccione la opción **Firmar el ensamblado** , haga clic en la lista desplegable para la opción **Seleccione un archivo de clave de nombre seguro** y, a continuación, haga clic en **Examinar**.  
  
4.  Type `C:\WSSAdapterWalkthrough\OrderProcess.snk`.  
  
5.  Haga clic en **Abrir**.  
  
#### <a name="create-an-xsd-schema-by-using-the-biztalk-editor"></a>Crear un esquema XSD utilizando el Editor de BizTalk  
  
1.  En el Explorador de soluciones, haga clic en el `OrderProcess` proyecto de equipo y haga clic en **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En **categorías**, haga clic en **archivos de esquema**.  
  
3.  En **plantillas**, haga clic en **esquema**.  
  
4.  Tipo de `OrderProcessSchema` en el **nombre** campo y, a continuación, haga clic en **agregar**.  
  
5.  En la ventana de propiedades para `OrderProcessSchema`, seleccione `Qualified` para el **Element FormDefault** propiedad.  
  
6.  En la ventana de propiedades para `OrderProcessSchema`, tipo `http://OrderProcess.PurchaseOrder` en el **Target Namespace** campo.  
  
7.  En el **el Editor de BizTalk**, haga clic en `Root`, haga clic en **cambiar el nombre de**y, a continuación, escriba `PurchaseOrder`.  
  
8.  Haga clic en el **PurchaseOrder** nodo, haga clic en **Insertar nodo de esquema**, a continuación, haga clic en **elemento de campo secundario**.  
  
9. Asígnele el nombre `PurchaseOrderID`.  
  
10. Cree otro elemento de campo secundario y asígnele el nombre `BillTo`.  
  
11. Cree otro elemento de campo secundario y asígnele el nombre `Amount`.  
  
12. En la ventana Propiedades, establezca la **tipo de datos** propiedad `Amount` a xs: unsignedInt.  
  
13. Cree otro elemento de campo secundario y asígnele el nombre `PurchaseOrderDate`.  
  
14. En la ventana Propiedades, establezca la **tipo de datos** propiedad `PurchaseOrderDate` a xs: DateTime.  
  
15. Haga clic en **archivo**y, a continuación, haga clic en **guardar todo**.  
  
16. Cierre [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
## <a name="create-an-infopath-form"></a>Crear un formulario de InfoPath  
 En este procedimiento, creará otra biblioteca de documentos y un formulario de InfoPath basado en el esquema creado en el último procedimiento. Este formulario de InfoPath se usará para enviar un documento a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  Este tutorial requiere tener instalado Microsoft Office InfoPath 2007  
  
#### <a name="create-a-new-document-library"></a>Crear una nueva biblioteca de documentos  
  
1.  Abra un explorador web y vaya a la dirección URL del sitio creado. Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.  
  
2.  En la barra de navegación superior, haga clic en **crear**.  
  
3.  En **las bibliotecas de documentos**, haga clic en **biblioteca de documentos**.  
  
4.  En el **nombre y una descripción** sección, escriba `InfoPathSolutions` en el **campo nombre**.  
  
5.  En el **navegación** sección, seleccione **Sí** para mostrar esta biblioteca de formularios en la barra Inicio rápido.  
  
6.  En el **plantilla de documento** sección, seleccione `None` para el **plantilla de documento**.  
  
7.  Haga clic en **Crear**. Tendrá lugar una redirección a la biblioteca vacía recién creada.  
  
8.  En el lado izquierdo, haga clic en **modificar configuración y columnas**.  
  
9. En **columnas**, haga clic en **agregar una nueva columna**.  
  
10. En **nombre y tipo**, tipo `Namespace` en el **nombre** campo.  
  
11. Haga clic en **Aceptar**.  
  
12. Cierre el sitio web de `WSSAdapterWalkthrough`.  
  
#### <a name="create-an-infopath-form-based-on-the-orderprocessschema-schema-file"></a>Crear un formulario de InfoPath basado en el archivo de esquema OrderProcessSchema  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office**y, a continuación, haga clic en **Microsoft Office InfoPath 2007**.  
  
2.  En el **rellenar un formulario** cuadro de diálogo, seleccione **diseñar un formulario.**  
  
3.  En el **diseñar un formulario** panel de tareas, seleccione **nuevo a partir de documento o esquema XML**.  
  
4.  En el **Data Source Wizard**, haga clic en **examinar** y seleccione el archivo de esquema creado en el último procedimiento. Por ejemplo, `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`.  
  
5.  Haga clic en **Siguiente**y, a continuación, en **Finalizar**.  
  
6.  En el **origen de datos** panel de tareas, haga clic en el **PurchaseOrder** nodo y, a continuación, haga clic en **sección con controles**. Al hacerlo, se creará el formulario en la plantilla.  
  
7.  Haga clic en **archivo**, haga clic en **guardar**y, a continuación, haga clic en **guardar**.  
  
8.  En el **Guardar como** cuadro de diálogo, escriba `PurchaseOrder.xsn` en el **nombre de archivo** campo y, a continuación, haga clic en **guardar**.  
  
9. Haga clic en **archivo**y, a continuación, haga clic en **publicar**.  
  
10. En el **Asistente para publicación de**, haga clic en **siguiente**.  
  
11. Seleccione **en un servidor Web**y, a continuación, haga clic en **siguiente**.  
  
12. Escriba la ruta de acceso y nombre de archivo para su `InfoPathSolutions` biblioteca de documentos y, a continuación, haga clic en **siguiente**. Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`.  
  
13. Haga clic en **finalizar**y, a continuación, haga clic en **cerrar**.  
  
14. Cierre Microsoft InfoPath.  
  
## <a name="modify-the-sharepoint-document-libraries"></a>Modificar las bibliotecas de documentos de SharePoint  
 En este procedimiento, se actualizará la propiedad de espacio de nombres para el archivo PurchaseOrder.xsn y se modificará la biblioteca de documentos de destino. Este espacio de nombres se utiliza como una variable al determinar suscriptores de documentos publicados para escenarios de enrutamiento por contenidos.  
  
#### <a name="update-the-namespace-for-purchaseorderxsn"></a>Actualizar el espacio de nombres para PurchaseOrder.xsn  
  
1.  Abra un explorador web y vaya a la dirección URL del sitio creado. Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.  
  
2.  En el lado izquierdo, bajo **documentos**, haga clic en `InfoPathSolutions`.  
  
3.  Mueva el puntero sobre `PurchaseOrder.xsn`, haga clic en él y, a continuación, haga clic en **editar propiedades**.  
  
4.  Tipo de `http://OrderProcess.PurchaseOrder` en el **Namespace** campo y, a continuación, haga clic en **guardar y cerrar**.  
  
#### <a name="modify-the-destination-document-library"></a>Modificar la biblioteca de documentos de destino  
  
1.  En la barra de navegación superior, haga clic en **documentos y listas**.  
  
2.  En **las bibliotecas de documentos**, haga clic en **destino**.  
  
3.  En el lado izquierdo, haga clic en **modificar configuración y columnas**.  
  
4.  En **columnas**, haga clic en **agregar nueva columna**.  
  
5.  En **nombre y tipo**, tipo `Partner Name` en el **nombre de la columna** campo.  
  
6.  Haga clic en **Aceptar**.  
  
7.  Cierre el sitio web de `WSSAdapterWalkthrough`.  
  
## <a name="modify-the-send-port-from-walkthrough-1"></a>Modificar el puerto de envío del Tutorial 1  
 En este procedimiento, modificará el puerto de envío del Tutorial 1. Este procedimiento se requiere para garantizar que el documento procesado en este tutorial se enrute correctamente al puerto de envío.  
  
#### <a name="modify-the-send-port"></a>Modificar el puerto de envío  
  
1.  Abra **administración de BizTalk Server.**  
  
2.  Expanda **Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y, a continuación, haga clic en el **puertos de envío** nodo.  
  
3.  Haga clic en `SendToDestination`y, a continuación, haga clic en **propiedades**.  
  
4.  En **transporte**, haga clic en **configurar**.  
  
5.  En el **Filename** , escriba `PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`.  
  
6.  En el **alias Namespace** , escriba `pons="http://OrderProcess.PurchaseOrder"`.  
  
7.  En el **biblioteca de documentos de plantillas de**, tipo `InfoPathSolutions`.  
  
8.  En el **plantillas Namespace columna**, tipo `Namespace`.  
  
9. Seleccione `Yes` para el **integración con Microsoft Office** propiedad.  
  
10. En **integración con Windows SharePoint Services**, tipo `Partner Name` en el **columna 01** campo.  
  
11. Tipo de `%XPATH=//pons:PurchaseOrder/pons:BillTo%` en el **valor de columna 01** , a continuación, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo para salir del **propiedades de puerto de envío** cuadro de diálogo.  
  
#### <a name="restart-the-send-port"></a>Reiniciar el puerto de envío  
  
1.  En el **consola de administración de BizTalk**, haga clic en el **puertos de envío** nodo.  
  
2.  Haga clic en `SendToDestination`y, a continuación, haga clic en **dar de baja**.  
  
3.  Haga clic en `SendToDestination`y, a continuación, haga clic en **iniciar**.  
  
4.  Cerrar la **consola de administración de BizTalk**.  
  
## <a name="send-a-message-through-the-system"></a>Enviar un mensaje a través del sistema  
 En este procedimiento, creará un formulario de InfoPath y lo cargará en el sitio web de Windows SharePoint Services. El adaptador de Windows SharePoint Services tomará el mensaje, lo archivará en la biblioteca de documentos de archivo y, a continuación, lo enviará a la biblioteca de documentos de destino. En este procedimiento se demuestra cómo un documento se transfiere de un sitio web de Sharepoint, a través de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a un sitio web de Sharepoint Services mediante el adaptador de Windows Sharepoint Services.  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a>Crear un formulario de InfoPath para su envío a través del sistema  
  
1.  Abra un explorador web y vaya a la dirección URL del sitio creado. Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.  
  
2.  En el lado izquierdo, bajo **documentos**, haga clic en `InfoPathSolutions`.  
  
3.  Haga clic en el `PurchaseOrder` archivo para mostrar el **descarga de archivos** cuadro de diálogo y, a continuación, haga clic en **abiertos**. InfoPath cargará el formulario.  
  
4.  En el **Purchase Order ID** , escriba `1002`.  
  
5.  En el **facturar a** , escriba `John Doe`.  
  
6.  En el **cantidad** , escriba `750`.  
  
7.  En el **fecha del pedido de compra** , escriba `1/2/2005`.  
  
8.  Haga clic en **Guardar**.  
  
9. En el **Guardar como** cuadro de diálogo, escriba `http://<server_name>/sites/WSSAdapterWalkthrough/Source`en el **nombre de archivo** campo y, a continuación, presione ENTRAR.  
  
10. Tipo de `PurchaseOrder2.xml` en el **nombre de archivo** campo y, a continuación, haga clic en **guardar**.  
  
11. Cierre Microsoft Office InfoPath.  
  
12. En el explorador Web, en la barra de navegación superior, haga clic en **documentos y listas**.  
  
13. En **las bibliotecas de documentos**, haga clic en **destino**.  
  
14. En la biblioteca de documentos de destino, verá ahora el mensaje incluido en la lista. También encontrará una copia archivada en la biblioteca de documentos de archivo.  
  
15. En la biblioteca de documentos de destino, haga clic en `PurchaseOrder1.xml`. Tenga en cuenta que este archivo XML se abre en Microsoft Internet Explorer.  
  
16. En la biblioteca de documentos de destino, haga clic en `PurchaseOrder2.xml`. Tenga en cuenta que este archivo XML se abre en Microsoft Office InfoPath.  
  
> [!NOTE]
>  En la biblioteca de documentos de destino, la columna de nombre de archivo debe contener el valor del campo PurchaseOrderID y la columna Nombre de socio comercial debe contener el valor del campo BillTo.  
  
## <a name="summary"></a>Resumen  
 En este tutorial, ha visto cómo agregar una mayor integración con Microsoft InfoPath utilizando el adaptador de Windows SharePoint Services y el enrutamiento por contenidos (CBR).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora que ha completado este tutorial, realice la [Tutorial: módulo 3: obtener acceso a propiedades de SharePoint desde una orquestación](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md) tutorial que se expande en el trabajo que ha realizado en este tutorial, se integra un orquestación al proyecto y se muestra cómo tener acceso a propiedades de SharePoint desde dentro de él.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Tutoriales del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-walkthroughs.md)