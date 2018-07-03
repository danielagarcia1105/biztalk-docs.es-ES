---
title: 'Paso 3: Crear un archivo de definición de aplicación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 843fafdb-571e-4da4-ad04-7dc7f23e03ac
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7a5e2919a4cfed649342fda82435211b059206d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988221"
---
# <a name="step-3-create-an-application-definition-file"></a>Paso 3: Crear un archivo de definición de aplicación
![Paso 3 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **Tiempo en completarse:** 15 minutos  
  
 La característica de catálogo de datos empresariales en Microsoft Office SharePoint Server expone e incorpora datos desde aplicaciones de línea de negocio (LOB) en los portales. Para incorporar estos datos en el sitio del portal, debe crear un archivo de definición de aplicación que pueden usar Microsoft Office SharePoint Server.  
  
 En este paso, usará la herramienta Editor de definición de catálogo de datos empresariales, disponible con el SDK de Microsoft Office SharePoint Server 2007, para crear un archivo de definición de aplicación para el catálogo de datos profesionales. Este archivo de definición describe el método EchoGreetings del adaptador de Echo y se usará en pasos posteriores para habilitar SharePoint para establecer comunicación con el adaptador.  
  
 El propósito de la aplicación de Microsoft Office SharePoint Server que se va a crear es para que pueda invocar el método EchoGreetings del adaptador de Echo y devolver la respuesta mediante un elemento Web de SharePoint.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado [paso 2: implementar el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md). También debe tener acceso a Business Data Catalog definición Editor, que se instala como parte del SDK de Microsoft Office SharePoint Server 2007. Puede descargar el SDK desde [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130).  
  
## <a name="creating-an-application-definition-file"></a>Creación de un archivo de definición de aplicación  
 Este tema proporciona instrucciones paso a paso para crear un archivo de definición de aplicación para conectar el catálogo de datos profesionales de SharePoint con el adaptador de WCF hospedado en IIS.  
  
#### <a name="to-connect-to-the-wcf-adapter-service-and-create-entities"></a>Para conectarse al servicio de adaptador WCF y crear entidades  
  
1.  Desde el **menú Inicio**, apunte a **todos los programas**y, a continuación, haga clic en **Editor de definición de catálogo de datos de Microsoft Business**.  
  
2.  En la barra de herramientas, haga clic en **Agregar sistema LOB**.  
  
3.  En la ventana Agregar sistema LOB, haga clic en **conectar al servicio Web**.  
  
4.  En el **URL** cuadro, escriba la dirección URL del servicio WCF. La dirección URL debe tener el formato siguiente: `https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`  
  
5.  Haga clic en **Conectar**.  
  
6.  Para ver las operaciones disponibles, haga clic en el **Agregar método Web** ficha. Debería ver el método EchoGreetings. Arrastre el método a la superficie de diseño.  
  
7.  Haga clic en **Aceptar**.  
  
8.  En el **escriba el nombre para el sistema LOB** cuadro de diálogo, escriba un nombre en el **nombre del sistema de LOB** cuadro. En este ejemplo, escriba **EchoWSLOB**y, a continuación, haga clic en **Aceptar**.  
  
9. Expanda el **EchoWSLob** nodo y, a continuación, expanda el **entidades** nodo. Seleccione **Entity0** y en el panel Propiedades, escriba **EchoGreetings** como el valor de la **nombre** propiedad.  
  
     ![Nombre de la entidad](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")  
  
## <a name="specify-user-name-and-password-headers-for-the-method"></a>Especifique el nombre de usuario y los encabezados de la contraseña para el método  
 Al llamar a un adaptador de WCF, es posible que deba proporcionar credenciales de usuario que se pasa al sistema de LOB. En [paso 1: usar el Asistente para desarrollo de servicio de adaptador para crear el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md), configura el adaptador de Echo para requerir que se proporciona información de nombre y la contraseña de usuario en los campos MyUserHeader y MyPassHeader. Ahora debe usar los mismos nombres de campo para este archivo de definición de aplicación.  
  
#### <a name="to-specify-user-name-and-password-headers"></a>Para especificar encabezados de nombre y la contraseña de usuario  
  
1.  En el panel de objetos de metadatos, expanda el **EchoGreetings** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Haga clic en el **EchoGreetings** nodo y, en el panel Propiedades, haga clic en el botón de puntos suspensivos **(...)**  situado en la **propiedades** campo.  
  
3.  En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el **nombre** campo del panel de propiedades, tipo **HttpHeaderUserName**.  
  
     ![Especificar campos de encabezado de nombre de usuario](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")  
  
4.  En el **PropertyValue**, escriba **MyUserHeader**.  
  
5.  Haga clic en **agregar**y en el tipo de panel propiedad **HttpHeaderPassword** para el campo nombre, a continuación, escriba **MyPassHeader** para el **PropertyValue**campo.  
  
6.  Haga clic en **Aceptar**.  
  
## <a name="set-up-single-sign-on-for-connecting-to-the-echo-adapter"></a>Establecer seguridad Single Sign-On para conectar con el adaptador de Echo  
 SharePoint utiliza información desde el inicio de sesión único para rellenar el MyUserHeader y MyPassHeader con los valores de autenticación. Para vincular este archivo de definición de aplicación para el inicio de sesión único, debe proporcionar un SecondarySsoApplicationId.  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a>Para establecer la propiedad SecondarySsoApplicationId  
  
1. En el panel de objetos de metadatos, expanda el **EchoWSLOB** nodo y, a continuación, expanda el **instancias** nodo.  
  
2. Haga clic en **EchoWSLOB_Instance**y en el panel Propiedades, haga clic en el botón de puntos suspensivos <strong>(...)</strong> situado en la **propiedades** campo.  
  
3. En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **SecondarySsoApplicationId** en el **nombre** campo.  
  
4. En el **PropertyValue** , escriba **EchoSSO**.  
  
    ![Establecer SecondarySsoApplicationId](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")  
  
5. Haga clic en **Aceptar**.  
  
## <a name="create-input-filters-and-default-values"></a>Crear filtros de entrada y los valores predeterminados  
 El archivo de definición de aplicación debe ser capaz de aceptar entradas de usuario que se pueden pasar a un servicio Web. Para ello, debe realizar el siguiente conjunto de tareas:  
  
#### <a name="to-create-a-filter-and-map-it-to-the-greeting-parameter"></a>Para crear un filtro y asignarla al parámetro saludo  
  
1.  En el panel de objetos de metadatos, expanda el **EchoWSLOB** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el **EchoGreetings** método, haga clic en **filtros**y, a continuación, haga clic en **Agregar filtro**.  
  
3.  En el panel Propiedades, escriba **saludo** en el **nombre** campo.  
  
     ![Establece el nombre del filtro](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")  
  
4.  En el panel de objetos de metadatos, expanda el **EchoWSLOB** nodo y, a continuación, expanda el **métodos** nodo  
  
5.  Expanda el **EchoGreetings** método y, a continuación, expanda el **parámetros** nodo.  
  
6.  Expanda el **saludo** nodo y, a continuación, expanda el segundo **saludo** nodo.  
  
7.  Haga clic en el **greetingText** nodo y en el panel Propiedades, seleccione **saludo** desde el **FilterDescriptor** lista.  
  
#### <a name="to-create-a-finder-method-instance-for-the-echogreetings-method"></a>Para crear una instancia de método de buscador para el método EchoGreetings  
  
1.  En el panel de objetos de metadatos, expanda el **EchoWSLOB** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el **EchoGreetings** método, haga clic en **instancias**y, a continuación, haga clic en **Agregar instancia del método** para abrir la ventana Crear instancia de método.  
  
3.  En la ventana Crear instancia de método, haga clic en **buscador** para **tipo de método de instancia**y, a continuación, seleccione **devolver** para **TypeDescriptor de devolución**.  
  
     ![Crear la instancia de método](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")  
  
4.  Haga clic en **Aceptar**.  
  
5.  En el panel Propiedades, escriba **EchoGreetings_Instance** en el **nombre** campo.  
  
#### <a name="to-set-default-parameters"></a>Para establecer los parámetros predeterminados  
  
1.  En el panel de objetos de metadatos, expanda el **EchoWSLOB** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el **EchoGreetings** método y, a continuación, expanda el **instancias** nodo.  
  
3.  Seleccione el **EchoGreetings_Instance** método de instancia y, en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **DefaultValues** campo.  
  
4.  En la ventana de edición, expanda el **saludo** nodo y, a continuación, expanda el segundo **saludo** nodo. Expanda el **nombre** nodo hasta que se muestre por completo la estructura de árbol.  
  
5.  En la ventana de edición, establezca los valores de campo de la siguiente manera:  
  
    |Establezca|A este|  
    |--------------|-------------|  
    |**id**|Un valor GUID, por ejemplo 27829ed4-583a - 40c 4-ad87-fb8cdd9dc98d.|  
    |**sentDateTime**|La fecha y hora actuales, por ejemplo 05/15/08 9:12 A.M.|  
    |**firstName**|Primero|  
    |**middleName**|Middle|  
    |**Apellidos**|Último|  
  
     ![Parámetros predeterminados](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")  
  
6.  Haga clic en **Cerrar**.  
  
### <a name="to-export-the-application-definition-file"></a>Para exportar el archivo de definición de aplicación  
  
1.  En el panel de objetos de metadatos, haga clic en el **EchoWSLOB** nodo y, a continuación, haga clic en **exportar**.  
  
2.  Guarde el archivo como EchoWS.xml.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 Ha usado la herramienta Editor de definición del catálogo de datos de negocio para crear un archivo de definición de aplicación que puede importarse en Microsoft Office SharePoint Server 2007 para habilitar la conectividad con el adaptador que se hospeda en IIS.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora debe crear una aplicación de SharePoint basada en el archivo de definición de la aplicación creado en este paso. Consulte [paso 4: crear una aplicación de Sharepoint para tener acceso al adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md) para obtener instrucciones.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 3: Hospedar el adaptador de Echo en IIS](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)