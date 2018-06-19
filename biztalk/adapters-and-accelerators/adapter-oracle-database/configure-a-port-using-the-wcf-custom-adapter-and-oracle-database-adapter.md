---
title: Configurar un puerto mediante el adaptador WCF-custom y el adaptador de la base de datos de Oracle | Documentos de Microsoft
description: Crear envío WCF-custom y puertos de recepción para usar el adaptador de base de datos de Oracle en el servidor BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c99ff526-ad97-4095-812f-0ce88b071e7f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7831ab57e7cae268aa1f47f380c69ef854b092b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215860"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter"></a>Configurar un puerto mediante el adaptador WCF-custom y el adaptador de la base de datos de Oracle
Cómo configurar el envío de WCF-Custom y puertos de recepción para realizar operaciones de entrada y salidas en la base de datos de Oracle mediante el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Vea [permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) para obtener instrucciones de permisos.
  
## <a name="deploy-adapters-for-sending-messages-to-an-oracle-database"></a>Implementar los adaptadores para enviar mensajes a una base de datos de Oracle  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
4.  Haga clic en **puertos de envío**, seleccione **New**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y la base de datos de Oracle.  
  
5.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de envío.  
  
6.  Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
    1.  Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para la base de datos de Oracle. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  
  
    2.  En el **General** ficha la **acción** texto, escriba la acción para la operación. Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) para obtener una lista de acciones para cada operación. Por ejemplo, la acción que se va a invocar la operación de inserción de una tabla de empleados en el esquema de recursos humanos en una base de datos de Oracle es:  
  
        ```  
        http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEE/Select  
        ```  
  
    3.  Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **oracleDBBinding**. Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener más información acerca de las propiedades de enlace, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  
  
    4.  Haga clic en el **credenciales** ficha y realice una de las siguientes acciones:  
  
        -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.  
  
            -   Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.  
  
            -   Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.  
  
        -   Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de SSO.  
  
         Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador de la base de datos de Oracle y BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).  
  
         Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
8.  Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.  
  
9. Si ha elegido **puerto de envío unidireccional estático** en el paso 4, especifique una canalización de envío. Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
10. Si ha elegido **puerto de petición-respuesta estático** en el paso 4, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
    2.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.  
  
11. Haga clic en **Aceptar**.  
  
## <a name="deploy-adapters-for-receiving-messages-from-an-oracle-database"></a>Implementar los adaptadores para recibir mensajes desde una base de datos de Oracle  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
4.  Haga clic en **puertos de recepción**, seleccione **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta**, en función de la modo de comunicación entre el servidor BizTalk Server y la base de datos de Oracle.  
  
5.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.  
  
6.  En el **ubicaciones de recepción** , haga clic en **nuevo**. El **propiedades de la ubicación de recepción** aparece el cuadro de diálogo.  
  
7.  En el **propiedades de la ubicación de recepción** diálogo cuadro, realice lo siguiente:  
  
    1.  Especifique un nombre para la ubicación de recepción.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
8.  En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
    1.  Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para la base de datos de Oracle. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  
  
    2.  Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **oracleDBBinding**. Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener más información acerca de las propiedades de enlace, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  
  
    3.  Haga clic en el **otros** ficha y realice una de las siguientes acciones:  
  
        -   Seleccione **cuenta de usuario**y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.  
  
            -   Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.  
  
            -   Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.  
  
        -   Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada.  
  
         Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador de la base de datos de Oracle y BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).
  
         Para volver a la **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
9. Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.  
  
10. Si ha elegido **puerto de recepción unidireccional** en el paso 4, especifique una canalización de recepción. Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.  
  
11. Si ha elegido **puerto de recepción de solicitud-respuesta** en el paso 4, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.  
  
    2.  Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
12. En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
13. En el **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Configurar manualmente un enlace de puerto físico para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)   
 [Conectarse a la base de datos de Oracle mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)