---
title: "Cómo instalar el paquete de instalación de Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
ms.assetid: c6b38a2f-ad07-4ccd-b267-9e3510df88c3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21fbacd76598a3a86cfa70b4761bc74420afe561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-web-setup-package"></a>Cómo instalar el paquete de instalación de Web
Utilice el contenido de la carpeta de distribución para instalar el servicio Web en un equipo de destino.  
  
### <a name="to-install-the-web-setup-package"></a>Para instalar el paquete de configuración Web  
  
1.  Copie la carpeta de distribución en el equipo de destino.  
  
    > [!IMPORTANT]
    >  El equipo de destino debe tener instalado el tiempo de ejecución de BizTalk Server, así como los ensamblados de BizTalk necesarios implementados e instalados en la caché de ensamblados global.  
  
2.  Ejecute el. Archivo MSI para instalar el servicio Web y siga al Asistente para instalación le solicita.  
  
    > [!IMPORTANT]
    >  Quite el sufijo "_Setup" cuando el asistente se lo solicite para el directorio virtual. De esta forma, se garantiza que las direcciones de ubicación de recepción coincidan con los archivos .asmx de servicio Web.  
  
3.  Compruebe que la configuración de seguridad del directorio virtual sea la adecuada para la autorización.  
  
## <a name="see-also"></a>Vea también  
 [Implementar servicios Web publicados en un equipo que no tenga Visual Studio](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)