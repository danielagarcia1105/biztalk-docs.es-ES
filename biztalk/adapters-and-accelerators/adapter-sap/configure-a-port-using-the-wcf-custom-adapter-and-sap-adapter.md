---
title: Configurar un puerto mediante el adaptador WCF-custom y el adaptador SAP en BizTalk | Microsoft Docs
description: Crear un puerto personalizado de WCF para enviar o recibir mensajes de SAP mediante el adaptador de mySAP en módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3962456-e9ac-4575-8266-b35e892dd428
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9baf552efc102d13b83b28f5c5b0c473147b2812
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982949"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sap-adapter"></a>Configurar un puerto mediante el adaptador WCF-custom y el adaptador SAP
Este tema proporciona instrucciones sobre cómo configurar el envío de WCF-Custom y puertos de recepción para realizar operaciones de entrada y salidas en el sistema de SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos de usuario mínimos de seguridad](../../core/minimum-security-user-rights.md). 
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a>Implementar los adaptadores para enviar mensajes a SAP  
Complete los pasos siguientes para configurar un WCF-Custom el puerto de envío para enviar mensajes al sistema de SAP mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3. Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
4. Haga clic en **puertos de envío**, apunte a **New**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre el servidor BizTalk Server y el sistema SAP.  
  
5. En el **propiedades de puerto de envío** cuadro de diálogo el **General** , escriba un nombre para el puerto de envío.  
  
6. Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
7. En el **propiedades de transporte WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
   1. Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para el sistema SAP. Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
   2. En el **General** ficha la **acción** texto, escriba la acción para la operación. Consulte [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) para obtener una lista de acciones para cada operación. Por ejemplo, la acción que se invoca el RFC_CUSTOMER_GET sería:  
  
      ```  
      http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
      ```  
  
   3. Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**. Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
   4. Haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:  
  
      -   Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.  
  
      -   Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de SSO.  
  
           Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).
  
           Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
8. Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.  
  
9. Si eligió un puerto de envío unidireccional estático en el paso 4, especifique una canalización de envío. Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.  
  
10. Si eligió **puerto de petición-respuesta estático** en el paso 4, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.  
  
    2.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.  
  
11. Haga clic en **Aceptar**.  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a>Implementar los adaptadores para recibir mensajes de SAP
Complete los pasos siguientes para configurar un WCF-Custom puerto de recepción para recibir mensajes de sistema de SAP mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3. Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
4. Haga clic en **puertos de recepción**, apunte a **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta** en función de la modo de comunicación entre el servidor BizTalk Server y el sistema SAP.  
  
5. En el **propiedades de puerto de recepción** cuadro de diálogo el **General** , escriba un nombre para el puerto de recepción.  
  
6. En el **ubicaciones de recepción** , haga clic **New**. El **propiedades de ubicación de recepción** aparece el cuadro de diálogo.  
  
7. En el **propiedades de ubicación de recepción** diálogo cuadro, realice lo siguiente:  
  
   1.  Especifique un nombre para la ubicación de recepción.  
  
   2.  Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
8. En el **propiedades de transporte WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
   1.  Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para el sistema SAP. Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
   2.  Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
   3.  Haga clic en el **otros** pestaña y realice una de las siguientes acciones:  
  
       -   Seleccione **cuenta de usuario**y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.  
  
       -   Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada.  
  
            Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).
  
            Haga clic en **Aceptar** para volver a la **propiedades de ubicación de recepción** cuadro de diálogo.  
  
9. Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.  
  
10. Si eligió **puerto de recepción unidireccional** en el paso 4, especifique una canalización de recepción. Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.  
  
11. Si eligió **puerto de recepción de solicitud-respuesta** en el paso 4, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.  
  
    2.  Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.  
  
12. Haga clic en **Aceptar i**n el **propiedades de ubicación de recepción** cuadro de diálogo.  
  
13. Haga clic en **Aceptar** en el **propiedades de puerto de recepción** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
[Configurar manualmente un enlace de puerto físico para el adaptador de SAP](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)