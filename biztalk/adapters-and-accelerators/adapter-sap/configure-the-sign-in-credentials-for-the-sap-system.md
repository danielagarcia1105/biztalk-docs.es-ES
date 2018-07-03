---
title: Configurar el inicio de sesión en las credenciales para el sistema SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb41106b-b673-4fcf-a56e-6208e3113469
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c788bf8c98fc06511ce692c84600f040443dd993
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989173"
---
# <a name="configure-the-sign-in-credentials-for-the-sap-system"></a>Configurar el inicio de sesión en las credenciales para el sistema SAP
El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requiere que los clientes de adaptador proporcionar las credenciales del cliente. El adaptador usa estas credenciales para autenticar al usuario con el sistema SAP y para establecer una conexión.  

 Los clientes del adaptador pueden proporcionar tanto las credenciales de cliente en tiempo de diseño o tiempo de ejecución. En tiempo de diseño, se necesitan credenciales para generar los metadatos. En tiempo de ejecución, se necesitan credenciales para realizar operaciones en el sistema SAP. Esta sección proporciona información sobre cómo especificar las credenciales del cliente en tiempo de diseño y tiempo de ejecución.  

## <a name="enter-the-client-credentials-at-design-time"></a>Escriba las credenciales del cliente en tiempo de diseño  
 Tiempo de diseño, puede especificar las credenciales mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

### <a name="enter-credentials-using-consume-adapter-service-add-in"></a>Escriba las credenciales mediante el complemento Consume Adapter Service  

1.  Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **Consume Adapter Service**.|  
    |**Templates** (Plantillas [C++])|Haga clic en **Consume Adapter Service**.|  

3.  Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.  

4.  En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** , seleccione **sapBinding**y, a continuación, haga clic en **configurar**.  

5.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** pestaña y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.  

6.  Haga clic en **Aceptar**.  

### <a name="enter-credentials-using-add-adapter-metadata-wizard"></a>Escriba las credenciales mediante el Asistente para agregar metadatos de adaptador  

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

6. En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** , seleccione **sapBinding**y, a continuación, haga clic en **configurar**.  

7. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** pestaña y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.  

8. Haga clic en **Aceptar**.  

## <a name="enter-client-credentials-at-run-time"></a>Escriba las credenciales del cliente en tiempo de ejecución  
 Para el tiempo de ejecución, puede especificar las credenciales del cliente como parte de la configuración del puerto WCF-Custom o WCF-SAP en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

### <a name="enter-credentials-for-the-wcf-custom-port"></a>Escriba las credenciales para el puerto de WCF-Custom  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

3. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

4. Para un puerto de envío en el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:  

   -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.  

   -   Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  

5. Para un puerto de recepción, en el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **otros** pestaña y realice una de las siguientes acciones:  

   -   Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.  

   -   Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada.  

6. Haga clic en **Aceptar**.  

### <a name="enter-credentials-for-the-wcf-sap-port"></a>Escriba las credenciales para el puerto de SAP de WCF  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. Agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).  

3. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

4. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el adaptador SAP de WCF que agregó anteriormente y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

5. Si va a crear un puerto de envío, en el cuadro de diálogo Propiedades de transporte, haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:  

   1.  Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.  

   2.  Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  

6. Si va a crear un puerto de recepción, en el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **otros** pestaña y realice una de las siguientes acciones:  

   1.  Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.  

   2.  Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  

7. Haga clic en **Aceptar**.  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] También es compatible con el sistema de inicio de sesión único (SSO) empresarial. Inicio de sesión único solo es aplicable en el escenario de BizTalk, en el que el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] es consciente de las aplicaciones afiliadas SSO. Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).

## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)