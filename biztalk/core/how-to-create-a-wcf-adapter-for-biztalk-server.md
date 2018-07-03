---
title: Cómo crear un adaptador de WCF para BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ddaeb72-d263-4291-bd79-485fc736e6e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b07c838f9c53f7416ee0fea0e4efe71c49f60404
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989797"
---
# <a name="how-to-create-a-wcf-adapter-for-biztalk-server"></a>Cómo crear un adaptador de WCF para BizTalk Server
La creación de un adaptador de [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] de BizTalk consta de tres partes.  
  
- Cree un servicio Web [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] mediante el Asistente para publicación de Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Para obtener información sobre el uso de BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Asistente para publicación de servicio, consulte [publicar servicios WCF](../core/publishing-wcf-services.md).  
  
- Configure las ubicaciones y puertos de envío y recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener un ejemplo de cómo hacerlo, consulte [cómo configurar la recepción y ubicaciones de envío y puertos para la intercepción de WCF de BAM](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md).  
  
- Si aloja su solución en IIS, debe configurar el servicio web [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] usando el Administrador de IIS.  
  
  -   Debe conceder permisos al usuario de grupo de aplicaciones. Para ello, consulte [consideraciones de seguridad para la suplantación de IIS](../core/security-considerations-for-iis-impersonation.md).  
  
  -   Debe configurar la seguridad de directorios para su aplicación tal y como se describe en el siguiente procedimiento.  
  
## <a name="setting-the-directory-security"></a>Configurar la seguridad de directorios  
 Asegúrese de que Access Control para seguridad de directorios del servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] permite accesos anónimos. Esto facilitará el acceso a la aplicación.  
  
 Por ejemplo, si el nombre de la aplicación es MyBizTalkService3 y dispone de MyBizTalkService3·en los sitios web predeterminados, puede seguir este procedimiento para configurar el control de acceso.  
  
#### <a name="to-set-the-access-control-in-windows-server-2008"></a>Procedimiento para establecer el control de acceso en Windows Server 2008  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, expanda **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2. En la ventana del Administrador de Internet Information Services (IIS), expanda el nombre del servidor, **sitios**, expanda **Internet Information Services**y, a continuación, expanda **sitio Web predeterminado**.  
  
3. Haga clic en **MyBizTalkService3**y, a continuación, haga clic en **Editar permisos**.  
  
4. En el **seguridad** pestaña de la **MyBizTalkService3 Properties** cuadro de diálogo, haga clic en **editar**.  
  
5. En el **permisos de MyBizTalkService3** cuadro de diálogo, haga clic en **agregar**.  
  
6. En el **Seleccionar usuarios, equipos o grupos** cuadro de diálogo, escriba `anonymous logon` y, a continuación, haga clic en **Aceptar**.  
  
7. Seleccione **ANONYMOUS LOGON** en el **los nombres de usuario o grupo** sección, seleccione **lectura & ejecutar** en el **permisos de ANONYMOUS LOGON** sección y, a continuación, haga clic en **Aceptar**.  
  
8. Haga clic en **Aceptar** para cerrar el **MyBizTalkService3 Properties** cuadro de diálogo.  
  
   Para confirmar que el servicio está configurado correctamente, haga clic en el servicio y, a continuación, haga clic en **examinar**.  
  
   Si el servicio está configurado correctamente, verá una pantalla semejante a la que se muestra a continuación.  
  
   ![Pantalla de servicio BizTalkServiceInstance](../core/media/ff0e4ba0-59e7-47d9-a252-2859179f5645.gif "ff0e4ba0-59e7-47d9-a252-2859179f5645")  
  
## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de WCF para interceptar datos de BAM](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)