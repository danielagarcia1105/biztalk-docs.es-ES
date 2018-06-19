---
title: Instalación de AppFabric conectarse para servicios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1de3bf49-e3cc-4d3f-9883-9a2c472f3647
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3d10862a6a60d173cc68c25d0dcc463d2f16e38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298692"
---
# <a name="installing-appfabric-connect-for-services"></a>Instalación de AppFabric conectarse para servicios
Esta guía proporciona instrucciones sobre cómo instalar BizTalk Server 2010 Feature Pack (octubre de 2010). El feature pack instala BizTalk Server 2010 AppFabric Connect para la característica de servicios que proporciona mejoras en la **Asistente de publicación de servicio de WCF de BizTalk** y **Asistente para el desarrollo de servicio de WCF adaptador**. Después de instalar el feature pack, podrá ampliar el alcance de sus instalaciones de artefactos de BizTalk Server o las aplicaciones en la nube mediante la adición de un punto de conexión de Bus de servicio de Windows Azure AppFabric LOB.  
  
## <a name="prerequisites"></a>Requisitos previos  
 BizTalk Server 2010 Feature Pack ofrece mejoras en el Asistente para publicación de servicio WCF de BizTalk y el Asistente de desarrollo del servicio de adaptador de WCF. Mientras el Asistente para publicación de servicio WCF de BizTalk está disponible con herramientas de desarrollo de BizTalk Server 2010, el Asistente para desarrollo de servicio de adaptador de WCF está disponible con BizTalk Adapter Pack 2010. Por lo tanto, antes de instalar el feature pack, debe tener herramientas de desarrollo de BizTalk Server 2010, BizTalk Adapter Pack 2010 o ambos instalado. Si tiene sólo una de estas instalado, se actualizará el Asistente relevante para la instalación del producto primario como parte de la instalación del paquete de características.  
  
 Además de estas funciones, hay algunos requisitos previos para utilizar a estos asistentes. La lista completa de requisitos previos para cada asistente se muestra en los temas que describen cómo utilizar a los asistentes. Los vínculos a los temas se proporcionan en [usar AppFabric Connect para los servicios](../technical-guides/installing-appfabric-connect-for-services.md#BKMK_Using).  
  
## <a name="installing-biztalk-server-2010-feature-pack"></a>Instalar BizTalk Server 2010 Feature Pack  
 Realice los pasos siguientes para instalar AppFabric Connect para los servicios:  
  
#### <a name="to-install-the-feature-pack"></a>Para instalar el feature pack  
  
1.  Descargar el AppFabric Connect para servicios instalables de [http://go.microsoft.com/fwlink/?LinkId=204701](http://go.microsoft.com/fwlink/?LinkId=204701). Ejecute el archivo autoextraíble de BizTalkServer2010_FeaturePack.exe para iniciar el programa de instalación de módulo de característica.  
  
2.  En el **bienvenida** página, haga clic en **siguiente**.  
  
3.  Acepte los términos de licencia y, a continuación, haga clic en **siguiente** y, a continuación, en la siguiente pantalla, haga clic en **siguiente** nuevo.  
  
4.  Al finalizar el Asistente para la instalación del paquete de características, haga clic en **finalizar**.  
  
##  <a name="BKMK_Using"></a>Usar AppFabric Connect para los servicios  
 Después de instalar AppFabric Connect para los servicios, puede hacer lo siguiente:  
  
-   Use la **Asistente de publicación de servicio de WCF de BizTalk** para exponer los artefactos de BizTalk (orquestaciones, esquemas, etc.) como servicios WCF con un extremo de retransmisión en el Bus de servicio de AppFabric de Azure. Para obtener más información, consulte [http://go.microsoft.com/fwlink/?LinkId=204700](http://go.microsoft.com/fwlink/?LinkId=204700).  
  
-   Use la **Asistente para desarrollo de servicio de adaptador de WCF** para exponer las operaciones en las aplicaciones de LOB como servicios WCF con un extremo de retransmisión en el Bus de servicio de AppFabric de Azure. Para obtener más información, consulte [http://go.microsoft.com/fwlink/?LinkId=204699](http://go.microsoft.com/fwlink/?LinkId=204699).  
  
## <a name="uninstalling-biztalk-server-2010-feature-pack"></a>Desinstalar BizTalk Server 2010 Feature Pack  
 Esta sección proporciona instrucciones sobre cómo desinstalar AppFabric Connect para los servicios.  
  
#### <a name="to-uninstall-the-feature-pack"></a>Para desinstalar el feature pack  
  
1.  Abra Windows Update, haga clic en **ver el historial de actualización**y, a continuación, haga clic en **actualizaciones instaladas**.  
  
2.  En la lista de actualizaciones instaladas, en **BizTalk Server 2010** categoría, haga clic en **BizTalk Server 2010 Feature Pack (octubre de 2010) LDR**y, a continuación, seleccione **desinstalar**. En el cuadro de diálogo Confirmar si desea desinstalar el feature pack, haga clic en **Sí**.  
  
3.  Actualice la lista para comprobar si se ha desinstalado el feature pack.  
  
## <a name="copyright"></a>Copyright  
 Este documento hace referencia a una versión preliminar de un producto de software que puede cambiar substancialmente antes del lanzamiento  comercial final.  Este documento solamente se proporciona con fines informativos y Microsoft no otorga ninguna garantía, expresa ni implícita, con este documento.  La información que se proporciona en este documento, incluidas las direcciones URL y otras referencias a sitios web de Internet, está sujeta a modificaciones sin previo aviso.  El riesgo completo del uso o los resultados del uso de este documento es responsabilidad del usuario.  A menos que se indique lo contrario, las empresas, las organizaciones, los productos, los nombres de dominio, las direcciones de correo electrónico, los logotipos, las personas, los lugares y los eventos que se describen en los ejemplos son ficticios.  No se pretende establecer ni se debe inferir ninguna asociación con ninguna empresa, organización, producto, nombre de dominio, dirección de correo electrónico, logotipo, persona, lugar ni evento real.  Es responsabilidad del usuario el cumplimiento de todas las leyes de derechos de autor aplicables.  Sin limitar los derechos otorgados por las leyes de derechos de autor, ninguna parte de este documento puede ser reproducida o introducida en un sistema de recuperación, ni transmitida de ninguna forma ni por ningún medio, ya sea electrónico, mecánico, fotocopias, grabación u otros, con ningún propósito, sin la previa autorización por escrito de Microsoft Corporation.  
  
 Microsoft puede ser titular de patentes, solicitudes de patentes, marcas, derechos de autor y otros derechos de propiedad intelectual sobre los contenidos de este documento.  El suministro de este documento no le otorga ninguna licencia sobre estas patentes, marcas, derechos de autor u otros derechos de propiedad intelectual, a menos que ello se prevea en un contrato por escrito de licencia de Microsoft.  
  
 © 2010 Microsoft Corporation.  Todos los derechos reservados.  
  
 Microsoft, Active Directory, ActiveX, BizTalk, Excel, InfoPath, JScript, IntelliSense, Internet Explorer, MSDN, Outlook, PivotChart, PivotTable, PowerPoint, SharePoint, Tahoma, Visio, Visual Basic, Visual C++, Visual C#, Visual SourceSafe, Visual Studio, Win32, Windows, Windows NT, Windows PowerShell, Windows Server, Windows Server System y Windows Server son marcas registradas del grupo de compañías Microsoft.  
  
 SAP, R/3, mySAP, mySAP.com, xApps, xApp, SAP NetWeaver y otros productos y servicios SAP mencionados en este documento, así como sus respectivos logotipos son marcas comerciales y marcas comerciales registradas de SAP AG en Alemania y en otros países del mundo. Los demás nombres de productos y servicios mencionados son marcas comerciales y marcas comerciales registradas de sus respectivas compañías. Los datos contenidos en este documento tienen sólo propósitos informativos. Las especificaciones del producto nacional pueden variar.  
  
 Las demás marcas comerciales pertenecen a sus respectivos propietarios.