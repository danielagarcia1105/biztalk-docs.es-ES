---
title: "Configurar el URI de conexión para el adaptador de la base de datos de Oracle | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection URI, specifying at design time
- connection URI, specifying at run time
ms.assetid: 9f302b67-0bcc-44d1-9517-10d402873540
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63cede1957c2f5f34396bbe2251a98cfc3965e7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-connection-uri-for-the-oracle-database-adapter"></a>Configurar el URI de conexión para el adaptador de la base de datos de Oracle
Un URI de conexión es una cadena de conexión que contiene los parámetros necesarios para conectarse a la base de datos de Oracle. Al usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], debe especificar el URI para conectarse a la base de datos de Oracle para generar los metadatos. Al configurar una orquestación mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe especificar el URI para conectarse a la base de datos de Oracle para realizar operaciones.  
  
## <a name="specifying-the-connection-uri-from-visual-studio"></a>Especificar la conexión URI desde Visual Studio  
 Desde Visual Studio, debe especificar las credenciales mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
#### <a name="to-specify-the-connection-uri-using-consume-adapter-service-add-in"></a>Para especificar el URI de conexión mediante el complemento Consume Adapter Service  
  
1.  Haga clic en el proyecto de BizTalk y, a continuación, seleccione **agregar elementos generados**.  
  
2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **Consume Adapter Service**.|  
    |**Plantillas**|Haga clic en **Consume Adapter Service**.|  
  
3.  Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.  
  
4.  En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** seleccione **oracleDBBinding**y haga clic en **configurar**.  
  
5.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha desde y hacia el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle:  
  
    -   Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.  
  
    -   Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.  
  
6.  Haga clic en el **propiedades de URI** pestaña y especificar valores para parámetros diferentes. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  
  
7.  Haga clic en el **propiedades de enlace** pestaña y especifique los valores de enlace, si hay alguno, que sean necesarias antes de generar el esquema. Para obtener más información acerca de las propiedades de enlace, vea [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
8.  Haga clic en **Aceptar**.  
  
#### <a name="to-specify-the-connection-uri-using-add-adapter-metadata-wizard"></a>Para especificar el URI de conexión mediante el Asistente para agregar metadatos de adaptador  
  
1.  Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **agregar adaptador**.|  
    |**Plantillas**|Haga clic en **agregar metadatos de adaptador**.|  
  
3.  Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
4.  En el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], seleccione **WCF-OracleDB**. Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.  
  
    > [!IMPORTANT]
    >  Si ya tiene un puerto de WCF-OracleDB configurado en BizTalk, seleccione el puerto de la **puerto** lista.  
  
5.  Haga clic en **Siguiente**.  
  
6.  En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** seleccione **oracleDBBinding**y, a continuación, haga clic en **configurar**.  
  
7.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** lista, seleccione **nombre de usuario** y Especifique el nombre de usuario y la contraseña para conectarse a la base de datos de Oracle:  
  
    -   Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.  
  
    -   Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.  
  
8.  Haga clic en el **propiedades de URI** pestaña y especificar valores para parámetros diferentes. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  
  
9. Haga clic en el **propiedades de enlace** pestaña y especifique los valores de enlace, si hay alguno, que sean necesarias antes de generar el esquema. Para obtener más información acerca de las propiedades de enlace, vea [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
10. Haga clic en **Aceptar**.  
  
## <a name="specifying-the-connection-uri-from-the-biztalk-server-administration-console"></a>Especificar la conexión URI a partir de la consola de administración de BizTalk Server  
 Desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe especificar las credenciales como parte de la configuración del puerto WCF-Custom o WCF-OracleDB.  
  
#### <a name="to-specify-the-connection-uri-for-the-wcf-custom-port"></a>Para especificar el URI de conexión para el puerto de WCF-Custom  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
3.  En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
4.  Para un puerto de envío en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** ficha y realice una de las siguientes acciones:  
  
    -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.  
  
        -   Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.  
  
        -   Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.  
  
    -   Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  
  
5.  Para un puerto de recepción, en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **otros** ficha y realice una de las siguientes acciones:  
  
    -   Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.  
  
        -   Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.  
  
        -   Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.  
  
    -   Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada.  
  
6.  Haga clic en **Aceptar**.  
  
#### <a name="to-specify-the-connection-uri-for-the-wcf-oracledb-port"></a>Para especificar el URI de conexión para el puerto de WCF-OracleDB  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  Agregar el adaptador de WCF-OracleDB a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador de la base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).  
  
3.  En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  
  
4.  En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione **WCF-OracleDB**y, a continuación, haga clic en **configurar**.  
  
    > [!NOTE]
    >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** ficha en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **nuevo**.  
  
5.  En el cuadro de diálogo Propiedades de puerto, haga clic en el **enlace** ficha. Desde el **BindingType** lista desplegable, seleccione **oracleDBBinding**.  
  
6.  Si va a crear un puerto de envío, en el cuadro de diálogo de propiedades de transporte, haga clic en el **credenciales** ficha y realice una de las siguientes acciones:  
  
    -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle.  
  
        -   Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.  
  
        -   Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.  
  
    -   Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  
  
7.  Si va a crear un puerto de recepción, en el cuadro de diálogo de propiedades de transporte, haga clic en el **otros** ficha y realice una de las siguientes acciones:  
  
    -   Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle.  
  
        -   Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.  
  
        -   Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.  
  
    -   Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  
  
8.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)   
 [Conectarse a la base de datos de Oracle mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)