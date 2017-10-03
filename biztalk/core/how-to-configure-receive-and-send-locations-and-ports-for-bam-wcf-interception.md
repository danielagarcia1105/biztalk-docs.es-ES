---
title: "Cómo configurar la recepción y envío ubicaciones y puertos para la intercepción de WCF de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 501194dc-427a-4910-88c9-19cf47daeaad
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa77f39e8320c0d6598caaf5ea547592078774ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception"></a>Cómo configurar ubicaciones y puertos de recepción y de envío para la intercepción de WCF de BAM
En este procedimiento puede configurar las ubicaciones de recepción y de envío en un escenario de enrutamiento por contenidos (CBR) para mostrar los conceptos clave de un modo sencillo. Los conceptos mostrados aquí se pueden aplicar a una orquestación que se expone como servicio de [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
 En este procedimiento se presupone que:  
  
-   Modificar el archivo.config del equipo tal y como se muestra en [cómo agregar el comportamiento del Interceptor de BAM al archivo Machine.config](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md).  
  
-   Crea un adaptador de WCF para BizTalk Server como se muestra en [cómo crear un adaptador de WCF para BizTalk Server](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md).  
  
### <a name="to-configure-the-receive-and-send-locations"></a>Para configurar las ubicaciones de recepción y de envío  
  
1.  Abra la consola de administración de BizTalk. Para ello, haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  Expanda el árbol de la consola para ubicar el nodo Ubicaciones de recepción de la aplicación de BizTalk. Haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **aplicaciones**, haga clic en la aplicación que ha seleccionado en el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] cuadro de diálogo de tipo de servicio y, a continuación, haga clic en **ubicaciones de recepción**. Existirá una nueva ubicación de recepción correspondiente a la que se ha creado. Se encontrará en estado deshabilitado.  
  
3.  Haga doble clic en la ubicación de recepción para abrir el **propiedades de la ubicación de recepción** diálogo cuadro y, a continuación, elija WCF-Custom como tipo de transporte.  
  
4.  Haga clic en el **configurar** para abrir el **propiedades de transporte de WCF-Custom** cuadro de diálogo.  
  
5.  Haga clic en el **enlace** pestaña y seleccione el enlace que desea usar.  
  
6.  Haga clic en el **comportamiento** pestaña, haga clic en el **EndpointBehavior** nodo y, a continuación, seleccione **Agregar extensión**.  
  
7.  Seleccione el BAMEndPointExtension (ésta es la extensión que se ha agregado al archivo machine.config) y, a continuación, haga clic en **Aceptar**.  
  
     ![Pantalla de extensión de comportamiento seleccione](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")  
  
8.  Seleccione la extensión que acaba de crear, escriba los valores siguientes y, a continuación, haga clic en **Aceptar**:  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |PollingIntervalSec|10|  
    |ConnectionString|ConnectionString: Integrated Security = SSPI; Persist Security Info = False; Initial Catalog = BAMPrimaryImport; origen de datos =|  
  
9. En el **propiedades de la ubicación de recepción** cuadro de diálogo, seleccione **PassThruReceive** desde el **canalización de recepción** lista desplegable y, a continuación, haga clic en **Aceptar**.  
  
10. Habilite la ubicación de recepción y actualice la consola de administración. Un estado iniciado indica que la configuración se ha realizado correctamente.  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador WCF para interceptar datos BAM](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)