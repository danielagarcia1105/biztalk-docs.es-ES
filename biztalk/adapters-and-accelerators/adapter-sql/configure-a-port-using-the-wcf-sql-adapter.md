---
title: Configurar un puerto mediante el adaptador de WCF-SQL en BizTalk | Documentos de Microsoft
description: Crear el envío de WCF-SQL y puertos de recepción para usar el adaptador de SQL Server en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8cdc032-3160-43de-9510-7ca69506083e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9a2ca9bda40aa016efba95b89948f1d12bc49f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226412"
---
# <a name="configure-a-port-using-the-wcf-sql-adapter"></a>Configurar un puerto mediante el adaptador de WCF-SQL
Este tema proporciona instrucciones sobre cómo configurar WCF-SQL de envío y puertos de recepción para realizar operaciones de entrada y salidas en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).
  
## <a name="deploy-adapters-to-send-messages-to-sql-server"></a>Implementar los adaptadores para enviar mensajes a SQL Server  
 Realice los pasos siguientes para configurar un puerto de envío WCF-SQL para enviar mensajes a SQL Server mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  Agregar el adaptador de WCF-SQL para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador de SQL a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).  
  
3.  En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
4.  Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
5.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, seleccione el tipo de puerto que desea configurar según el modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y SQL Server.  
  
6.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de envío.  
  
7.  Desde el **tipo** la lista desplegable, seleccione el adaptador de WCF-SQL que agregó anteriormente y, a continuación, haga clic en **configurar**.  
  
8.  En el cuadro de diálogo Propiedades de transporte, haga lo siguiente:  
  
    1.  Haga clic en el **General** , haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
    2.  En el **General** ficha la **acción** texto, escriba la acción para la operación. Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) para obtener una lista de acciones para cada operación. Por ejemplo, la acción que se va a invocar la operación de inserción en una tabla de una base de datos de SQL Server es:  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
        > [!NOTE]
        >  Empleado es el nombre de una tabla de base de datos de SQL Server.  
  
    3.  Haga clic en el **enlace** pestaña y especificar valores para enlazar propiedades expuestas por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
        > [!NOTE]
        >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, las propiedades de enlace relacionados con las notificaciones no están disponibles al configurar un puerto de envío porque las notificaciones son operaciones entrantes y requieren una configuración de puerto de recepción.  
  
    4.  Haga clic en el **credenciales** ficha y, a continuación, realice una de las siguientes acciones:  
  
        -   Seleccione el **no use Single Sign-On** opción, especifique el nombre de usuario y contraseña para conectarse a SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas.  
  
            > [!NOTE]
            >  Si desea conectarse a SQL Server mediante la autenticación de Windows, especifique un nombre de usuario en blanco y una contraseña. Antes de hacerlo, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server Using Windows Authentication con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
        -   Seleccione el **Use Single Sign-On** opción y, a continuación, especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  
  
             Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).  
  
    5.  Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
9. Desde el **controlador de envío** lista, seleccione **BizTalkServerApplication**.  
  
10. Si decide crear **puerto de envío unidireccional estático** en el paso 5, especifique una canalización de envío. Desde el **canalización de envío** lista, seleccione la canalización que corresponde a XMLTransmit.  
  
11. Si decide crear **puerto de petición-respuesta estático** en el paso 5, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
    2.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.  
  
12. Haga clic en **Aceptar**.  
  
## <a name="deploy-adapters-to-receive-messages-from-sql-server"></a>Implementar los adaptadores para recibir mensajes de SQL Server  
 Realice los siguientes pasos para configurar un WCF-SQL puerto de recepción para recibir mensajes de SQL Server mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  Agregar el adaptador de WCF-SQL para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador de SQL a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).  
  
3.  En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
4.  Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
5.  Haga clic en **puertos de recepción**, seleccione **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta**, en función de la modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y SQL Server.  
  
6.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.  
  
7.  En el **ubicaciones de recepción** , haga clic en **nuevo**. El **propiedades de la ubicación de recepción** aparece el cuadro de diálogo.  
  
8.  En el **propiedades de la ubicación de recepción** diálogo cuadro, realice lo siguiente:  
  
    1.  Especifique un nombre para la ubicación de recepción.  
  
    2.  Desde el **tipo** la lista desplegable, seleccione el adaptador de WCF-SQL que agregó anteriormente y, a continuación, haga clic en **configurar**.  
  
9. En el cuadro de diálogo Propiedades de transporte, haga lo siguiente:  
  
    1.  Haga clic en el **General** , haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
    2.  Haga clic en el **enlace** pestaña y especificar valores para enlazar propiedades expuestas por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
        > [!NOTE]
        >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, las propiedades de enlace relacionados con las notificaciones no están disponibles al configurar un puerto de envío porque las notificaciones son operaciones entrantes y requieren una configuración de puerto de recepción.  
  
    3.  Haga clic en el **comportamiento** pestaña para establecer el nivel de aislamiento de transacción. Para obtener más información acerca de cómo establecer el nivel de aislamiento de transacción, vea [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).  
  
    4.  Haga clic en el **otros** ficha y realice una de las siguientes acciones:  
  
        -   Seleccione **cuenta de usuario**y especifique el nombre de usuario y la contraseña para conectarse a SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas.  
  
            > [!NOTE]
            >  Si desea conectarse a SQL Server mediante la autenticación de Windows, especifique un nombre de usuario en blanco y una contraseña. Antes de hacerlo, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server Using Windows Authentication con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
        -   Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  
  
             Para obtener más información acerca de la seguridad con respecto a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).  
  
    5.  Para volver a la **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
10. Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.  
  
11. Si decide crear **puerto de recepción unidireccional** en el paso 5, especifique una canalización de recepción. Desde el **canalización de recepción** lista, seleccione la canalización XMLReceive correspondiente.  
  
12. Si decide crear **puerto de recepción de solicitud-respuesta** en el paso 5, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.  
  
    2.  Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
13. En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
14. En el **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Configurar manualmente un enlace de puerto físico para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)