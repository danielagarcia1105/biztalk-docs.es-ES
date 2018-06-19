---
title: Cómo distribuir el paquete de instalación de Web | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, distributing
- Web services, deploying
ms.assetid: 0db71fdf-80d9-4ad5-b0d4-730d0bb549d4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed7e6277045593360cbdfe57848f7313054b60f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254124"
---
# <a name="how-to-distribute-the-web-setup-package"></a>Cómo distribuir el paquete de instalación de Web
Después de crear el paquete de instalación, necesita crear una carpeta de distribución en la que el archivo MSI y el archivo BindingInfo.xml se copian para configurar el servicio Web.  
  
### <a name="to-distribute-the-web-setup-package"></a>Para distribuir el paquete de configuración Web  
  
1.  Cree una carpeta de distribución que contenga los archivos de configuración.  
  
2.  Copie el archivo .MSI de la carpeta saliente del proyecto de configuración Web a la carpeta de distribución.  
  
3.  Copie el archivo BindingInfo.xml de la carpeta temporal en la carpeta del proyecto de servicio Web ASP.NET a la carpeta de distribución.  
  
## <a name="see-also"></a>Vea también  
 [Implementar servicios Web publicados en un equipo que no tenga Visual Studio](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)