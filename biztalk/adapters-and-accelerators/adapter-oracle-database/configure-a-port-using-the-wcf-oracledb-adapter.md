---
title: Configurar un puerto mediante el adaptador de WCF-OracleDB en BizTalk | Microsoft Docs
description: Creación de envío WCF-OracleDB y puertos de recepción para usar el adaptador de Oracle DB en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9eafefb-9b30-4801-9be9-6034ae0d3b7d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aee5b39d077c48317e557072c54ba032ebe82a24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009181"
---
# <a name="configure-a-port-using-the-wcf-oracledb-adapter"></a>Configurar un puerto mediante el adaptador de WCF-OracleDB
Configuración de WCF-OracleDB de envío y puertos de recepción para realizar operaciones de entrada y salidas en la base de datos de Oracle mediante el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx). 
  
## <a name="deploy-adapters-to-send-messages-to-oracle-database"></a>Implementar los adaptadores para enviar mensajes a la base de datos de Oracle  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Agregar el adaptador de WCF-OracleDB a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregación del adaptador de base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).  
  
3. En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
4. Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
5. Haga clic en **puertos de envío**, apunte a **New**y, a continuación, elija el tipo de puerto que desea configurar según el modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y la base de datos de Oracle.  
  
6. En el **propiedades de puerto de envío** cuadro de diálogo el **General** , escriba un nombre para el puerto de envío.  
  
7. Desde el **tipo** la lista desplegable, seleccione OracleDB de WCF y, a continuación, haga clic en **configurar**.  
  
8. En el cuadro de diálogo Propiedades de transporte, realice lo siguiente:  
  
   1. Haga clic en el **General** pestaña, haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  
  
   2. En el **General** ficha la **acción** texto, escriba la acción para la operación. Consulte [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) para obtener una lista de acciones para cada operación. Por ejemplo, la acción para invocar la operación de inserción de una tabla de empleados en el esquema de recursos humanos en una base de datos de Oracle es:  
  
      ```  
      http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEE/Select  
      ```  
  
   3. Haga clic en el **enlace** pestaña y especificar los valores de las propiedades de enlace expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).
  
      > [!NOTE]
      >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, las propiedades de enlace relacionadas con las notificaciones no están disponibles al configurar un puerto de envío porque las notificaciones son operaciones de entrada y requieren una configuración de puerto de recepción.  
  
   4. Haga clic en el **credenciales** pestaña y, a continuación, realice uno de los siguientes:  
  
      -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle.  
  
          -   Para conectar con las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.  
  
          -   Para conectarse mediante la autenticación de Windows, escriba **/** en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.  
  
      -   Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  
  
   5. Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
9. Desde el **controlador de envío** lista, seleccione **BizTalkServerApplication**.  
  
10. Si eligió **puerto de envío unidireccional estático** en el paso 5, especifique una canalización de envío. Desde el **canalización de envío** lista, seleccione la canalización que corresponde a XMLTransmit.  
  
11. Si eligió **puerto de petición-respuesta estático** en el paso 4, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
    2.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.  
  
12. Haga clic en **Aceptar**.  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-database"></a>Implementar los adaptadores para recibir mensajes de la base de datos de Oracle  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Agregar el adaptador de WCF-OracleDB a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregación del adaptador de base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).  
  
3. En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
4. Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
5. Haga clic en **puertos de recepción**, apunte a **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta**, en función de la modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y la base de datos de Oracle.  
  
6. En el **propiedades de puerto de recepción** cuadro de diálogo el **General** , escriba un nombre para el puerto de recepción.  
  
7. En el **ubicaciones de recepción** , haga clic **New**. El **propiedades de ubicación de recepción** aparece el cuadro de diálogo.  
  
8. En el **propiedades de ubicación de recepción** diálogo cuadro, realice lo siguiente:  
  
   1.  Especifique un nombre para la ubicación de recepción.  
  
   2.  Desde el **tipo** la lista desplegable, seleccione OracleDB de WCF y, a continuación, haga clic en **configurar**.  
  
9. En el cuadro de diálogo Propiedades de transporte, realice lo siguiente:  
  
   1. Haga clic en el **General** pestaña, haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  
  
   2. Haga clic en el **enlace** pestaña y especificar valores para enlazar las propiedades expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).
  
      > [!NOTE]
      >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, las propiedades de enlace relacionadas con las notificaciones no están disponibles al configurar un puerto de envío porque las notificaciones son operaciones de entrada y requieren una configuración de puerto de recepción.  
  
   3. Haga clic en el **comportamiento** pestaña para establecer el nivel de aislamiento de transacción. Para obtener más información acerca de cómo establecer el nivel de aislamiento de transacción, vea [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md).  
  
   4. Haga clic en el **otros** pestaña y realice una de las siguientes acciones:  
  
      -   Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle.  
  
          -   Para conectar con las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.  
  
          -   Para conectarse mediante la autenticación de Windows, escriba **/** en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.  
  
      -   Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  
  
   5. Para volver a la **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
10. Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.  
  
11. Si eligió **puerto de recepción unidireccional** en el paso 5, especifique una canalización de recepción. Desde el **canalización de recepción** lista, seleccione la canalización XMLReceive correspondiente.  
  
12. Si eligió **puerto de recepción de solicitud-respuesta** en el paso 5, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.  
  
    2.  Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
13. En el **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
14. En el **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
   [Configurar manualmente un enlace de puerto físico para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)
 
 [Conectarse a la base de datos de Oracle mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)