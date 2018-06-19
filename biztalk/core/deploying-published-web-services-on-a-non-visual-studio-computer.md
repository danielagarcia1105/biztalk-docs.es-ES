---
title: Implementación de publica servicios Web en un equipo que no tenga Visual Studio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- deploying, Web services
- Web services, planning
- Web services, deploying
ms.assetid: e9f8e801-21f3-4458-b05c-206b72868916
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad894c257bdd2eed6462b63c0e921f78ca13c17e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239036"
---
# <a name="deploying-published-web-services-on-a-non-visual-studio-computer"></a>Implementar servicios Web publicados en un equipo que no tenga Visual Studio
Para implementar el servicio Web publicado en un equipo que no tenga [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] instalado, es necesario crear un proyecto de configuración de Web, distribuir el paquete de configuración Web (archivo .msi), instalar el paquete en el equipo que no dispone de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y configurar el servicio Web instalado.  
  
> [!NOTE]
>  También puede usar la consola de administración de BizTalk Server para crear archivos MSI donde se empaquetan aplicaciones de BizTalk que contienen los proyectos de servicios Web publicados. Estos archivos MSI se pueden usar para implementar los proyectos de servicios Web en un equipo que no disponga de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Para obtener más información sobre cómo crear archivos MSI mediante la consola de administración de BizTalk Server, vea [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo crear un programa de instalación de Web para el servicio Web publicado](../core/how-to-create-a-web-setup-for-your-published-web-service.md)  
  
-   [Cómo distribuir el paquete de instalación de Web](../core/how-to-distribute-the-web-setup-package.md)  
  
-   [Cómo instalar el paquete de instalación de Web](../core/how-to-install-the-web-setup-package.md)  
  
-   [Cómo configurar el servicio Web instalado](../core/how-to-configure-the-installed-web-service.md)  
  
## <a name="see-also"></a>Vea también  
 [Implementar aplicaciones de BizTalk](../core/deploying-biztalk-applications.md)