---
title: Cómo crear una configuración Web para el servicio Web publicado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
- Web services, .msi file
- .msi files, Web services
ms.assetid: 77c86242-1d27-4d99-ae00-fe2614bc13ef
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d894cba37b85c4f18fe2a05af33eb2f4e6e1981e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984389"
---
# <a name="how-to-create-a-web-setup-for-your-published-web-service"></a>Cómo crear una configuración Web para el servicio Web publicado
Puede crear un paquete de instalación para facilitar la configuración del servicio Web en un entorno de producción. Esto produce un archivo .MSI.  
  
### <a name="to-create-an-installation-package-to-produce-an-msi-file-using-visual-studio"></a>Para crear un paquete de instalación y producir un archivo .MSI mediante Visual Studio  
  
1. Abra el proyecto del servicio Web ASP.NET publicado.  
  
2. En el Explorador de soluciones, haga clic en el nodo de la solución, haga clic en **agregar**y, a continuación, haga clic en **nuevo proyecto**.  
  
3. En el **Agregar nuevo proyecto** cuadro de diálogo el **tipos de proyecto** área, expanda **otros tipos de proyectos**, expanda **Setup and Deployment Projects**y, a continuación, seleccione **instalador de Visual Studio**. En el **plantillas** área, seleccione **Web Setup Project**.  
  
4. En el **nombre** cuadro de texto, escriba un nombre para el proyecto de instalación Web. Puede usar el mismo nombre que el proyecto de servicio Web ASP.NET y agregar "_Setup" como sufijo y, a continuación, haga clic en **Aceptar**.  
  
5. En el Explorador de soluciones, haga clic en el nodo del proyecto de instalación Web recién creado y seleccione **vista**y, a continuación, haga clic en **sistema de archivos**.  
  
6. En el **sistema de archivos** ventana, haga clic en el **carpeta de aplicación Web** nodo y seleccione **agregar**, a continuación, haga clic en **resultado del proyecto**.  
  
7. En el **Agregar grupo de resultados del proyecto** cuadro de diálogo, seleccione **resultado principal** y **archivos de contenido** desde el servicio Web ASP.NET de proyecto y, a continuación, haga clic en **Aceptar**.  
  
8. En el Explorador de soluciones, expanda el **Dependencias detectadas** nodo bajo el proyecto de instalación Web.  
  
9. Seleccione todas las dependencias. En el **propiedades** ventana, establezca el **excluir** propiedad **True**.  
  
10. Cree su proyecto de instalación Web.  
  
    > [!NOTE]
    >  Para obtener más información acerca de cómo crear proyectos de instalación Web, vea "Cómo a crear o agregar a Web Setup Project" en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] colección de ayuda en [ http://go.microsoft.com/fwlink/?LinkId=62268 ](http://go.microsoft.com/fwlink/?LinkId=62268).  
  
## <a name="see-also"></a>Vea también  
 [Implementación de servicios web publicados en un equipo sin Visual Studio](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)