---
title: Configurar las credenciales de inicio de sesión para Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 743ced51-706b-4788-b5a8-e0ed8ffb3b48
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08081cc1e59181f3cd6aad0dfa532b060287d2ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978949"
---
# <a name="configure-the-sign-in-credentials-for-the-oracle-e-business-suite"></a>Configurar las credenciales de inicio de sesión para Oracle E-Business Suite
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]requiere que los clientes de adaptador proporcionar las credenciales del cliente. El adaptador usa estas credenciales para autenticar al usuario con Oracle E-Business Suite y para establecer una conexión.  

 Los clientes del adaptador pueden proporcionar las credenciales del cliente tanto al usar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y cuando se usa el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Cuando se usa [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], se necesitan credenciales para generar los metadatos. Cuando se usa el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, se necesitan credenciales para realizar operaciones en Oracle E-Business Suite.  

> [!IMPORTANT]
>  Puede especificar las credenciales para Oracle E-Business Suite o la base de datos de Oracle subyacente. Puede especificar las credenciales para conectarse y generar los metadatos. Sin embargo, al realizar una operación para invocar un artefacto de Oracle E-Business Suite, debe especificar las credenciales de Oracle E-Business Suite porque son necesarias para establecer el contexto de la aplicación para la aplicación de Oracle E-Business Suite que desea invocar. Para obtener más información acerca del contexto de las aplicaciones de configuración, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  

 Esta sección proporciona información sobre cómo especificar las credenciales del cliente en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

## <a name="specifying-credentials-from-visual-studio"></a>Especificar las credenciales desde Visual Studio  
 Desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], debe especificar las credenciales mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

#### <a name="to-specify-credentials-using-consume-adapter-service-add-in"></a>Especificar credenciales mediante el complemento Consume Adapter Service  

1.  Haga clic en el proyecto de BizTalk y, a continuación, seleccione **agregar elementos generados**.  

2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **Consume Adapter Service**.|  
    |**Templates** (Plantillas [C++])|Haga clic en **Consume Adapter Service**.|  

3.  Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.  

4.  En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** , seleccione **oracleEBSBinding**y, a continuación, haga clic en **configurar**.  

5.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** lista, seleccione **Username** y Especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  

    |Use|Para|  
    |--------------|----------------|  
    |**Para conectarse con credenciales de base de datos de Oracle**|Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.|  
    |**Para conectarse con credenciales de Oracle E-Business Suite**|Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace.|  
    |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**|Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.|  
    |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"**|Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlaza la propiedad en blanco.|  

6.  Haga clic en **Aceptar**.  

#### <a name="to-specify-credentials-using-add-adapter-metadata-wizard"></a>Especificar credenciales mediante el Asistente para agregar metadatos de adaptador  

1. Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

2. En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  


   |    Use    |           Para            |
   |----------------|---------------------------------|
   | **Categorías** |     Haga clic en **agregar adaptador**.      |
   | **Templates** (Plantillas [C++])  | Haga clic en **agregar metadatos de adaptador**. |


3. Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

4. En el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], seleccione **WCF-OracleEBS**. Seleccione el equipo donde está instalado BizTalk Server y el nombre de la base de datos de BizTalk.  

   > [!IMPORTANT]
   >  Si ya tiene un puerto de WCF-OracleEBS configurado en BizTalk, seleccione el puerto de la lista de puertos.  

5. Haga clic en **Siguiente**.  

6. En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** , seleccione **oracleEBSBinding**y, a continuación, haga clic en **configurar**.  

7. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** lista, seleccione **Username** y Especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  


   |                                         Use                                          |                                                                                                                                               Para                                                                                                                                                |
   |-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                     **Para conectarse con credenciales de base de datos de Oracle**                      |                                                                          Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.                                                                          |
   |                 **Para conectarse con credenciales de Oracle E-Business Suite**                  | Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace. |
   | **Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**  |                                                                                                         Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.                                                                                                         |
   | **Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"** |                                       Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlaza la propiedad en blanco.                                       |


8. Haga clic en **Aceptar**.  

## <a name="specifying-credentials-from-the-biztalk-server-administration-console"></a>Especificar las credenciales de la consola de administración de BizTalk Server  
 Desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe especificar las credenciales como parte de la configuración del puerto WCF-Custom o WCF-OracleEBS.  

#### <a name="to-specify-credentials-for-the-wcf-custom-port"></a>Para especificar las credenciales para el puerto de WCF-Custom  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

3. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

4. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **enlace** ficha. Desde el **BindingType** lista desplegable, seleccione **oracleEBSBinding**.  

5. Si va a crear un puerto de envío en el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:  

   -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  

       |Use|Para|  
       |--------------|----------------|  
       |**Para conectarse con credenciales de base de datos de Oracle**|Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.|  
       |**Para conectarse con credenciales de Oracle E-Business Suite**|Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace.|  
       |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**|Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.|  
       |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"**|Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlaza la propiedad en blanco.|  

   -   Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  

6. Si va a crear un puerto de recepción, en el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **otros** pestaña y realice una de las siguientes acciones:  

   -   Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  

       |Use|Para|  
       |--------------|----------------|  
       |**Para conectarse con credenciales de base de datos de Oracle**|Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.|  
       |**Para conectarse con credenciales de Oracle E-Business Suite**|Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace.|  
       |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**|Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.|  
       |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"**|Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlaza la propiedad en blanco.|  

   -   Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  

7. Haga clic en **Aceptar**.  

#### <a name="to-specify-credentials-for-the-wcf-oracleebs-port"></a>Para especificar las credenciales para el puerto de WCF-OracleEBS  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. Agregar el adaptador de WCF-OracleEBS a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador para Oracle E-Business Suite a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).  

3. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

4. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-OracleEBS**y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

5. En el cuadro de diálogo Propiedades de puerto, haga clic en el **enlace** ficha. Desde el **BindingType** lista desplegable, seleccione **oracleEBSBinding**.  

6. Si va a crear un puerto de envío, en el cuadro de diálogo Propiedades de transporte, haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:  

   -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  

       |Use|Para|  
       |--------------|----------------|  
       |**Para conectarse con credenciales de base de datos de Oracle**|Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.|  
       |**Para conectarse con credenciales de Oracle E-Business Suite**|Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace.|  
       |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**|Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.|  
       |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"**|Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlaza la propiedad en blanco.|  

   -   Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  

7. Si va a crear un puerto de recepción, en el cuadro de diálogo Propiedades de transporte, haga clic en el **otros** pestaña y realice una de las siguientes acciones:  

   -   Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  

       |Use|Para|  
       |--------------|----------------|  
       |**Para conectarse con credenciales de base de datos de Oracle**|Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.|  
       |**Para conectarse con credenciales de Oracle E-Business Suite**|Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace.|  
       |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**|Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.|  
       |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"**|Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlaza la propiedad en blanco.|  

   -   Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  

8. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)   
 [Conectarse a Oracle E-Business Suite mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)