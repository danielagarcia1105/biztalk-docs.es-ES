---
title: Seguridad y Windows Installer | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Windows installer
- Windows installer
ms.assetid: efa68c3e-2006-4665-bd41-07defaf4e2e2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9d452fc92e9fcd1c238086513a08b4b392caaa5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017526"
---
# <a name="security-and-windows-installer"></a>Seguridad y Windows Installer
Windows Installer es una eficaz herramienta para instalar y actualizar aplicaciones de BizTalk. Al usar Windows Installer, se deben tener en cuenta los problemas de seguridad que pueden ocasionar los creadores malintencionados de archivos .msi (Windows Installer), además de adoptar las medidas oportunas para evitarlos.  
  
 Normalmente, los administradores ejecutan archivos .msi y, por lo tanto, los procesos ejecutados durante la instalación o actualización de una aplicación tienen privilegios muy altos. Un creador malintencionado de archivos .msi puede aprovechar esto de varias formas, incluidas las siguientes:  
  
- Ejecutar archivos de secuencias de comandos que realizan cambios no deseables en el sistema o los archivos  
  
- Sobrescribir el catálogo COM  
  
- Sobrescribir valores del Registro Estos cambios no se pueden revertir.  
  
- Ejecutar ataques "flood" de congestión del servidor en el sistema de archivos  
  
  Al trabajar con archivos .msi, debe adoptar como mínimo las siguientes medidas de precaución:  
  
- Instale solo archivos .msi en los que confíe totalmente.  
  
  > [!NOTE]
  >  Se recomienda que los responsables de generar los archivos .msi tomen medidas adicionales para firmar los archivos .msi para que así los usuarios puedan comprobar que el origen del archivo es de confianza.  
  
- Pruebe exhaustivamente los archivos .msi antes de usarlos en un entorno de producción.  
  
- Almacene los archivos .msi en carpetas seguras y protegidas con listas de control de acceso discrecional (DACL).  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones de seguridad para la implementación de aplicaciones](../core/security-considerations-for-application-deployment.md)