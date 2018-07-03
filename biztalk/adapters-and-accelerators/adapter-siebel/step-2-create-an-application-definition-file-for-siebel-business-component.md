---
title: 'Paso 2: Crear un archivo de definición de aplicación para operaciones de componentes empresariales de Siebel | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75d34c48-0f2a-42e4-a60b-e04bcf2404e1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c017d5e71cdd2a4281849647727364520ad77784
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967621"
---
# <a name="step-2-create-an-application-definition-file-for-siebel-business-component-operations"></a>Paso 2: Crear un archivo de definición de aplicación para operaciones de componentes empresariales de Siebel
![Paso 2 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **Tiempo en completarse:** 15 minutos  
  
 **Objetivo:** catálogo de datos empresariales expone e incorpora datos desde aplicaciones de línea de negocio (LOB) en los portales. Para incorporar estos datos en el sitio del portal, debe crear un archivo de definición de aplicación que pueden usar Microsoft Office SharePoint Server.  
  
 La herramienta Editor de definición del catálogo de datos de negocio le permite crear un archivo de definición de aplicación para el catálogo de datos profesionales. Esta herramienta genera automáticamente el código XML para el archivo de definición. Por lo tanto, no es necesario crear manualmente el archivo en un documento XML editor.  
  
 El propósito de la aplicación de Microsoft Office SharePoint Server que se va a crear es realizar una operación de consulta en el componente empresarial de cuenta para recuperar una lista de registros. Para lograr esto, debe completar un conjunto de tareas en el Editor de definición de catálogo de datos de Business. Este tema proporciona instrucciones sobre cómo realizar estas tareas.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener el Editor de definición del catálogo de datos profesionales instalado como parte del SDK de Microsoft Office SharePoint Server 2007. Puede descargar el SDK desde [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130).  
  
-   Debe ha publicado el servicio WCF, como se describe en [paso 1: publicar las operaciones de componentes empresariales de Siebel como un servicio WCF](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).  
  
## <a name="creating-an-application-definition-file"></a>Creación de un archivo de definición de aplicación  
 Esta sección proporciona instrucciones paso a paso para crear un archivo de definición de aplicación para el servicio WCF.  
  
### <a name="connect-to-the-wcf-service-and-create-entities"></a>Conectar con el servicio WCF y crear entidades  
 Debe conectarse al servicio WCF para extraer el lenguaje de descripción de servicios Web (WSDL) para el servicio. Desde el archivo WSDL, el Editor de definición del catálogo de datos profesionales extrae los métodos. Estos métodos se pueden usar para crear entidades. En este ejemplo, debe crear una entidad para la operación de consulta en el componente de negocio de la cuenta.  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>Para conectarse al servicio WCF y crear entidades  
  
1.  Inicie el Editor de definición del catálogo de datos profesionales. En el **iniciar** menú, haga clic en **Editor de definición de catálogo de datos de Microsoft Business**.  
  
2.  En la herramienta, haga clic en **Agregar sistema LOB**.  
  
3.  En la ventana Agregar sistema LOB, haga clic en **conectar al servicio Web**.  
  
4.  En el cuadro de dirección URL, escriba la dirección URL del servicio WCF. La dirección URL debe tener el formato siguiente:  
  
    ```  
    https://<computer_name>/Siebel_Account/BusinessObjects_Account_Account_Operation.svc?wsdl  
    ```  
  
     donde, BusinessObjects_Account_Account_Operation.svc es el archivo de servicio creado para el contrato de Siebel.  
  
     La dirección URL que debe escribir está disponible cuando se prueba si se publica correctamente, como se describe en el servicio WCF [paso 1: publicar las operaciones de componentes empresariales de Siebel como un servicio WCF](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).  
  
5.  Haga clic en **Conectar**.  
  
6.  Haga clic en el **Agregar método Web** pestaña para ver las operaciones que seleccionó en el Asistente para desarrollo de servicio de adaptador de WCF. Verá el **consulta** método.  
  
     ![Agregar métodos web a la aplicación BDC](../../adapters-and-accelerators/adapter-siebel/media/f9505cd3-67e3-4f99-b189-d010322a3137.gif "f9505cd3-67e3-4f99-b189-d010322a3137")  
  
7.  Arrastre el **consulta** método a la superficie de diseño y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **escriba el nombre para el sistema LOB** cuadro de diálogo, escriba un nombre en el **nombre del sistema de LOB** cuadro. En este ejemplo, escriba `Siebel_Account`y, a continuación, haga clic en **Aceptar**. Una entidad, **Entity0**, se crea en el Editor de definición de catálogo de datos de Business.  
  
    > [!IMPORTANT]
    >  La herramienta Editor de definición de catálogo de datos profesionales no controla los tipos de datos enumerados. Por lo tanto, la herramienta Editor de definición de catálogo de datos profesionales importa los campos hasta que encuentra un tipo de datos enumerado y omite los campos restantes. La herramienta Editor de definición del catálogo de datos de negocio también produce un error. Puede omitir este error y continuar, haga clic en Aceptar. Puede agregar manualmente los campos obligatorios en el archivo de definición de aplicación en una etapa posterior.  
  
9. Cambie los nombres de entidad para usar nombres más descriptivos. En este ejemplo, cambiar **Entity0** a **cuenta**.  
  
    1.  Expanda el **Siebel_Account** nodo y, a continuación, expanda el **entidades** nodo.  
  
    2.  Seleccione el **Entity0** nodo.  
  
    3.  En el panel Propiedades, escriba **cuenta** en el **nombre** campo.  
  
         ![Cambiar el nombre de la entidad](../../adapters-and-accelerators/adapter-siebel/media/44eda1de-b348-4421-9c51-0355b51f4a90.gif "44eda1de-b348-4421-9c51-0355b51f4a90")  
  
### <a name="specify-user-name-and-password-headers-for-methods"></a>Especifique el nombre de usuario y contraseña encabezados para métodos  
 Al crear un servicio WCF para las operaciones del componente de negocios seleccionada en el sistema de Siebel, especifica los encabezados de nombre y la contraseña del usuario como parte de la configuración de comportamiento de punto de conexión ([paso 1: publicar las operaciones de componentes empresariales de Siebel como un servicio WCF](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)). Debe especificar los mismos valores para las propiedades del método.  
  
##### <a name="to-specify-user-name-and-password-headers-for-the-query-method"></a>Para especificar los encabezados de nombre y la contraseña de usuario para el método de consulta  
  
1.  En el panel de objetos de metadatos, expanda el **cuenta** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Haga clic en el **consulta** nodo y en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** campo.  
  
3.  En el cuadro de diálogo Editor de la colección PropertyView, haga clic en **agregar**y en el panel Propiedades, escriba `HttpHeaderUserName` para el **nombre** campo. De forma similar, escriba `MyUserHeader` para el **PropertyValue** campo. Seleccione **System.String** para el **tipo** campo.  
  
     ![Agregar una propiedad](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")  
  
4.  En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel Propiedades, escriba `HttpHeaderPassword` para el **nombre** campo. De forma similar, escriba `MyPassHeader` para el **PropertyValue** campo. Seleccione **System.String** para el **tipo** campo.  
  
5.  Haga clic en **Aceptar**.  
  
### <a name="set-up-single-sign-on-for-connecting-to-a-siebel-system"></a>Establecer seguridad Single Sign-On para conectarse a un sistema de Siebel  
 Cuando haya terminado de realizar todos los procedimientos de este tema, habrá creado una definición de aplicación XML que se puede importar a una aplicación de SharePoint. Desde la aplicación, invocará las operaciones de componentes empresariales de Siebel (expuestas como métodos Web) para recuperar los datos pertinentes en el sistema Siebel. Para habilitar esta opción, debe crear una asignación entre un usuario en el sistema Siebel y el usuario en la aplicación de SharePoint. Cree esta asignación en el sitio Web de Administración Central de SharePoint después de haber importado la definición de aplicación XML.  
  
 Sin embargo, para crear la asignación, debe establecer una propiedad **SecondarySsoApplicationId** en el Editor de definición de catálogo de datos de Business.  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a>Para establecer la propiedad SecondarySsoApplicationId  
  
1.  En el panel de objetos de metadatos, expanda el **Siebel_Account** nodo y, a continuación, expanda el **instancias** nodo.  
  
2.  Haga clic en **Siebel_Account_Instance** y en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** campo.  
  
3.  En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel Propiedades, escriba **SecondarySsoApplicationId** para el **nombre** campo. De forma similar, escriba **SiebelSSO** para el **PropertyValue** campo. Seleccione **System.String** para el **tipo** campo.  
  
     ![Agregue la propiedad SSO](../../adapters-and-accelerators/adapter-siebel/media/59ce70eb-498f-406b-965d-c273c2d6ed14.gif "59ce70eb-498f-406b-965d-c273c2d6ed14")  
  
4.  Haga clic en **Aceptar**.  
  
### <a name="requirement-perform-a-query-operation-on-the-account-business-component"></a>Requisito: Realizar una operación de consulta en el componente empresarial de cuenta  
 El primer requisito de este ejemplo es crear una definición de aplicación que se puede usar para realizar una operación de consulta en el componente de negocio de la cuenta. Para lograr este requisito, debe realizar el siguiente conjunto de tareas:  
  
-   En el método de consulta, crear un filtro y asignarla al parámetro en el que se realiza la operación de consulta. Para el componente de negocio de cuenta, realizará una consulta mediante el **SearchExpr** parámetro. Por lo tanto, se asignará el filtro para el **SearchExpr** parámetro.  
  
-   Cree una instancia de método de buscador para el método de consulta. Un método Finder recupera una lista de registros basada en un filtro.  
  
##### <a name="to-create-a-filter-and-map-it-to-the-searchexpr-parameter"></a>Para crear un filtro y asignarla al parámetro SearchExpr  
  
1.  Crear un filtro para el método de consulta.  
  
    1.  En el panel de objetos de metadatos, expanda el **cuenta** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Expanda el método de consulta, haga clic en **filtros**y, a continuación, haga clic en **Agregar filtro**.  
  
         ![Agregar filtro a un método](../../adapters-and-accelerators/adapter-siebel/media/9cf7ccfd-6da0-44b7-b522-df327a74e7a2.gif "9cf7ccfd-6da0-44b7-b522-df327a74e7a2")  
  
    3.  En el panel Propiedades, escriba `SearchExpression` para el **nombre** campo.  
  
    4.  Para el **FilterType** propiedad, seleccione **es igual a**.  
  
         ![Especifique un nombre de filtro y el tipo](../../adapters-and-accelerators/adapter-siebel/media/9faa18e1-4d27-4ee4-960a-458f978812a7.gif "9faa18e1-4d27-4ee4-960a-458f978812a7")  
  
2.  Asignar el filtro para el **SearchExpr** parámetro en el método de consulta.  
  
    1.  En el panel de objetos de metadatos, expanda el **cuenta** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Expanda el método de consulta y, a continuación, expanda el **parámetros** nodo.  
  
    3.  Expanda el **AccountQueryInputRecord** nodo y, a continuación, expanda el segundo **AccountQueryInputRecord** nodo.  
  
    4.  Haga clic en el **SearchExpr** nodo y en el panel Propiedades, seleccione **SearchExpression** desde el **FilterDescriptor**lista.  
  
         ![Asignar un parámetro a un filtro](../../adapters-and-accelerators/adapter-siebel/media/199c8ba7-d0e8-4fb4-9d73-9cf548512498.gif "199c8ba7-d0e8-4fb4-9d73-9cf548512498")  
  
        > [!IMPORTANT]
        >  El **AccountQueryInputRecord** también contiene un **QueryFields** nodo, que a su vez contiene un **elemento** nodo. Debe eliminar el **elemento** nodo, en caso contrario, la operación de consulta en el componente empresarial cuenta podría no proporcionar los resultados deseados. Para eliminar el **elemento** nodo, haga clic en el nodo y, a continuación, seleccione **eliminar**.  
  
##### <a name="to-create-a-finder-method-instance-for-query-method"></a>Para crear una instancia de método de buscador para el método de consulta  
  
1.  En el panel de objetos de metadatos, expanda el **cuenta** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el **consulta** nodo, haga clic en **instancias**y, a continuación, haga clic en **Agregar instancia del método** para abrir la ventana Crear instancia de método.  
  
     ![Agregar una instancia de método de buscador](../../adapters-and-accelerators/adapter-siebel/media/c90e7784-4fb7-4eb5-baf5-efbefba4bb1f.gif "c90e7784-4fb7-4eb5-baf5-efbefba4bb1f")  
  
3.  En la ventana Crear instancia de método, haga clic en **buscador** para el **tipo de método de instancia**.  
  
4.  Haga clic en **devolver** desde **TypeDescriptor de devolución** sección.  
  
     ![Agregar una instancia de método de buscador](../../adapters-and-accelerators/adapter-siebel/media/e8343988-d7c1-4b04-85b0-ca7d07097490.gif "e8343988-d7c1-4b04-85b0-ca7d07097490")  
  
5.  Haga clic en **Aceptar**.  
  
6.  En el panel Propiedades, escriba `QueryAccount` para el **nombre** campo.  
  
     ![Especifique un nombre para la instancia de método](../../adapters-and-accelerators/adapter-siebel/media/401223f3-806f-4010-8646-d5ac0c0e9f67.gif "401223f3-806f-4010-8646-d5ac0c0e9f67")  
  
### <a name="remove-the-parameters-of-systemnullable-type"></a>Quite los parámetros de tipo System.Nullable  
 Los parámetros devueltos de función de consulta pueden contener parámetros que son del tipo System.Nullable. Debido a la presencia de estos parámetros en la definición de aplicación, podría obtener un error mientras presenta datos de Siebel en un portal de SharePoint. Por lo tanto, debe quitar los parámetros de tipo System.Nullable desde la definición de aplicación.  
  
 Además, para cada parámetro de tipo System.Nullable, el Editor de definición del catálogo de datos profesionales crea otro parámetro de tipo System.Boolean y anexa "Specified" al nombre del parámetro. Por ejemplo, el parámetro AccountRole es de tipo System.Nullable. Por lo tanto, el Editor de definición del catálogo de datos profesionales agrega un parámetro AccountRoleSpecified a la lista de parámetros. Debe quitar también estos parámetros.  
  
> [!NOTE]
>  Puede ver que el parámetro de tipo, seleccione el parámetro en el Editor de definición de catálogo de datos de Business y examinando el valor de la **TypeName** propiedad en el panel Propiedades.  
  
> [!NOTE]
>  Puede omitir este paso si la aplicación no contiene ningún parámetro de tipo System.Nullable.  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type-for-the-query-method"></a>Para quitar los parámetros de tipo System.Nullable del método de consulta  
  
1.  En el panel de objetos de metadatos, expanda el **cuenta** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el **consulta** nodo y, a continuación, expanda el **parámetros** nodo.  
  
3.  Expanda el **devolver** nodo y, a continuación, expanda el segundo **devolver** nodo.  
  
4.  Haga clic en el parámetro que desea eliminar y, a continuación, seleccione **eliminar**.  
  
5.  En el cuadro de diálogo, haga clic en **Aceptar**.  
  
### <a name="export-the-application-definition-to-a-file"></a>Exportar la definición de aplicación a un archivo  
 Ahora ha creado una definición de aplicación que contiene los metadatos de instancia de sistema de Siebel. Esta definición se debe exportar a un archivo XML, que puede importarse en Microsoft Office SharePoint Server.  
  
##### <a name="to-export-the-application-definition-to-a-file"></a>Para exportar la definición de aplicación a un archivo  
  
1.  Haga clic en el **Siebel_Account** nodo en el panel de objetos de metadatos y, a continuación, haga clic en **exportar**.  
  
2.  Guarde el archivo como Siebel_Account.xml.  
  
### <a name="modify-the-application-definition-file-to-include-specific-parameters"></a>Modifique el archivo de definición de aplicación para incluir parámetros específicos  
 Como se mencionó anteriormente en este tema, la herramienta Editor de definición de catálogo de datos profesionales no controla los tipos de datos enumerados. La herramienta Editor de definición de catálogo de datos profesionales importa los campos hasta que encuentra un tipo de datos enumerado y omite los campos restantes. Por lo tanto, se pueden omitir algunos de los campos que desea incluir en la aplicación. Puede editar manualmente el archivo de definición de aplicación para incluir esos campos.  
  
> [!NOTE]
>  Debe asegurarse de que están presentes en el archivo .cs generado por el Asistente de desarrollo del servicio de adaptador de WCF en los parámetros que se va a agregar [paso 1: publicar las operaciones de componentes empresariales de Siebel como un servicio WCF](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).  
  
 En este archivo de definición de aplicación, se agregará o quitará los parámetros de retorno para la **QueryAccount** método.  
  
##### <a name="to-modify-the-application-definition-file"></a>Para modificar el archivo de definición de aplicación  
  
1. Abra el archivo de definición de aplicación, Siebel_Account.xml, mediante el uso de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o cualquier otro editor.  
  
2. Modifique el archivo de definición de aplicación para reemplazar los parámetros para el **QueryAccount** método.  
  
   1.  En el archivo de definición de aplicación, busque lo siguiente:  
  
       ```  
       <TypeDescriptor TypeName="BDC.AccountQueryRecord,Siebel_Account" Name="Item">  
       ```  
  
   2.  Dentro de la `<TypeDescriptors>` etiquetar, sustituya la `<TypeDescriptor>` elementos con los siguientes:  
  
       ```  
  
       <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Id" />  
       <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Country" />  
       <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Name" />  
       <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Location" />  
       ```  
  
   3.  Guarde el archivo y ciérrelo.  
  
   > [!TIP]
   >  Puede importar el archivo de definición de la aplicación actualizada en la herramienta Editor de definición del catálogo de datos de negocio para ver los campos recién agregados. Sin embargo, antes de importar tendrá que quitar la aplicación existente de "Siebel_Account" de la herramienta Editor de definición de catálogo de datos profesionales.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora debe crear una aplicación de SharePoint para recuperar datos de un sistema Siebel. Consulte [paso 3: crear una aplicación de SharePoint para recuperar datos de Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) para obtener instrucciones.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Presentación de datos de un sistema de Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)