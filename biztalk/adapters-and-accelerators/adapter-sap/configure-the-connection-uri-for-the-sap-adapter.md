---
title: Configurar el URI de conexión para el adaptador de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, specifying at run time
- connection URI, specifying at design time
ms.assetid: 8df8e4a7-13f7-48c0-8af2-451253ced7e7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88e96df27b0a8a26b20581e3ff757181ac8195cb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983053"
---
# <a name="configure-the-connection-uri-for-the-sap-adapter"></a>Configurar el URI de conexión para el adaptador de SAP
Una conexión de URI es una cadena de conexión para conectarse a un sistema SAP. Contiene varios parámetros necesarios para establecer conexión con un sistema SAP. En tiempo de diseño, debe especificar el URI para conectarse al sistema SAP para generar los metadatos. Debe especificar el URI para conectarse al sistema SAP para realizar operaciones en tiempo de ejecución.  

## <a name="enter-the-connection-uri-at-design-time"></a>Escriba el URI de conexión en tiempo de diseño  
 Para el tiempo de diseño, puede especificar el URI de conexión mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a>Especifique la conexión URI utilizando el complemento Consume Adapter Service  

1. Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

2. En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  


   |    Use    |             Para             |
   |----------------|------------------------------------|
   | **Categorías** | Haga clic en **Consume Adapter Service**. |
   | **Templates** (Plantillas [C++])  | Haga clic en **Consume Adapter Service**. |


3. Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.  

4. En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **sapBinding**y haga clic en **configurar** .  

5. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha. Desde el **tipo de credencial de cliente** cuadros de lista desplegable, seleccione **Username** y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.  

6. Haga clic en el **propiedades de URI** pestaña y especificar valores para parámetros diferentes. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  

7. Haga clic en el **propiedades de enlace** pestaña y especificar los valores de enlace, si existe, que deben especificarse antes de generar el esquema. Por ejemplo, debe especificar un valor para el **GenerateFlatFileCompatibleIDoc** propiedad antes de generar el esquema para recibir IDOC desde un sistema SAP. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  

8. Haga clic en **Aceptar**.  

### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a>Especifique la conexión URI utilizando el Asistente para agregar metadatos de adaptador  

1. Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

2. En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  


   |    Use    |           Para            |
   |----------------|---------------------------------|
   | **Categorías** |     Haga clic en **agregar adaptador**.      |
   | **Templates** (Plantillas [C++])  | Haga clic en **agregar metadatos de adaptador**. |


3. Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

4. En el Asistente para agregar adaptador, seleccione **SAP de WCF**. Seleccione el equipo donde está instalado BizTalk Server y el nombre de la base de datos de BizTalk.  

   > [!IMPORTANT]
   >  Si ya tiene un puerto de SAP de WCF configurado en BizTalk, seleccione el puerto desde el **puerto** lista.  

5. Haga clic en **Siguiente**.  

6. En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **sapBinding**y haga clic en **configurar** .  

7. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha. Desde el **tipo de credencial de cliente** cuadros de lista desplegable, seleccione **Username** y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.  

8. Haga clic en el **propiedades de URI** pestaña y especificar valores para parámetros diferentes. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  

9. Haga clic en el **propiedades de enlace** pestaña y especificar los valores de enlace, si existe, que deben especificarse antes de generar el esquema. Por ejemplo, debe especificar un valor para el **GenerateFlatFileCompatibleIDoc** propiedad antes de generar el esquema para recibir IDOC desde un sistema SAP. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  

    > [!NOTE]
    >  Si ha seleccionado un puerto de envío WCF-SAP existente, no necesita especificar las propiedades de enlace. Se seleccionan las propiedades de enlace de la configuración de puerto de envío. Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si existe. En este caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos. Sin embargo, en tiempo de ejecución los valores especificados para las propiedades de enlace en la configuración del puerto de envío será aplicable.  

10. Haga clic en **Aceptar**.  

## <a name="enter-the-connection-uri-at-run-time"></a>Escriba el URI de conexión en tiempo de ejecución  
 Para el tiempo de ejecución, puede especificar el identificador URI como parte de la configuración del puerto WCF-Custom o WCF-SAP en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a>Escriba el URI de conexión para el puerto de WCF-Custom  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

3. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

4. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.  

5. En el **dirección (URI)** cuadro de texto, especifique el URI de conexión para conectarse al sistema SAP. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  

6. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **enlace** ficha. Desde el **BindingType** lista desplegable, seleccione **sapBinding**.  

7. Si va a crear un puerto de envío en el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:  

   1.  Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.  

   2.  Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  

8. Si va a crear un puerto de recepción, en el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **otros** pestaña y realice una de las siguientes acciones:  

   1.  Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.  

   2.  Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  

9. Haga clic en **Aceptar**.  

### <a name="enter-the-connection-uri-for-the-wcf-sap-port"></a>Escriba el URI de conexión para el puerto de SAP de WCF  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. Agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).  

3. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

4. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el adaptador SAP de WCF que agregó anteriormente y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

5. En el cuadro de diálogo Propiedades de transporte, haga clic en el **General** ficha.  

6. Haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  

7. En el cuadro de diálogo Propiedades de transporte, haga clic en el **enlace** pestaña y especificar los valores de propiedades de enlace.  

   > [!NOTE]
   >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, operaciones relacionadas con entrada de enlace de propiedades no están disponibles al configurar un puerto de envío debido a operaciones de entrada requieren una configuración de puerto de recepción.  

8. Si va a crear un puerto de envío, en el cuadro de diálogo Propiedades de transporte, haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:  

   1.  Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.  

   2.  Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  

9. Si va a crear un puerto de recepción, en el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **otros** pestaña y realice una de las siguientes acciones:  

    1.  Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.  

    2.  Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  

10. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)