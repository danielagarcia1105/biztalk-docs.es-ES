---
title: Configurar un puerto mediante el adaptador de SAP de WCF de BizTalk | Microsoft Docs
description: Crear un puerto de SAP de WCF para enviar o recibir mensajes de SAP mediante el adaptador de mySAP en módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 420683f8-2516-4c65-895d-fe535824d450
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a80c778e34505755a147dccf48e50ea9ea3a18d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992677"
---
# <a name="configure-a-port-using-the-wcf-sap-adapter"></a>Configurar un puerto mediante el adaptador de SAP de WCF
Este tema proporciona instrucciones sobre cómo configurar SAP de WCF de envío y puertos de recepción para realizar operaciones de entrada y salidas en el sistema de SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a>Implementar los adaptadores para enviar mensajes a SAP  
Complete los pasos siguientes para configurar un SAP de WCF el puerto de envío para enviar mensajes al sistema de SAP mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).  
  
3. En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
4. Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
5. Haga clic en **puertos de envío**, apunte a **New**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre el servidor BizTalk Server y el sistema SAP.  
  
6. En el **propiedades de puerto de envío** cuadro de diálogo el **General** , escriba un nombre para el puerto de envío.  
  
7. Desde el **tipo** la lista desplegable, seleccione el adaptador SAP de WCF que agregó anteriormente y, a continuación, haga clic en **configurar**.  
  
8. En el cuadro de diálogo Propiedades de transporte, realice lo siguiente:  
  
   1. Haga clic en el **General** pestaña, haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
   2. En el **General** ficha la **acción** texto, escriba la acción para la operación. Consulte [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) para obtener una lista de acciones para cada operación. Por ejemplo, la acción que se invoca el RFC_CUSTOMER_GET sería:  
  
      ```  
      http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
      ```  
  
   3. Haga clic en el **enlace** pestaña y especificar valores para enlazar las propiedades expuestas por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
      > [!NOTE]
      >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, operaciones relacionadas con entrada de enlace de propiedades no están disponibles al configurar un puerto de envío debido a operaciones de entrada requieren una configuración de puerto de recepción.  
  
   4. Haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:  
  
   -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.  
  
   -   Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de SSO.  
  
        Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).  
  
        Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
9. Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.  
  
10. Si decide crear un **puerto de envío unidireccional estático** en el paso 5, especifique una canalización de envío. Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.  
  
11. Si decide crear un **puerto de petición-respuesta estático** en el paso 5, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.  
  
    2.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.  
  
12. Haga clic en **Aceptar**.  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a>Implementar los adaptadores para recibir mensajes de SAP  
Complete los pasos siguientes para configurar un SAP de WCF-puerto de recepción para recibir mensajes de sistema de SAP mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).  
  
3. En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
4. Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
5. Haga clic en **puertos de recepción**, apunte a **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta** en función de la modo de comunicación entre el servidor BizTalk Server y el sistema SAP.  
  
6. En el **propiedades de puerto de recepción** cuadro de diálogo el **General** , escriba un nombre para el puerto de recepción.  
  
7. En el **ubicaciones de recepción** , haga clic **New**. El **propiedades de ubicación de recepción** aparece el cuadro de diálogo.  
  
8. En el **propiedades de ubicación de recepción** diálogo cuadro, realice lo siguiente:  
  
   1.  Especifique un nombre para la ubicación de recepción.  
  
   2.  Desde el **tipo** la lista desplegable, seleccione el adaptador SAP de WCF que agregó anteriormente y, a continuación, haga clic en **configurar**.  
  
9. En el cuadro de diálogo Propiedades de transporte, realice lo siguiente:  
  
   1. Haga clic en el **General** pestaña, haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
   2. Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
      > [!NOTE]
      >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, operaciones relacionadas con entrada de enlace de propiedades no están disponibles al configurar un puerto de envío debido a operaciones de entrada requieren una configuración de puerto de recepción.  
  
   3. Haga clic en el **otros** pestaña y realice una de las siguientes acciones:  
  
   4. Seleccione **cuenta de usuario**y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.  
  
   5. Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada.  
  
       Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).  
  
       Haga clic en **Aceptar** para volver a la **propiedades de ubicación de recepción** cuadro de diálogo.  
  
10. Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.  
  
11. Si decide crear **puerto de recepción unidireccional** en el paso 5, especifique una canalización de recepción. Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.  
  
12. Si decide crear **puerto de recepción de solicitud-respuesta** en el paso 5, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.  
  
    2.  Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.  
  
13. Haga clic en **Aceptar** en el **propiedades de ubicación de recepción** cuadro de diálogo.  
  
14. Haga clic en **Aceptar** en el **propiedades de puerto de recepción** cuadro de diálogo.

## <a name="see-also"></a>Vea también
[Configurar manualmente un enlace de puerto físico para el adaptador de SAP](manually-configure-a-physical-port-binding-to-the-sap-adapter.md)