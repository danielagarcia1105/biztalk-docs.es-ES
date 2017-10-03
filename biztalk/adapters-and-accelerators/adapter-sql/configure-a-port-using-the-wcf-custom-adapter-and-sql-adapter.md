---
title: Configurar un puerto mediante el adaptador de WCF-custom y el adaptador de SQL en BizTalk | Documentos de Microsoft
description: "Crear envío WCF-custom y puertos de recepción para usar el adaptador de SQL Server en BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d44d9932-0a5e-4072-a480-2f8dc544ca79
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c2a47cf267bd3316600ad68a241a204090f3da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter"></a>Configurar un puerto mediante el adaptador de WCF-custom y el adaptador de SQL
Pasos para configurar el envío de WCF-Custom y puertos de recepción para realizar operaciones de entrada y salidas en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx). 
  
## <a name="deploy-adapters-to-send-messages-to-sql-server"></a>Implementar los adaptadores para enviar mensajes a SQL Server  
 Realice los pasos siguientes para configurar un puerto de envío WCF-Custom para enviar mensajes a SQL Server mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.    
 
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
4.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, seleccione el tipo de puerto que desea configurar según el modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y SQL Server.  
  
5.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de envío.  
  
6.  Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
    1.  Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para SQL Server. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
    2.  En el **General** ficha la **acción** texto, escriba la acción para la operación. Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) para obtener una lista de acciones para cada operación. Por ejemplo, la acción que se va a invocar la operación de inserción en una tabla de una base de datos de SQL Server es:  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
        > [!NOTE]
        >  Empleado es el nombre de una tabla de base de datos de SQL Server.  
  
    3.  Haga clic en el **enlace** ficha y desde el **BindingType** lista, seleccione **sqlBinding**. Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
    4.  Haga clic en el **credenciales** ficha y, a continuación, realice una de las siguientes acciones:  
  
        -   Seleccione el **no use Single Sign-On** opción, especifique el nombre de usuario y contraseña para conectarse a SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas.  
  
            > [!NOTE]
            >  Si desea conectarse a SQL Server mediante la autenticación de Windows, especifique un nombre de usuario en blanco y una contraseña. Antes de hacerlo, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server mediante la autenticación de Windows con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
        -   Seleccione el **Use Single Sign-On** opción y, a continuación, especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  
  
             Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).  
  
    5.  Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
8.  Desde el **controlador de envío** lista, seleccione **BizTalkServerApplication**.  
  
9. Si ha elegido **puerto de envío unidireccional estático** en el paso 4, especifique una canalización de envío. Desde el **canalización de envío** lista, seleccione la canalización que corresponde a XMLTransmit.  
  
10. Si ha elegido **puerto de petición-respuesta estático** en el paso 4, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
    2.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.  
  
11. Haga clic en **Aceptar**.  
  
## <a name="deploy-adapters-to-receive-messages-from-sql-server"></a>Implementar los adaptadores para recibir mensajes de SQL Server
 Realice los siguientes pasos para configurar un WCF-Custom puerto de recepción para recibir mensajes de SQL Server mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
4.  Haga clic en **puertos de recepción**, seleccione **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta**, en función de la modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y SQL Server.  
  
5.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.  
  
6.  En el **ubicaciones de recepción** , haga clic en **nuevo**. El **propiedades de la ubicación de recepción** aparece el cuadro de diálogo.  
  
7.  En el **propiedades de la ubicación de recepción** diálogo cuadro, realice lo siguiente:  
  
    1.  Especifique un nombre para la ubicación de recepción.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
8.  En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
    1.  Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para SQL Server. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
    2.  Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sqlBinding**. Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
    3.  Haga clic en el **comportamiento** pestaña para establecer el nivel de aislamiento de transacción. Para obtener más información acerca de cómo establecer el nivel de aislamiento de transacción, vea [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).  
  
    4.  Haga clic en el **otros** ficha y realice una de las siguientes acciones:  
  
        -   Seleccione **cuenta de usuario**y especifique el nombre de usuario y la contraseña para conectarse a SQL Server. Tenga en cuenta que el nombre de usuario y la contraseña distinguen entre mayúsculas y minúsculas.  
  
            > [!NOTE]
            >  Si desea conectarse a SQL Server mediante la autenticación de Windows, especifique un nombre de usuario en blanco y una contraseña. Antes de hacerlo, el usuario de Windows con la que ha iniciado sesión debe agregarse a SQL Server como se describe en [conectar con SQL Server mediante la autenticación de Windows con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
        -   Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  
  
             Para obtener más información acerca de la seguridad con respecto a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).  
  
    5.  Para volver a la **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
9. Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.  
  
10. Si ha elegido **puerto de recepción unidireccional** en el paso 4, especifique una canalización de recepción. Desde el **canalización de recepción** lista, seleccione la canalización XMLReceive correspondiente.  
  
11. Si ha elegido **puerto de recepción de solicitud-respuesta** en el paso 4, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.  
  
    2.  Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
12. En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
13. En el **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Configurar manualmente un enlace de puerto físico para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)