---
title: "Configurar el URI de conexión del adaptador de SQL | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6460b22-48e4-4b7e-b82e-151e7dab1e09
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9959a88f9799730cb60d2b05358f226b31d0f84c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-connection-uri-for-the-sql-adapter"></a>Configurar el URI de conexión del adaptador de SQL
Un URI de conexión es una cadena de conexión que contiene los parámetros necesarios para conectarse a SQL Server. Al usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], debe especificar el URI para conectarse a SQL Server para generar los metadatos. Al configurar un envío o recepción puerto utilizado por el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe especificar el URI para conectarse a SQL Server para realizar operaciones.  
  
## <a name="enter-the-connection-uri-from-visual-studio"></a>Escriba el URI de conexión desde Visual Studio  
 De [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], puede especificar el identificador URI de conexión mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
### <a name="use-the-consume-adapter-service-add-in"></a>Use el Consume Adapter Service complemento  
  
1.  Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **Consume Adapter Service**.|  
    |**Plantillas**|Haga clic en **Consume Adapter Service**.|  
  
3.  Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.  
  
4.  En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** seleccione **sqlBinding**y, a continuación, haga clic en **configurar**.  
  
5.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha. Desde el **tipo de credencial de cliente** lista, realice una de las siguientes acciones:  
  
    > [!NOTE]
    >  Si se conecta a SQL Server mediante autenticación de Windows, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server Using Windows Authentication con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
    |Haga clic en|Para|  
    |----------------|----------------|  
    |**Ninguno**|Conectarse a SQL Server mediante la autenticación de Windows.|  
    |**Windows**|Conectarse a SQL Server mediante la autenticación de Windows.|  
    |**Nombre de usuario**|Especifique un nombre de usuario y una contraseña para conectarse a SQL Server especificando credenciales para un usuario definido en la base de datos de SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas. **Nota:** si deja la **nombre de usuario** y **contraseña** campos como espacio en blanco, el adaptador se conecta a SQL Server mediante autenticación de Windows.|  
  
6.  Haga clic en el **propiedades de URI** pestaña y especificar valores para parámetros diferentes. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
7.  Haga clic en el **propiedades de enlace** pestaña y especificar valores para las propiedades de enlace, si hay alguno, que sean necesarias antes de generar el esquema. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
8.  Haga clic en **Aceptar**.  
  
### <a name="use-the-add-adapter-metadata-wizard"></a>Use el Asistente para agregar metadatos de adaptador  
  
1.  Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **agregar adaptador**.|  
    |**Plantillas**|Haga clic en **agregar metadatos de adaptador**.|  
  
3.  Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
4.  En el Asistente para agregar adaptador, seleccione **WCF-SQL**. Seleccione el equipo donde está instalado el servidor BizTalk Server y el nombre de la base de datos de BizTalk.  
  
    > [!IMPORTANT]
    >  Si ya tiene un puerto de WCF-SQL configurado en BizTalk, seleccione el puerto de la **puerto** lista.  
  
5.  Haga clic en **Siguiente**.  
  
6.  En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** lista desplegable, seleccione **sqlBinding**y, a continuación, haga clic en **configurar**.  
  
7.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** cuadro de lista desplegable, realice una de las siguientes acciones:  
  
    > [!NOTE]
    >  Si se conecta a SQL Server mediante autenticación de Windows, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server Using Windows Authentication con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
    |Haga clic en|Para|  
    |----------------|----------------|  
    |**Ninguno**|Conectarse a SQL Server mediante la autenticación de Windows.|  
    |**Windows**|Conectarse a SQL Server mediante la autenticación de Windows.|  
    |**Nombre de usuario**|Especifique un nombre de usuario y una contraseña para conectarse a SQL Server especificando credenciales para un usuario definido en la base de datos de SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas. **Nota:** si deja la **nombre de usuario** y **contraseña** campos como espacio en blanco, el adaptador se conecta a SQL Server mediante autenticación de Windows.|  
  
8.  Haga clic en el **propiedades de URI** y a continuación, especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
9. Haga clic en el **propiedades de enlace** ficha y, a continuación, especifique valores para las propiedades de enlace, si existe, requeridos por las operaciones de destino. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
    > [!NOTE]
    >  Si ha seleccionado un puerto de envío WCF-SQL existente, no es necesario especificar las propiedades de enlace. Las propiedades de enlace se toman de la configuración del puerto de envío. Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si los hubiera. En este caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos. Sin embargo, en tiempo de ejecución se pueden aplicables los valores especificados para propiedades de enlace en la configuración del puerto de envío.  
  
10. Haga clic en **Aceptar**.  
  
## <a name="enter-the-connection-uri-from-the-biztalk-server-administration-console"></a>Escriba el URI de conexión desde la consola de administración de BizTalk Server  
 Desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, puede especificar el URI de conexión como parte de WCF-Custom o una configuración de puerto de WCF-SQL.  
  
### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a>Escriba el URI de conexión para el puerto de WCF-Custom  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
3.  En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
    > [!NOTE]
    >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** ficha en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **nuevo**.  
  
4.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.  
  
5.  En el **dirección (URI)** cuadro de texto, especifique el URI de conexión para conectarse a SQL Server. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
6.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **enlace** ficha. Desde el **BindingType** lista desplegable, seleccione **sqlBinding**.  
  
7.  Si va a crear un puerto de envío en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** ficha y realice una de las siguientes acciones:  
  
    -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas.  
  
        > [!NOTE]
        >  Si desea conectarse a SQL Server mediante la autenticación de Windows, especifique un nombre de usuario en blanco y una contraseña. Antes de hacerlo, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server Using Windows Authentication con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
    -   Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  
  
8.  Si va a crear un puerto de recepción, en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **otros** ficha y realice una de las siguientes acciones:  
  
    -   Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas.  
  
        > [!NOTE]
        >  Si desea conectarse a SQL Server mediante la autenticación de Windows, especifique un nombre de usuario en blanco y una contraseña. Antes de hacerlo, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server Using Windows Authentication con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
    -   Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  
  
9. Haga clic en **Aceptar**.  
  
### <a name="enter-the-connection-uri-for-the-wcf-sql-port"></a>Escriba el URI de conexión para el puerto de WCF-SQL  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  Agregar el adaptador de WCF-SQL para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador de SQL a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).  
  
3.  En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
4.  En el cuadro de diálogo de propiedades de puerto de la **tipo** la lista desplegable, seleccione el adaptador de WCF-SQL que agregó anteriormente y, a continuación, haga clic en **configurar**.  
  
    > [!NOTE]
    >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** ficha en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **nuevo**.  
  
5.  En el cuadro de diálogo Propiedades de transporte, haga clic en el **General** ficha.  
  
6.  Haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
7.  En el cuadro de diálogo Propiedades de transporte, haga clic en el **enlace** pestaña y especificar los valores de propiedades de enlace.  
  
    > [!NOTE]
    >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, las propiedades de enlace relacionados con las notificaciones no están disponibles al configurar un puerto de envío porque las notificaciones son operaciones entrantes y requieren una configuración de puerto de recepción.  
  
8.  Si va a crear un puerto de envío, en el cuadro de diálogo de propiedades de transporte, haga clic en el **credenciales** ficha y realice una de las siguientes acciones:  
  
    -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas.  
  
        > [!NOTE]
        >  Si desea conectarse a SQL Server mediante la autenticación de Windows, especifique un nombre de usuario en blanco y una contraseña. Antes de hacerlo, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server Using Windows Authentication con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
    -   Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  
  
9. Si va a crear un puerto de recepción, en el cuadro de diálogo de propiedades de transporte, haga clic en el **otros** ficha y realice una de las siguientes acciones:  
  
    -   Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas.  
  
        > [!NOTE]
        >  Si desea conectarse a SQL Server mediante la autenticación de Windows, especifique un nombre de usuario en blanco y una contraseña. Antes de hacerlo, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server Using Windows Authentication con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
    -   Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  
  
10. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)