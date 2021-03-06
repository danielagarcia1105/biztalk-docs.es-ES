---
title: Configurar un puerto mediante el adaptador de WCF-OracleEBS en BizTalk | Microsoft Docs
description: Usar el adaptador de WCF-OracleEBS para recibir o enviar mensajes de Oracle EBS en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4c5c10-79a6-48d3-b4ee-dddf837f020b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dc78e6bd96f69bb92018af7a68007acfe47636d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988797"
---
# <a name="configure-a-port-using-the-wcf-oracleebs-adapter"></a>Configurar un puerto mediante el adaptador de WCF-OracleEBS
Configuración de WCF-OracleEBS de envío y puertos de recepción para realizar operaciones de entrada y salidas sobre el uso de Oracle E-Business Suite el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).
  
## <a name="deploy-adapters-to-send-messages-to-oracle-ebs"></a>Implementar los adaptadores para enviar mensajes a Oracle EBS 
 Realice los pasos siguientes para configurar un puerto de envío WCF-OracleEBS para enviar mensajes a Oracle E-Business Suite utilizando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.    
 
1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Agregar el adaptador de WCF-OracleEBS a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. [Agregar el adaptador para Oracle E-Business Suite a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md) se enumeran los pasos.
  
3. En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
4. Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
5. Haga clic en **puertos de envío**, apunte a **New**y, a continuación, elija el tipo de puerto que desea configurar según el modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y Oracle E-Business Suite.  
  
6. En el **propiedades de puerto de envío** cuadro de diálogo el **General** , escriba un nombre para el puerto de envío.  
  
7. Desde el **tipo** la lista desplegable, seleccione OracleEBS de WCF y, a continuación, haga clic en **configurar**.  
  
8. En el cuadro de diálogo Propiedades de transporte, realice lo siguiente:  
  
   1. Haga clic en el **General** pestaña, haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión, consulte [configurar el URI de conexión para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md).  
  
   2. En el **General** ficha la **acción** texto, escriba la acción para la operación. Consulte [mensajes y esquemas de mensaje para el adaptador de Oracle EBS](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md) para obtener una lista de acciones para cada operación. Por ejemplo, la acción para invocar la operación de inserción en una tabla de interfaz (FA_BOOKS) en la aplicación de recurso es:  
  
      ```  
      InterfaceTables/Insert/OFA/FA/FA_BOOKS  
      ```  
  
   3. Haga clic en el **enlace** pestaña y especificar los valores de las propiedades de enlace expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
      > [!NOTE]
      >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, las propiedades de enlace relacionadas con las notificaciones no están disponibles al configurar un puerto de envío porque las notificaciones son operaciones de entrada y requieren una configuración de puerto de recepción.  
  
   4. Haga clic en el **credenciales** pestaña y, a continuación, realice uno de los siguientes:  
  
      -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  
  
          |Use|Para|  
          |--------------|----------------|  
          |**Para conectarse con credenciales de base de datos de Oracle**|Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.|  
          |**Para conectarse con credenciales de Oracle E-Business Suite**|Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace.|  
          |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**|Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.|  
          |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"**|Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlaza la propiedad en blanco.|  
  
      -   Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  
  
   5. Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
9. Desde el **controlador de envío** lista, seleccione **BizTalkServerApplication**.  
  
10. Si eligió **puerto de envío unidireccional estático** en el paso 5, especifique una canalización de envío. Desde el **canalización de envío** lista, seleccione la canalización que corresponde a XMLTransmit.  
  
11. Si eligió **puerto de petición-respuesta estático** en el paso 4, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
    2.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.  
  
12. Haga clic en **Aceptar**.  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-ebs"></a>Implementar los adaptadores para recibir mensajes de Oracle EBS  
 Siga estos pasos para configurar un WCF-OracleEBS puerto de recepción para recibir mensajes desde Oracle E-Business Suite mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Agregar el adaptador de WCF-OracleEBS a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador para Oracle E-Business Suite a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).  
  
3. En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
4. Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
5. Haga clic en **puertos de recepción**, apunte a **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta**, en función de la modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y Oracle E-Business Suite.  
  
6. En el **propiedades de puerto de recepción** cuadro de diálogo el **General** , escriba un nombre para el puerto de recepción.  
  
7. En el **ubicaciones de recepción** , haga clic **New**. El **propiedades de ubicación de recepción** aparece el cuadro de diálogo.  
  
8. En el **propiedades de ubicación de recepción** diálogo cuadro, realice lo siguiente:  
  
   1.  Especifique un nombre para la ubicación de recepción.  
  
   2.  Desde el **tipo** la lista desplegable, seleccione OracleEBS de WCF y, a continuación, haga clic en **configurar**.  
  
9. En el cuadro de diálogo Propiedades de transporte, realice lo siguiente:  
  
   1. Haga clic en el **General** pestaña, haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión, consulte [configurar el URI de conexión para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md).  
  
   2. Haga clic en el **enlace** pestaña y especificar valores para enlazar las propiedades expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
      > [!NOTE]
      >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, las propiedades de enlace relacionadas con las notificaciones no están disponibles al configurar un puerto de envío porque las notificaciones son operaciones de entrada y requieren una configuración de puerto de recepción.  
  
   3. Haga clic en el **comportamiento** pestaña para establecer el nivel de aislamiento de transacción. Para obtener más información acerca de cómo establecer el nivel de aislamiento de transacción, vea [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).  
  
   4. Haga clic en el **otros** pestaña y realice una de las siguientes acciones:  
  
      -   Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  
  
          |Use|Para|  
          |--------------|----------------|  
          |**Para conectarse con credenciales de base de datos de Oracle**|Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.|  
          |**Para conectarse con credenciales de Oracle E-Business Suite**|Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace.|  
          |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**|Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.|  
          |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"**|Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlaza la propiedad en blanco.|  
  
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
 [Configurar manualmente un puerto físico de enlace para el adaptador de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)   
 [Conectarse a Oracle E-Business Suite mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)