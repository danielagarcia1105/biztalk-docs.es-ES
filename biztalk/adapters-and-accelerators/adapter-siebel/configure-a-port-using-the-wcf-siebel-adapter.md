---
title: Configurar un puerto mediante el adaptador de WCF-Siebel | Microsoft Docs
description: Crear puertos de envío WCF-Siebel para usar el adaptador de aplicaciones Siebel eBusiness en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6314104-c742-440c-b530-b5a82295353a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eec0ca12c8b77d9327ddc7fae6136c75ff99202
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975525"
---
# <a name="configure-a-port-using-the-wcf-siebel-adapter"></a>Configurar un puerto mediante el adaptador de WCF-Siebel
Cómo configurar puertos de envío WCF-Siebel para llevar a cabo las operaciones salientes en un sistema de Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).
  
## <a name="deploy-adapters-for-sending-messages-to-a-siebel-system"></a>Implementar los adaptadores para enviar mensajes a un sistema de Siebel  
 Realice los pasos siguientes para configurar un puerto de envío WCF-Siebel para enviar mensajes a un sistema de Siebel mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).  
  
3. En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
4. Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
5. Haga clic en **puertos de envío**, apunte a **New**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre el servidor BizTalk Server y el sistema Siebel.  
  
6. En el **propiedades de puerto de envío** cuadro de diálogo el **General** , escriba un nombre para el puerto de envío.  
  
7. Desde el **tipo** lista desplegable, seleccione el WCF-Siebel adaptador que agregó anteriormente y haga clic en **configurar**.  
  
8. En el cuadro de diálogo Propiedades de transporte, realice lo siguiente:  
  
   1. Haga clic en el **General** pestaña, haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión del sistema de Siebel](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).  
  
   2. En el **General** ficha la **acción** texto, escriba la acción para la operación. Consulte [mensajes y esquemas de mensaje](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) para obtener una lista de acciones para cada operación. Por ejemplo, la acción para invocar la operación de inserción en el componente de negocio de la cuenta es:  
  
      ```  
      http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
      ```  
  
   3. Haga clic en el **enlace** pestaña y especificar los valores de las propiedades de enlace. Para obtener más información, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
   4. Haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:  
  
      - Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema Siebel.  
  
      - Seleccione el **Use Single Sign-On** opción y especifique una aplicación de afiliado ESSO.  
  
        Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).  
  
   5. Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  
  
9. Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.  
  
10. Si eligió un puerto de envío unidireccional estático en el paso 5, especifique una canalización de envío. Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.  
  
11. Si eligió un puerto de petición-respuesta estático en el paso 5, especifique el envío y las canalizaciones de recepción.  
  
    1.  Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.  
  
    2.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.  
  
12. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Configurar manualmente un enlace de puerto físico para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)