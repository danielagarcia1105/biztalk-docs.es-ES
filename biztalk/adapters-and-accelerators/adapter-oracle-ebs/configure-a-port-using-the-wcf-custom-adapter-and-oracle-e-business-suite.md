---
title: Configurar un puerto mediante el adaptador de WCF-custom y Oracle E-Business Suite en BizTalk | Documentos de Microsoft
description: Utilice el adaptador WCF-Custom para recibir o enviar mensajes desde Oracle EBS en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83d0bb00-934c-40cf-8833-354e7ce7e927
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03f6071c4df6e60024483e897d577281b1f39487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218372"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-oracle-e-business-suite"></a>Configurar un puerto mediante el adaptador de WCF-custom y Oracle E-Business Suite
Cómo configurar el envío de WCF-Custom y puertos de recepción para realizar operaciones de entrada y salidas sobre el uso de Oracle E-Business Suite el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).
  
## <a name="deploy-adapters-to-send-messages-to-oracle-ebs"></a>Implementar los adaptadores para enviar mensajes a Oracle EBS  
 Siga estos pasos para configurar un puerto de envío WCF-Custom para enviar mensajes a Oracle E-Business Suite utilizando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1.  Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
4.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, seleccione el tipo de puerto que desea configurar según el modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y Oracle E-Business Suite.  
  
5.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de envío.  
  
6.  Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
    1.  Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para Oracle E-Business Suite. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).  
  
    2.  En el **General** ficha la **acción** texto, escriba la acción para la operación. Vea [mensajes y esquemas de mensaje para el adaptador de Oracle EBS](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)) para obtener una lista de acciones para cada operación. Por ejemplo, la acción que se va a invocar la operación de inserción en una tabla de interfaz (FA_BOOKS) en la aplicación de recurso es:  
  
        ```  
        InterfaceTables/Insert/OFA/FA/FA_BOOKS  
        ```  
  
    3.  Haga clic en el **enlace** ficha y desde el **BindingType** lista, seleccione **oracleEBSBinding**. Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
    4.  Haga clic en el **credenciales** ficha y, a continuación, realice una de las siguientes acciones:  
  
        -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  
  
            |Use|Para|  
            |--------------|----------------|  
            |**Para conectarse con credenciales de base de datos de Oracle**|Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.|  
            |**Para conectarse con credenciales de Oracle E-Business Suite**|Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace.|  
            |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**|Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.|  
            |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"**|Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlace de propiedad en blanco.|  
  
        -   Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.  
  
    5.  Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
8.  Desde el **controlador de envío** lista, seleccione **BizTalkServerApplication**.  
  
9. Si ha elegido **puerto de envío unidireccional estático** en el paso 4, especifique una canalización de envío. Desde el **canalización de envío** lista, seleccione la canalización que corresponde a XMLTransmit.  
  
10. Si ha elegido **puerto de petición-respuesta estático** en el paso 4, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
    2.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.  
  
11. Haga clic en **Aceptar**.  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-ebs"></a>Implementar los adaptadores para recibir mensajes desde Oracle EBS 
 Realizar los siguientes pasos para configurar un WCF-Custom puerto de recepción para recibir mensajes desde Oracle E-Business Suite mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1.  Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
4.  Haga clic en **puertos de recepción**, seleccione **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta**, en función de la modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y Oracle E-Business Suite.  
  
5.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.  
  
6.  En el **ubicaciones de recepción** , haga clic en **nuevo**. El **propiedades de la ubicación de recepción** aparece el cuadro de diálogo.  
  
7.  En el **propiedades de la ubicación de recepción** diálogo cuadro, realice lo siguiente:  
  
    1.  Especifique un nombre para la ubicación de recepción.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
8.  En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
    1.  Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para Oracle E-Business Suite. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).  
  
    2.  Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **oracleEBSBinding**. Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
    3.  Haga clic en el **comportamiento** pestaña para establecer el nivel de aislamiento de transacción. Para obtener más información acerca de cómo establecer el nivel de aislamiento de transacción, vea [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).  
  
    4.  Haga clic en el **otros** ficha y realice una de las siguientes acciones:  
  
        -   Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  
  
            |Use|Para|  
            |--------------|----------------|  
            |**Para conectarse con credenciales de base de datos de Oracle**|Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.|  
            |**Para conectarse con credenciales de Oracle E-Business Suite**|Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace.|  
            |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**|Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.|  
            |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"**|Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlace de propiedad en blanco.|  
  
        -   Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada de SSO.  
  
    5.  Para volver a la **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
9. Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.  
  
10. Si ha elegido **puerto de recepción unidireccional** en el paso 4, especifique una canalización de recepción. Desde el **canalización de recepción** lista, seleccione la canalización XMLReceive correspondiente.  
  
11. Si ha elegido **puerto de recepción de solicitud-respuesta** en el paso 4, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.  
  
    2.  Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.  
  
12. En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
13. En el **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Configuración manual de un puerto físico de enlace para el adaptador de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)   
 [Conectarse a Oracle E-Business Suite mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)